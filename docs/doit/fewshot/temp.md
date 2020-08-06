# 미완성


## `LFW/LFWSampler.hpp`

클래스 분석의 시작은 클래스 정의 형태와 생성자를 분석하는 것이므로 클래스 정의 형태를 살펴봅니다.

^^지금의 목표는 `LFWSampler` 과 `LFWSampler::GetDataFromGlobalBuffer` 을 이해하는 것입니다.^^

```c++ linenums="1"
...
template<typename DTYPE>
class LFWSampler : public DataLoader<DTYPE>{
private:
    /* data */
    int m_numOfClass;

public:
    LFWSampler(int numOfClass, Dataset<DTYPE> *dataset, int batchSize = 1, int useShuffle = FALSE, int numOfWorker = 1, int dropLast = TRUE);
    virtual ~LFWSampler();

    virtual void MakeAllOfIndex(std::vector<int> *pAllOfIndex);

    virtual void DataPreprocess();
    void Tensor2Image(std::string filename, Tensor<DTYPE> *imgTensor, int doValuerScaling);
};
```

- **3**:

    `LFWSampler` 는 `DataLoader` 를 상속받는 클래스 템플릿입니다.

- **9**:

    먼저 생성자를 살펴보겠습니다.

```c++ linenums="1"
template<typename DTYPE> LFWSampler<DTYPE>::LFWSampler(int numOfClass, Dataset<DTYPE> *dataset, int batchSize, int useShuffle, int numOfWorker, int dropLast)
    : DataLoader<DTYPE>(dataset, batchSize, useShuffle, numOfWorker, dropLast) {
    m_numOfClass = numOfClass;
}
```

- **2**:

    생성자에서는 멤버 이니셜라이저로 상위 클래스인 `DataLoader` 를 초기화합니다. 

- **3**:

    그리고 단지 `numOfClass` 를 `m_numOfClass` 에 저장하고 있습니다. 이 코드도 멤버 이니셜라이저로 초기화할 수 있을 것 같아요.

하지만 `LFWSampler` 에 `GetDataFromGlobalBuffer` 가 정의되어 있지 않았어요. 그러니까 상위 클래스인 `DataLoader` 를 분석해야 할 것 같아요.

## `src/DataLoader.hpp`

클래스 분석의 시작은 클래스 정의 형태와 생성자를 분석하는 것이므로 클래스 정의 형태를 살펴봅니다.

```c++ linenums="1"
template<typename DTYPE> class DataLoader {
private:
    /* data */
    Dataset<DTYPE> *m_pDataset;
    int m_lenOfDataset;
    int m_numOfEachDatasetMember;
    std::thread m_aThreadForDistInfo;
    std::thread *m_aaWorkerForProcess;  // dynamic allocation
    int m_numOfWorker;
    int m_nowWorking;

    // for distribute data info
    std::queue<std::vector<int> *> m_splitedIdxBuffer;
    sem_t m_distIdxFull;  // numOfthread + 1;
    sem_t m_distIdxEmpty;
    sem_t m_distIdxMutex;

    int m_batchSize;
    int m_dropLast;  // implement yet
    int m_useShuffle;

    // for global buffer
    std::queue<std::vector<Tensor<DTYPE> *> *> m_globalBuffer;
    sem_t m_globalFull;  // numOfthread * 2
    sem_t m_globalEmpty;
    sem_t m_globalMutex;

    void Alloc();
    void Delete();

    void Init();

public:
    DataLoader(Dataset<DTYPE> *dataset, int batchSize = 1, int useShuffle = FALSE, int numOfWorker = 1, int dropLast = TRUE);
    virtual ~DataLoader();


    void                          StartProcess();
    void                          StopProcess();

    // distribute data idx to each thread
    void                          DistributeIdxOfData2Thread();
    virtual void                  MakeAllOfIndex(std::vector<int> *pAllOfIndex);

    virtual void                  DataPreprocess();

    void                          Push2IdxBuffer(std::vector<int> *setOfIdx);

    std::vector<int>            * GetIdxSetFromIdxBuffer();

    Tensor<DTYPE>               * Concatenate(std::queue<Tensor<DTYPE> *>& setOfData);

    void                          Push2GlobalBuffer(std::vector<Tensor<DTYPE> *> *preprocessedData);

    std::vector<Tensor<DTYPE> *>* GetDataFromGlobalBuffer();

    int GetBatchSize(){return m_batchSize;}
    int GetWorkingSignal(){return m_nowWorking;}
    int GetNumOfEachDatasetMember(){return m_numOfEachDatasetMember;}
    Dataset<DTYPE> * GetDataset(){return m_pDataset;}

    // static int random_generator(int upperbound);
};
```

- **1**:

    `DataLoader` 는 클래스 템플릿으로 정의되어 있습니다.

- **34**:

    생성자가 이렇게 정의되어 있습니다. 생성자를 분석해봅니다.

```c++ linenums="1"
template<typename DTYPE> DataLoader<DTYPE>::DataLoader(Dataset<DTYPE> *dataset, int batchSize, int useShuffle, int numOfWorker, int dropLast) {
    this->Init();
    // need to default value to run the data loader (background)
    m_pDataset = dataset;
    // batch size
    m_batchSize = batchSize;
    assert(m_batchSize > 0);
    // random or not
    m_useShuffle = useShuffle;
    // number of thread
    m_numOfWorker = numOfWorker;
    assert(m_numOfWorker > 0);
    // Drop last
    m_dropLast = dropLast;

    // elicit information of data;
    m_lenOfDataset = m_pDataset->GetLength();
    assert(m_lenOfDataset > 0);
    m_numOfEachDatasetMember = m_pDataset->GetNumOfDatasetMember();
    assert(m_numOfEachDatasetMember > 0);

    sem_init(&m_distIdxFull,  0, 0);
    sem_init(&m_distIdxEmpty, 0, m_numOfWorker + 1);
    sem_init(&m_distIdxMutex, 0, 1);

    sem_init(&m_globalFull,   0, 0);
    sem_init(&m_globalEmpty,  0, m_numOfWorker * 2);
    sem_init(&m_globalMutex,  0, 1);

    this->Alloc();
    this->StartProcess();
}
```

- **2**:

    `Init` 메소드는 다음과 같이 정의되어 있어요.

    ```c++ linenums="1"
    template<typename DTYPE> void DataLoader<DTYPE>::Init() {
        m_pDataset               = NULL;
        m_lenOfDataset           = 1;
        m_numOfEachDatasetMember = 1;
        m_aaWorkerForProcess     = NULL;
        m_numOfWorker            = 1;
        m_nowWorking             = FALSE;
        m_batchSize              = 1;
        m_dropLast               = FALSE;
        m_useShuffle             = FALSE;
    }
    ```

    멤버변수들을 초기화해주는 함수라는 것을 알 수 있어요. 하지만 멤버 이니셜라이저를 사용하면 좋을 것 같습니다.

- **4**:

    `m_pDataset` 에 `dataset` 을 저장하는데 마찬가지로 멤버 이니셜라이저를 사용해서 더 나은 성능을 기대할 수 있을 것 같아요.

- **17**:

    `m_pDataset` 의 `GetLength` 함수를 호출하는데 이것을 이해하기 위하여 먼저 `Dataset` 클래스를 이해할 필요가 있습니다. 계속 코드를 이해할 때 `Dataset` 클래스가 걸리네요. 하지만 우선 데이터 길이를 반환받는 함수라고 생각하고 계속 진행합니다.

- **30**:

    `Alloc` 메소드는 다음과 같이 정의되어 있습니다.

    ```c++ linenums="1"
    template<typename DTYPE> void DataLoader<DTYPE>::Alloc() {
        // thread allocate
        m_aaWorkerForProcess = new std::thread[m_numOfWorker];
    }
    ```

    스레드 배열을 생성하여 `std::thread m_aaWorkerForProcess` 를 초기화합니다.

- **31**:

    `StartProcess` 메소드의 정의입니다. 

    ```c++ linenums="1"
    template<typename DTYPE> void DataLoader<DTYPE>::StartProcess() {
        // Generate thread for Dist - DistributeIdxOfData2Thread()
        // Generate thread set for Process -
        m_nowWorking = TRUE;

        m_aThreadForDistInfo = std::thread([&]() {
            this->DistributeIdxOfData2Thread();
        });  // lambda expression
        printf("Generate dataloader base thread\r\n");

        for (int i = 0; i < m_numOfWorker; i++) {
            m_aaWorkerForProcess[i] = std::thread([&]() {
                this->DataPreprocess();
            });  // lambda expression
            printf("Generate worker[%d] for data preprocessing\r\n", i);
        }
    }
    ```

    - **4**:

        `int m_nowWorking` 을 `TRUE` 로 초기화합니다. 하지만 `TRUE` 와 `FALSE` 로 사용할 변수라면 $4$ 바이트나 되는 `int` 가 아니라 $1$ 바이트짜리 `bool` 에 저장하는 것이 나을 것 같아요.

    - **6-8**:

        스레드를 생성하고 스레드 정보를 `m_aThreadForDistInfo` 에 저장하며 `DistributeIdxOfData2Thread` 함수를 호출합니다. 함수 이름만 봐서는 처리할 데이터를 스레드에 공평하게 분배하기 위하여 인덱스를 분배하는 사전작업을 하는 함수인 것 같아요.

        하지만 어차피 함수 하나를 호출하는데 왜 람다 표현식으로 스레드를 호출했는지 모르겠습니다. 연구를 해봐야할듯.

        `DistributeIdxOfData2Thread` 함수는 다음과 같아요.

        ```c++ linenums="1"
        template<typename DTYPE> void DataLoader<DTYPE>::DistributeIdxOfData2Thread() {
            std::vector<int> *allOfIdx = new std::vector<int>();
            this->MakeAllOfIndex(allOfIdx);         // virtual function
            std::vector<int> *setOfIdx = NULL;
            int dropLastSize           = allOfIdx->size() % m_batchSize; // num of dropLast
            int numOfBatchBlockSize    = allOfIdx->size() / m_batchSize;
            int cnt                    = 0;

            if (m_useShuffle)
                std::random_shuffle(allOfIdx->begin(), allOfIdx->end(), random_generator);

            while (m_nowWorking) {
                setOfIdx = new std::vector<int>(m_batchSize);

                for (int i = 0; i < m_batchSize; i++) {
                    (*setOfIdx)[i] = (*allOfIdx)[m_batchSize * cnt + i];
                }
                cnt++;

                this->Push2IdxBuffer(setOfIdx);

                if (cnt == numOfBatchBlockSize) {
                    if (!m_dropLast && dropLastSize) {
                        std::reverse(allOfIdx->begin(), allOfIdx->end());

                        if (m_useShuffle)
                            std::random_shuffle(allOfIdx->begin() + dropLastSize, allOfIdx->end(), random_generator);
                    } else {
                        if (m_useShuffle)
                        std::random_shuffle(allOfIdx->begin(), allOfIdx->end(), random_generator);
                    }
                    cnt = 0;
                }
            }

            delete allOfIdx;
        }       
        ```

        - **3**:

            `MakeAllOfIndex` 함수에 `vector` 포인터 `allOfIdx` 를 전달합니다. `MakeAllOfIndex` 함수는 다음과 같아요.

            ```c++ linenums="1"
            template<typename DTYPE> void DataLoader<DTYPE>::MakeAllOfIndex(std::vector<int> *pAllOfIndex)
            {
                pAllOfIndex->resize(m_lenOfDataset);
                for (int i = 0; i < m_lenOfDataset; i++)
                    (*pAllOfIndex)[i] = i;
            }           
            ```

            단순히 `resize` 로 벡터 크기를 정한다음 `0, 1, ..., m_lenOfDataset-1` 까지 벡터에 대입해주네요.

            `std::vector` 는 원소가 추가될 때마다 공간이 부족하면 $2$ 의 배승만큼 공간을 늘리는데 그것에 소모되는 비용을 줄이고자 이렇게 짠 것 같습니다. 하지만 `std::vector::reserve` 를 사용하는 것과 비교하여 어떤 게 더 좋은지 연구가 필요할 것 같네요.
        
        - **13-16**:

            `vector( size_type count, const T& value, const Allocator& alloc = Allocator());` 의 형태로 벡터를 초기화하고 있는데 이는 `C++11` 까지 지원되는 문법이므로 나중 상위 호환성을 맞추어야할 때 바꿔야할 것 같습니다.

            어쨌든 `m_batchSize` 만큼 `allOfIdx` 를 분배해주고 있습니다.
        
        - **20**:

            `Push2IdxBuffer` 함수에 `m_batchSize` 만큼 `allOfIdx` 가 분배된 `setOfIdx` 를 전달합니다.

            `Push2IdxBuffer` 는 이렇게 정의되어 있어요.

            ```c++ linenums="1"
            template<typename DTYPE> void DataLoader<DTYPE>::Push2IdxBuffer(std::vector<int> *setOfIdx) {
                sem_wait(&m_distIdxEmpty);
                sem_wait(&m_distIdxMutex);

                m_splitedIdxBuffer.push(setOfIdx);

                sem_post(&m_distIdxMutex);
                sem_post(&m_distIdxFull);
            }
            ```

            단순히 **Critical Section** 에 들어가기 전에 스레드들을 잠궈주고     `std::queue<std::vector<int> *> m_splitedIdxBuffer` 에 `setOfIdx` 를 넣어주네요.
    
        이런 식으로 `DistributeIdxOfData2Thread` 가 스레드들에 `m_batchSize` 만큼 `allOfIdx` 를 분배해준다는 것을 알 수 있었습니다. 나중에 주석을 좀 더 자세하게 달아놓거나 API 를 좀 더 자세히 써두면 사람들이 상세한 코드 분석 없이도 주석만 보고 코드 분석을 빠르게 진행할 수 있을 것 같습니다.

        이렇게 코드 분석을 통하여 함수 기능을 이해하는 것은 시간이 조금 오래걸릴 수도 있기 때문에 API 와 주석으로 이해할 수 있도록 하는 것이 좋을 것 같아요.

    - **11-14**:

        `m_numOfWorker` 만큼 `DataPreprocess` 를 스레드로 호출하며 `m_aaWorkerForProcess` 벡터에 스레드를 저장합니다.

        `DataPreprocess` 는 다음과 같습니다.

        ```c++ linenums="1"
        template<typename DTYPE> void DataLoader<DTYPE>::DataPreprocess() {
            // for thread
            // doing all of thing befor push global buffer
            // arrange everything for worker
            std::queue<Tensor<DTYPE> *> *localBuffer       = new std::queue<Tensor<DTYPE> *>[m_numOfEachDatasetMember];
            std::vector<int> *setOfIdx                     = NULL;
            int idx                                        = 0;
            std::vector<Tensor<DTYPE> *> *data             = NULL;
            Tensor<DTYPE> *pick                            = NULL;
            std::vector<Tensor<DTYPE> *> *preprocessedData = NULL;
            std::cout << "DataLoader worker" << '\n';
            while (m_nowWorking) {
                // get information from IdxBuffer
                setOfIdx = this->GetIdxSetFromIdxBuffer();

                for (int i = 0; i < m_batchSize; i++) {
                    idx = (*setOfIdx)[i];
                    data = m_pDataset->GetData(idx);

                    for (int j = 0; j < m_numOfEachDatasetMember; j++) {
                        // Chech the type of Data for determine doing preprocessing (IMAGE)
                        // if true do data Preprocessing
                        // push data into local buffer
                        localBuffer[j].push((*data)[j]);
                    }

                    delete data;
                    data = NULL;
                }

                // delete set of idx vector
                delete setOfIdx;
                setOfIdx = NULL;

                preprocessedData = new std::vector<Tensor<DTYPE> *>(m_numOfEachDatasetMember, NULL);  // do not deallocate in this function!

                for (int k = 0; k < m_numOfEachDatasetMember; k++) {
                    // concatenate each localbuffer
                    // push preprocessedData vector
                    (*preprocessedData)[k] = this->Concatenate(localBuffer[k]);
                }

                // push preprocessedData into Global buffer
                this->Push2GlobalBuffer(preprocessedData);
                preprocessedData = NULL;
            }

            delete[] localBuffer;
        }
        ```
            
    이로써 `StartProcess` 는 