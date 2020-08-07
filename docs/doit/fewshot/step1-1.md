!!! info

    이곳은 **fewshot-learning** 을 구현하기 위한 [**WICWIU**](https://github.com/WICWIU/WICWIU) 개발팀의 [**WICWIU**](https://github.com/WICWIU/WICWIU) 분석/코딩 과정을 기록해두는 곳입니다.

[**WICWIU** 의 학습 과정은](../../dev/wicwiu/learn.md) 다음과 같이 이루어졌다는 것을 이미 알아보았습니다.

- Step 1. 학습 데이터 &rarr; `Tensor`

- [Step 2. 순전파](step2.md)

- [Step 3. 역전파](step3.md)

- [Step 4. Weight 파라미터 갱신](step4.md)

여기는 fewshot 팀이 "**Step 1. 학습 데이터 &rarr; `Tensor`**" 을 구현하기 위한 과정을 기록해두는 곳입니다.

# Coding: CasiaWebFace Image to vector

## `getDirList` 함수

먼저 **CasiaWebFace** 이미지를 자동으로 읽어오기 위하여 디렉토리 리스트를 얻을 수 있는 코드를 만들어 봤다.

```c++ linenums="1"
#include <string>
#include <iostream>
#include <fstream>
#include <iterator>
#include <vector>
#include <dirent.h>
#include <sys/types.h>

DIR* getDirList(const char * dirName)
{
    DIR *dir;
    if ((dir = opendir(dirName)) == NULL)
        throw std::invalid_argument("could not open directory");
    return dir;
}
```

- **11~14**:

    `getDirList` 함수에 디렉토리 경로를 입력하면 디렉토리 내부 파일 정보를 갖고 있는 `DIR` 포인터를 반환한다.

    이 함수를 사용하여 다음과 같이 **CasiaWebFace** 이미지가 저장되어 있는 `/tmp/casia_train` 디렉토리의 내부 파일을 반환받는 코드를 짤 수 있다.

## `test_getDirList` 함수

!!! info

    `test_getDirList` 함수의 `test_` 는 **camel case** 가 아닌 **snake case** 로 되어있는데, 테스트 코드임을 강조하기 위하여 그렇게 한 것이다. 나머지 코드는 모두 **camel case** 로 코딩되어 있다.

```c++ linenums="1"
void test_getDirList(bool error=false);

int main(int argc, char const *argv[])
{
    test_getDirList();
    return EXIT_SUCCESS;
}

void test_getDirList(bool error)
{
    DIR* dir;
    try
    {
        dir = (error) ?\
            getDirList("aweoifjaowief") :\
            dir = getDirList("/tmp/casia_train");
        struct dirent *ent;

        while ((ent = readdir(dir)) != NULL)
        {
            std::cout << ent->d_name << std::endl;
        }
        closedir(dir);
    } 
    catch (const std::invalid_argument& e)
    {
        std::cerr << e.what() << std::endl;
    }
}
```

- **1**:

    `test_getDirList` 는 `error` 인자를 받는데 `false` 가 기본값으로 설정되어 있다. 

- **14~21**:

    `error = false` 인  경우 `/tmp/casia_train` 디렉토리 내부 파일들을 출력한다. 

- **14~21**:

    `error` 를 `true` 로 설정한다면 의도적으로 에러를 발생시키는 코드가 된다. 즉, 존재하지 않는 파일 경로를 `getDirList` 함수에 입력하여 에러를 발생시켜서 에러 처리 코드(`try~catch`) 가 잘 작동하는지 검증한다.

## `test_getFirstCasiaImage` 함수

이후 `getDirList` 함수를 활용하여 `/tmp/casia_train` 의 첫번째 디렉토리의 첫번째 이미지를 읽어보는 테스트 코드를 만들어 봤다. 

```c++ linenums="1"
void test_getFirstCasiaTrainImage();

int main(int argc, char const *argv[])
{
    test_getFirstCasiaTrainImage();
    return EXIT_SUCCESS;
}

void test_getFirstCasiaTrainImage()
{
    DIR * dir;
    std::string casiaTrainDirPath = "/tmp/casia_train";
    std::string casiaTrainFirstDirPath;
    std::string casiaTrainFirstImagePath;

    //
    // Get first directory of casia_train
    //
    try
    {
        dir = getDirList(casiaTrainDirPath.c_str());
        if (dir == nullptr)
            throw;
        struct dirent *ent;

        for (int idx = 0; (ent = readdir(dir)) != NULL; idx++)
        {
            if (idx == 2) // first index (because: 0 -> . 1 -> .. 2 -> first path)
            {
                casiaTrainFirstDirPath = casiaTrainDirPath + "/" + std::string(ent->d_name);
            }
        }
        closedir(dir);
    } 
    catch (const std::invalid_argument& e)
    {
        std::cerr << e.what() << std::endl;
    }

    //
    // Get first image of first directory
    //
    try
    {
        dir = getDirList(casiaTrainFirstDirPath.c_str());
        if (dir == nullptr)
            throw;
        struct dirent *ent;

        for (int idx = 0; (ent = readdir(dir)) != NULL; idx++)
        {
            if (idx == 2) // first index (because: 0 -> . 1 -> .. 2 -> first path)
            {
                casiaTrainFirstImagePath = casiaTrainFirstDirPath + "/" +std::string(ent->d_name);
            }
        }
        closedir(dir);
    } 
    catch (const std::invalid_argument& e)
    {
        std::cerr << e.what() << std::endl;
    }

    //
    // Convert image to vector<unsigned char>
    //
    std::ifstream casiaTrainFirstImage(casiaTrainFirstImagePath, std::ios::binary);
    std::vector<unsigned char> casiaTrainFirstImageBuffer(std::istreambuf_iterator<char>(casiaTrainFirstImage), {});
    
    //
    // Show result and converted image
    //
    std::cout << "First image of first caisa_train sub directory:" << std::endl;
    std::cout << '\t' << casiaTrainFirstImagePath  << std::endl;
    std::cout << "casiaTrainFirstImageBuffer size: " << std::endl;
    std::cout << '\t' << casiaTrainFirstImageBuffer.size() << std::endl;
    std::cout << "First 10 bytes:" << std::endl;
    std::cout << "\t";
    int ct=0;
    for (const auto byte: casiaTrainFirstImageBuffer)
    {
        if (ct < 10)
            std::cout << static_cast<int>(byte) << ' ';
        ct++;
    }
    std::cout << std::endl;
}
```

- **19~39**:

    `/tmp/casia_train` 의 첫번째 디렉토리 경로를 `casiaTrainFirstDirPath` 에 저장한다.

- **42~61**:

    `/tmp/casia_train` 의 첫번째 디렉토리의 첫번째 이미지 경로를 `casiaTrainFirstImagePath` 에 저장한다.

- **66~67**:

    `/tmp/casia_train` 의 첫번째 디렉토리의 첫번째 이미지를 바이너리로 읽고 `unsigned char` 자료형을 갖는 `vector` 로 변환한다.

- **82~87**:

    이미지의 첫 `10` 바이트를 읽고 `int` 로 형변환하여 출력해본다. 그냥 잘 읽혔는지 확인하는 테스트 코드이다.

!!! info

    [**WICWIU**](https://github.com/WICWIU/WICWIU) 는 `C++` 프로젝트이기 때문에 `C` 스타일로 코딩하는 것이 아니라 `C++` 스타일로 코딩하려고 노력하고 있습니다. 

    예를 들어서 다음 코드는 `C` 스타일 형변환입니다.

    ```c
    for (const auto byte: casiaTrainFirstImageBuffer)
    {
        std::cout << (int)(byte) << ' ';
    }
    ```

    다음 코드는 `C++` 스타일 형변환입니다.

    ```c
    for (const auto byte: casiaTrainFirstImageBuffer)
    {
        std::cout << static_cast<int>(byte) << ' ';
    }
    ```

    `C++` 프로젝트에서 `C` 스타일로 코딩하면 프로젝트 안정성에 문제가 생길 수도 있기 때문에 주의해야 할 것 같습니다. 다음 링크를 참조하면 `C++` 코딩 스타일 등에 대한 좋은 정보를 얻을 수 있습니다.

    - https://github.com/AnthonyCalandra/modern-cpp-features

    - https://github.com/isocpp/CppCoreGuidelines

    - https://github.com/lefticus/cppbestpractices

---

# Analysis: Dataset to Tensor

fewshot 팀은 LFW 팀이 개발해둔 코드를 참고할 수 있기 때문에 먼저 LFW 코드를 분석해보았다. [**WICWIU**](https://github.com/WICWIU/WICWIU) 개발 가이드의 [**WICWIU 로 학습하기**](../../dev/wicwiu/learn.md) 의 첫번째 과정이 "**Step 1. 학습 데이터 &rarr; `Tensor`**" 이기 때문에 먼저 학습시켜야할 데이터셋인 **Casia Web Face** 를 `Tensor` 로 변환해야 했다. 그래서 LFW 팀의 코드에서 데이터셋을 `Tensor` 로 변환하는 코드 흐름을 중점으로 분석을 시도해보았다.

!!! note

    `tutorials/LFW/` 경로를 `LFW/` 로 축약하여 사용하였다.

!!! info "분석 방향"

    `LFW` 를 사용하여 인공신경망을 학습하고 테스트하는 `main` 함수를 ^^데이터셋을 `Tensor` 로 변환하여 인공신경망에 입력하는 것을 중심으로 분석^^ 해본다.

!!! tldr "분석 지도"

    - [ ] `LFW/main.cpp`: `main` 함수

## `LFW/main.cpp`: `main` 함수

!!! help "분석 목표"

    `LFW` 를 사용하여 데이터셋을 가져온 후 학습하고 테스트하는 `main` 함수에서 어떻게 데이터셋을 가져오고 `Tensor` 로 변환하는지 이해하기

```c++ linenums="1" hl_lines="13-15"
...
#define NUMBER_OF_CLASS               5749          // for lfw_funneled
...
int main(int argc, char const *argv[])
{
...
    Tensorholder<float> *x     = new Tensorholder<float>(1, BATCH, 1, 1, 145200, "x");
    Tensorholder<float> *label = new Tensorholder<float>(1, BATCH, 1, 1, NUMBER_OF_CLASS, "label");

    // ======================= Select net ===================
    NeuralNetwork<float> *net = new my_FaceNet<float>(x, label, NUMBER_OF_CLASS);
...
    vision::Compose *transform = new vision::Compose({new vision::Resize(224), new vision::CenterCrop(220)});
    LFWDataset<float> *train_dataset = new LFWDataset<float>("./data", "lfw_funneled", NUMBER_OF_CLASS, transform);
    DataLoader<float> *train_dataloader = new LFWSampler<float>(NUMBER_OF_CLASS, train_dataset, BATCH, TRUE, 1, FALSE);
...
```

- **13-15**:

    `Compose` 객체를 `Resize(224)` 와 `Centercrop(220)` 파라미터로 생성한다.

    그리고 `LFWDataset` 을 생성하고 `LFWSampler` 를 만든다. 

```c++ linenums="1" hl_lines="5"
...
        // ======================= Train =======================
        net->SetModeTrain();
        for (int j = 0; j < loop_for_train; j++) {
            std::vector<Tensor<float> *> * temp =  train_dataloader->GetDataFromGlobalBuffer();
...
            net->FeedInputTensor(2, (*temp)[0], (*temp)[1]);
...
```

- **5**:

    학습을 시작할 때 `LFWSampler::GetDataFromGlobalBuffer` 를 통하여 데이터셋을 `Tensor<float>` 포인터형 벡터에 저장한다.

- **7**:

    `Tensor` 로 변환된 데이터셋을 신경망에 입력해준다.

```cpp linenums="1" 
...
        // ======================= Test ======================
...
            for(int i = 0; i < curBatch; i++){
                dataset.CopyData(batchIdx * BATCH + i, vTestSample[i]);
            }

			net->InputToFeature(INPUT_DIM, vTestSample.size(), &vTestSample[0], FEATURE_DIM, &vTestFeature[0], BATCH);
...
```

- **5**:

    테스트를 할 때에는 `LFWDataset::CopyData` 를 통하여 데이터셋을 `float` 포인터형 벡터에 저장한다.

- **8**:

    여기에서 신경망에 데이터셋을 입력해주는 것 같다.

!!! done "분석 결론"

    `main` 함수에서는 인공신경망을 구성한 후 학습 시에는 `LFWSampler::GetDataFromGlobalBuffer` 으로 데이터셋을 마련하고 테스트 시에는 `LFWDataset::CopyData` 로 데이터셋을 마련한다.

!!! info "분석 방향"
    
    그러므로 `LFWSampler::GetDataFromGlobalBuffer` 와 `LFWDataset::CopyData` 를 분석하면 데이터셋을 어떻게 `Tensor` 로 바꾸어 신경망에 입력할 수 있는지 참고할 수 있다.

    그런데 `LFWSampler` 가 `LFWDataset` 에 의존하기 때문에 `LFWDataset` 을 분석하고 `LFWSampler` 을 분석해야 한다. 

    그런데 `LFWDataset` 은

    ```c++
    LFWDataset<float> *train_dataset = new LFWDataset<float>("./data", "lfw_funneled", NUMBER_OF_CLASS, transform);
    ```

    으로 생성되며 `vision::Compose *transform` 가 인자로 전달되기 때문에 먼저 

    ```c++
    vision::Compose *transform = new vision::Compose({new vision::Resize(224), new vision::CenterCrop(220)});
    ``` 

    부터 분석해야 한다.

    그런데 `Compose` 는 생성자에서 `{new vision::Resize(224), new vision::CenterCrop(220)}` 을 전달받기 때문에 이것들부터 분석해야 한다.

    그런데 `Resize` 와 `CenterCrop` 클래스는 `Transform` 클래스를 상속받는다. 그러므로 먼저 `Transform` 클래스를 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [ ] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/ImageProcess.hpp`: `Transform` 생성자

!!! help "분석 목표"

    `Transform` 객체 생성 과정 이해하기

```c++ linenums="1"
namespace vision {
class Transform {
private:
public:
    Transform() { }
    virtual ~Transform() {}
    virtual void DoTransform(ImageWrapper& imgWrp) { }
};
...
}
```

- **1-2**:

    `Transform` 클래스는 이름공간 `vision` 에 선언된 클래스이다.

- **5-7**:

    생성자와 메소드들이 구현되어 있지 않다. 이로써 클래스 구조 유지를 위한 추상 클래스임을 알 수 있다.

    !!! danger

        그렇다면 이 클래스를 생성하는 것을 막기 위하여 나중에 추상 클래스로 선언할 필요가 있을 것 같다.

!!! done "분석 결론"

    `Transform` 은 `DoTransform` 메소드 구조만 갖고 있는 추상클래스이다.

!!! info "분석 방향"

    이제 `new vision::Resize(224)` 를 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/ImageProcess.hpp`: `Resize` 생성자

!!! help "분석 목표"

    `Resize` 객체 생성 과정(`new vision::Resize(224)`) 이해하기

```c++ linenums="1"
namespace vision {
...
class Resize : public Transform {
private:
    int newHeight;
    int newWidth;

public:
    Resize(int heigth, int width) : newHeight(heigth), newWidth(width) {
    }

    Resize(int size) : newHeight(size), newWidth(size) {
    }

    virtual ~Resize() {}

    virtual void DoTransform(ImageWrapper& imgWrp) {
...
    }
};
...
}
```

- **1-3**:

    `Resize` 는 이름공간 `vision` 에 정의된 `Transform` 의 하위 클래스이다.

- **12**:

    `224` 를 전달받아 `newHeight` 와 `newWidth` 에 저장한다.

!!! done "분석 결론"

    `Resize` 객체 생성 과정(`new vision::Resize(224)`) 은 `224` 를 전달받아 `newHeight` 와 `newWidth` 에 저장한다.

!!! info "분석 방향"

    이제 `new vision::CenterCrop(220)` 를 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

!!! help "분석 목표"

    `CenterCrop` 객체 생성 과정(`new vision::CenterCrop(220)`) 이해하기

```c++ linenums="1"
namespace vision {
...
class CenterCrop : public Transform {
private:
    int m_heigth;
    int m_width;

public:
    CenterCrop(int heigth, int width) : m_heigth(heigth), m_width(width) {
    }
    CenterCrop(int size) : m_heigth(size), m_width(size) {
    }
    virtual ~CenterCrop() {}
    virtual void DoTransform(ImageWrapper& imgWrp) {
...
    }
};
...
}
```

- **1-3**:

    `CenterCrop` 은 이름공간 `vision` 에 정의된 `Transform` 의 하위 클래스이다.

- **11**:

    `220` 를 전달받아 `m_height` 와 `m_width` 에 저장한다.

    !!! danger

        **Naming Convention** 이 통일이 안되어있기 때문에 나중에 통일해야할 것 같다.

!!! done "분석 결론"

    `CenterCrop` 객체 생성 과정(`new vision::CenterCrop(220)`) 은 `220` 를 전달받아 `m_height` 와 `m_width` 에 저장한다.

!!! info "분석 방향"

    이제 

    ```c++
    vision::Compose *transform = new vision::Compose({new vision::Resize(224), new vision::CenterCrop(220)});
    ``` 

    을 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/ImageProcess.hpp`: `Compose` 생성자

!!! help "분석 목표"

    `Compose` 객체 생성 과정
    
    ```c++
    vision::Compose *transform = new vision::Compose({new vision::Resize(224), new vision::CenterCrop(220)});
    ```
    
    이해하기

```c++ linenums="1"
namespace vision {
...
class Compose : public Transform {
private:
    std::vector<Transform *> m_listOfTransform;
    int m_size;

public:
    Compose(std::initializer_list<Transform *> lvalue) : m_listOfTransform(lvalue) {
        m_size = m_listOfTransform.size();
    }

    virtual ~Compose() {
...
    }

    virtual void DoTransform(ImageWrapper& imgWrp) {
...
    }
};
...
}
```

- **1-3**: 

    `Compose` 은 이름공간 `vision` 에 정의된 `Transform` 의 하위 클래스이다.

- **9-11**:

    `{new vision::Resize(224), new vision::CenterCrop(220)}` 를 전달받아 `std::vector<Transform *> m_listOfTransform` 에 저장하고 
    
    `std::vector<Transform *> m_listOfTransform` 의 사이즈를 `int m_size` 에 저장한다.

!!! done "분석 결론"

    `Compose` 객체 생성 과정
        
    ```c++
    vision::Compose *transform = new vision::Compose({new vision::Resize(224), new vision::CenterCrop(220)});
    ```
    
    은
    
    `{new vision::Resize(224), new vision::CenterCrop(220)}` 을 전달받아 `std::vector<Transform *> m_listOfTransform` 에 저장하고,

    `std::vector<Transform *> m_listOfTransform` 의 사이즈를 `int m_size` 에 저장한다.

!!! info "분석 방향"

    이제 

    ```c++
    LFWDataset<float> *train_dataset = new LFWDataset<float>("./data", "lfw_funneled", NUMBER_OF_CLASS, transform);
    ```

    을 분석해야 한다.

    그런데 `LFWDataset` 은 `Dataset` 의 하위클래스이기 때문에 먼저 `Dataset` 를 분석해본다. 

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [ ] `src/Dataset.hpp`: `Dataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/Dataset.hpp`: `Dataset` 생성자

!!! help "분석 목표"

    `Dataset` 객체 생성 과정 이해하기

```c++ linenums="1"
template<typename DTYPE> class Dataset {  // [] operator override
private:
    /* data */
    char m_dataPath[256];
    std::vector<char *> imageName;
    std::vector<int> label;
	std::vector<int> m_vPosIndex;
	std::vector<int> m_vNegIndex;

public:
    Dataset();
    virtual ~Dataset();

    virtual void                          Alloc();
    virtual void                          Dealloc();
    virtual std::vector<Tensor<DTYPE> *>* GetData(int idx);
    virtual std::vector<Tensor<DTYPE> *>* GetDataOfPositiveLabel(int anchorIdx, int *pPosIdx = NULL);
    virtual std::vector<Tensor<DTYPE> *>* GetDataOfNegativeLabel(int anchorIdx, int *pNegIdx = NULL);
    void                                  SetLabel(const int *pLabel, int noLabel);
    void                                  SetLabel(const unsigned char *pLabel, int noLabel);
    virtual int 						  GetLabel(int idx) {
...
    }
    virtual int                           GetLength() { return label.size(); }
    int                                   GetNumOfDatasetMember();
    virtual void                           CopyData(int idx, DTYPE *pDest) {             // copy i-th iamge into pDest. (designed for k-NN)
...
    }   

	virtual void 						 SetPosNegIndices(std::vector<int> *pvPosIndex, std::vector<int> *pvNegIndex){	// registers indices fo positive and negative samples for each sample
...
	}
    std::vector<int> &                   GetPositiveIndices() { return m_vPosIndex; }
    std::vector<int> &                   GetNegativeIndices() { return m_vNegIndex; }
	virtual int 						 GetPositiveIndex(int idx){			// for triplet loss
...
	}
	virtual int 						 GetNegativeIndex(int idx){			// for triplet loss
...
	}    
};
...
template<typename DTYPE> Dataset<DTYPE>::Dataset() {
}
```

- **1**:

    `Dataset` 은 클래스 템플릿으로 정의된 클래스이다. 

    !!! danger
    
        [API](../../api.md) 에도 `Dataset` 클래스의 설명이 나와있지 않기에 일일이 소스코드를 분석함으로써 클래스를 이해해야 한다. 나중에 API 에 설명을 추가하면 좋을 것 같다.

- **30-40**:

    !!! danger

        그런데 이 메소드들이 `Dataset` 추상 클래스에 있어야하는지 모르겠다. 나중에 클래스 상속관계를 분석해서 정리를 한번 할 필요가 있을 것 같다.

- **43-44**:

    `Dataset` 생성자는 구현되어있지 않다. 

    !!! danger
    
        이는 하위 클래스들의 객체 구조를 유지하기 위한 추상 메소드이기 때문에 순수 추상 메소드로 선언해서 `Dataset` 의 생성을 방지할 필요가 있을 것 같다.

!!! done "분석 결론"

    `Dataset` 객체는 구현되어 있지 않은 추상 클래스이다.

!!! info "분석 방향"

    이제 

    ```c++
    LFWDataset<float> *train_dataset = new LFWDataset<float>("./data", "lfw_funneled", NUMBER_OF_CLASS, transform);
    ```

    을 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [x] `src/Dataset.hpp`: `Dataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

!!! help "분석 목표"

    `LFWDataset` 객체 생성 과정

    ```c++
    LFWDataset<float> *train_dataset = new LFWDataset<float>("./data", "lfw_funneled", NUMBER_OF_CLASS, transform);
    ```

    이해하기 

```c++ linenums="1"
template<typename DTYPE>
class LFWDataset : public Dataset<DTYPE>{
private:
    int m_numOfImg;
    std::string m_rootPath;
    std::string m_dataPath;
    vision::Compose *m_transform;
    sem_t sem;

    int m_useClasNum;
    std::vector<std::string> m_className;
    std::vector<std::string> m_aImagePath;
    std::vector<int> m_vSamplePerClass;
    int trigger;
    int imgNum[20];

    void           CheckClassList();
    void           CreateImageListOfEachClass();
    void           CountSamplePerClass(int maxClass = 0);
    void           AllocImageBuffer(int idx, ImageWrapper& imgWrp);
    void           DeleteImageBuffer(ImageWrapper& imgWrp);
    Tensor<DTYPE>* Image2Tensor(ImageWrapper& imgWrp, int doValueScaling);

public:
    LFWDataset(std::string rootPath, std::string dataPath, int useClassNum, vision::Compose *transform) {
        m_rootPath   = rootPath;
        m_dataPath   = dataPath;
        m_useClasNum = useClassNum;
        m_numOfImg = 0;
        trigger      = 0;

        m_transform  = transform;
        assert(m_transform != NULL);

        Alloc();
        CheckClassList();
        CreateImageListOfEachClass();

        LogMessageF("lfw_funneled_label.txt", TRUE, "%d samples\n", this->GetLength());
        CountSamplePerClass();
    }

    virtual ~LFWDataset() {
        Delete();
    }
    virtual void                          Alloc();
    virtual void                          Delete();
    virtual std::vector<Tensor<DTYPE> *>* GetData(int idx);
    virtual void                          CopyData(int idx, DTYPE *pDest);             // copy i-th iamge into pDest. (designed for k-NN)
    std::string& GetImagePath(int idx)   { return m_aImagePath[idx]; }
    int GetSampleCount(int classId)     { return (classId >= 0 && classId < m_vSamplePerClass.size()) ? m_vSamplePerClass[classId] : 0;}
    int GetNoMinorClass(int minCount = 2);
    void Tensor2Image(std::string filename, Tensor<DTYPE> *imgTensor, int doValuerScaling);
};
...
```

- **1-2**:

    `Dataset<DTYPE>` 을 상속받는 클래스 템플릿으로 선언되어 있다.

- **26~32** 

    !!! danger

        멤버 이니셜라이저를 사용하면 성능이 더 좋아지니까 나중에 바꿔야 할 듯하다.

- **32**:

    `vision::Compose * m_transform` 에 `vision::Compose *transform = new vision::Compose({new vision::Resize(224), new vision::CenterCrop(220)});` 을 저장한다.

- **35**:

    `Alloc` 은 다음과 같이 간단히 정의되어 있다.

    ```c++
    template<typename DTYPE> void LFWDataset<DTYPE>::Alloc()  { sem_init(&sem, 0, 1);}
    ```

    `Alloc` 은 단순히 세마포를 초기화해준다.

- **36**:

    `CheckClassList` 는 다음과 같이 정의되어 있다.

    ```c++
    template<typename DTYPE> void LFWDataset<DTYPE>::CheckClassList() {
        // mnt/ssd/Data/ImageNet/synset_words.txt
        std::string filePath = m_rootPath + "/" + m_dataPath + ".txt";
        const char *cstr     = filePath.c_str();
        FILE *pFile = NULL;
        pFile = fopen(cstr, "r");
        ...
            char realValue[100];

            for (int i = 0; i < m_useClasNum; i++) {
                if (fscanf(pFile, "%s", realValue)) {
                    m_className.push_back((std::string)realValue);
                    while (fgetc(pFile) != '\n') ;
                } else {
                    printf("there is something error\n");
                    exit(-1);
                }
            }
        ...
        fclose(pFile);
    }
    ```

    단순히 `std::string filePath = m_rootPath + "/" + m_dataPath + ".txt";` 를 읽어서 한줄씩 `std::vector<std::string> m_className` 벡터에 저장하고 있다.

    !!! danger

        `C` 스타일로 코딩된 것이 많아서 나중에 `C++` 스타일로 고쳐야할 것 같다.

- **37**:

    `CreateImageListOfEachClass()` 는 다음과 같이 정의되어 있다.

    ```c++ linenums="1"
    template<typename DTYPE> void LFWDataset<DTYPE>::CreateImageListOfEachClass() {
        std::vector<int> vTmpLabel;
        vTmpLabel.reserve(2048);

        for (int classNum = 0; classNum < m_useClasNum; classNum++) {
            std::string filePath = m_rootPath + '/' + m_dataPath + '/' + m_className[classNum] + "/list.txt";  // check with printf
            const char *cstr     = filePath.c_str();

            FILE *pFile = NULL;
            pFile = fopen(cstr, "r");

            char realValue[100];
            int  numOfImageOfClass = 0;
            ...
                if (fscanf(pFile, "%s", realValue)) {  // first realValue is already readed above
                    numOfImageOfClass = atoi(realValue);

                    for (int imageNum = 0; imageNum < numOfImageOfClass; imageNum++) {
                        if (fscanf(pFile, "%s", realValue)) {
                            m_aImagePath.push_back((std::string)(m_className[classNum] + '/' + realValue));
                            vTmpLabel.push_back(classNum);
                        } else {
                            printf("there is something error\n");
                            exit(-1);
                        }
                    }
                } else {
                    printf("there is something error\n");
                    exit(-1);
                }
            ...
            fclose(pFile);
        }
        m_numOfImg = m_aImagePath.size();
        this->SetLabel(&vTmpLabel[0], m_numOfImg);
        assert(m_numOfImg > 0);
    }   
    ```

    - **3**:
    
        https://en.cppreference.com/w/cpp/container/vector/reserve 에 `std::vector<T,Allocator>::reserve` 내용이 있는데 비용이 많이 들어가는 메모리 할당을 필요한 만큼 하도록 해서 속도도 높이고, 메모리 효율도 챙기는 좋은 코드인 것 같다.
    
    - **6~10**:

        `std::string filePath = m_rootPath + '/' + m_dataPath + '/' + m_className[classNum] + "/list.txt";` 를 읽어서 `pFile` 로 파일을 연다.
    
    - **12-16**:
        
        `pFile` 의 한줄을 `realValue` 에 저장한다. 이것을 `atoi` 함수로 `int` 로 변환하여 `numOfImageOfClass` 에 저장한다.

    - **18~20**:

        `numOfImageOfClass` 만큼 `for` 문을 돌면서 `pFile` 다음 라인을 `realValue` 에 읽고 `(std::string)(m_className[classNum] + '/' + realValue)` 을 `std::vecotr<std::string> m_aImagePath` 에 저장한다. 

        !!! danger

            하지만 C 스타일 형변환과 C 스타일 에러 처리를 해주고 있기 때문에 C++ 스타일 형변환과 `try-catch` 문으로 바꾸어야 할 것 같다.
        
    - **21**:

        그리고 `std::vector<int> vTmpLabel;` 에 `classNum` 을 저장한다. `classNum` 은 `0` 부터 `m_useClasNum` 까지의 `int` 이다.

    - **34~35**:

        마지막으로 `m_aImagePath` 벡터 사이즈를 갖고 와서 `m_numOfImg` 에 저장하고 `SetLabel` 함수에 `vTmpLabel` 의 주소값과 함께 전달해준다.
    
    이로써 `CreateImageListOfEachClass` 는 이미지 경로와 클래스 라벨을 벡터에 잘 저장해주는 함수라는 것을 알 수 있다.

!!! done "분석 결론"

    `LFWDataset` 은 `std::string filePath = m_rootPath + "/" + m_dataPath + ".txt";` 를 읽어서 클래스 리스트를 `std::vector<std::string> m_className` 에 저장하고,

    `std::string filePath = m_rootPath + '/' + m_dataPath + '/' + m_className[classNum] + "/list.txt";` 를 읽어서 이미지 경로를 `std::vecotr<std::string> m_aImagePath` 에 저장하고,

    `this->SetLabel(&vTmpLabel[0], m_numOfImg);` 을 호출하면서 생성된다.

!!! info "분석 방향"

    이제 `LFWDataset::CopyData` 메소드를 분석해야 한다. 하지만 그 전에 `Dataset::SetLabel` 메소드가 정확히 무엇을 하는지 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [x] `src/Dataset.hpp`: `Dataset` 생성자

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [ ] `src/Dataset.hpp`: `Dataset::SetLabel` 메소드

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/Dataset.hpp`: `Dataset::SetLabel` 메소드

!!! help "분석 목표"

    `this->SetLabel(&vTmpLabel[0], m_numOfImg);` 이해하기

```c++ linenums="1"
template<typename DTYPE> void Dataset<DTYPE>::SetLabel(const unsigned char *pLabel, int noLabel)
{
    try {
        label.resize(noLabel);
    } catch(...){
        printf("Failed to allocate memory (noLabel = %d) in %s (%s %d)\n", noLabel, __FUNCTION__, __FILE__, __LINE__);
        return;
    }

    for(int i = 0; i < noLabel; i++)
        label[i] = (int)pLabel[i];
}
```

- **1**:

    `std::vector<int>` 의 첫번째 원소의 주소값을 `const unsigned char *` 로 받는다. 

    !!! danger
    
        논의가 필요한 코드인 것 같다.

- **4**:

    `std::vector<int> label;` 의 크기를 `noLabel` 로 조정한다.

- **10-11**:

    `std::vector<int> label;` 에 `pLabel[i]` 를 저장한다. 따라서 `0` 부터 `m_useClasNum` 까지의 `int` 가 저장된다.

!!! done "분석 결론"

    `this->SetLabel(&vTmpLabel[0], m_numOfImg);` 는 `std::vector<int> label;` 에 `vTmpLabel` 의 내용을 저장한다.

!!! info "분석 방향"

    이제 `LFWDataset::CopyData` 메소드를 분석해본다. 

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [x] `src/Dataset.hpp`: `Dataset` 생성자

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [x] `src/Dataset.hpp`: `Dataset::SetLabel` 메소드

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

!!! help "분석 목표"

    `dataset.CopyData(batchIdx * BATCH + i, vTestSample[i]);` 로 어떻게 데이터가 `Tensor` 로 변환되어 신경망으로 입력되는지 이해하기

```c++ linenums="1"
template<typename DTYPE> void LFWDataset<DTYPE>::CopyData(int idx, DTYPE *pDest)
{
    Tensor<DTYPE> *image = NULL;
    ImageWrapper imgWrp;

    // image load
    this->AllocImageBuffer(idx, imgWrp);
    m_transform->DoTransform(imgWrp);
    image = this->Image2Tensor(imgWrp, TRUE);
    memcpy(pDest, &(*image)[0], INPUT_DIM * sizeof(DTYPE));

    delete image;
}   
```

- **7**:

    `AllocImageBuffer` 는 다음과 같다.

    ```c++ linenums="1"
    template<typename DTYPE> void LFWDataset<DTYPE>::AllocImageBuffer(int idx, ImageWrapper& imgWrp) {
        int   width, height;
        FILE *jpegFile         = NULL;
        unsigned char *jpegBuf = NULL;
        int pixelFormat        = TJPF_RGB;
        tjhandle tjInstance    = NULL;
        long     size;
        int inSubsamp, inColorspace;
        unsigned long jpegSize;

        // create file address
        std::string filePath = m_rootPath + '/' + m_dataPath + '/' + m_aImagePath[idx];  // check with printf
        const char *cstr     = filePath.c_str();

        // Load image (no throw and catch)
        /* Read the JPEG file into memory. */
        jpegFile = fopen(cstr, "rb");

        fseek(jpegFile, 0, SEEK_END);
        size = ftell(jpegFile);
        fseek(jpegFile, 0, SEEK_SET);

        jpegSize = (unsigned long)size;
        jpegBuf  = (unsigned char *)tjAlloc(jpegSize);

        if (fread(jpegBuf, jpegSize, 1, jpegFile) < 1) exit(-1);

        fclose(jpegFile);
        jpegFile = NULL;

        tjInstance = tjInitDecompress();
        tjDecompressHeader3(tjInstance, jpegBuf, jpegSize, &width, &height, &inSubsamp, &inColorspace);
        imgWrp.imgBuf = (unsigned char *)tjAlloc(width * height * tjPixelSize[pixelFormat]);
        tjDecompress2(tjInstance, jpegBuf, jpegSize, imgWrp.imgBuf, width, 0, height, pixelFormat, 0);

        imgWrp.imgShape = new Shape(tjPixelSize[pixelFormat], height, width);

        tjFree(jpegBuf);
        jpegBuf = NULL;
        tjDestroy(tjInstance);
        tjInstance = NULL;
    }
    ```

    - **12-21**:

        `std::string filePath = m_rootPath + '/' + m_dataPath + '/' + m_aImagePath[idx];  // check with printf` 를 `jpegFile` 로 열고 파일 사이즈를 `size` 에 저장한다.

        !!! danger

            **libjpeg-turbo** 와의 호환성을 유지하면서 C 스타일을 C++ 스타일로 바꾸는 방법에 대한 논의가 필요하다.
    
    - **23-34**:

        **libjpeg-turbo** 를 사용하여 `.jpeg` 파일의 압축을 풀고 `imgWrp.imgBuf` 에 저장한다.

    - **36**:

        그리고 `imgWrp.imgShape` 에 $\text{tjPixelSize[pixelFormat]} \times \text{height } \times \text{width}$ 형상을 `Shape` 로 만들어서 저장한다.
    
    !!! danger

        하지만 이 함수는 이미지를 읽고 압축을 푸는 과정에서 에러처리를 하지 않기 때문에 위험한 코드이다. 
    
        그리고 함수 이름 `AllocImageBuffer` 만 보았을 때는 메모리 공간만 할당할 것 같은데 실제로 `.jpeg` 파일의 압축을 풀고 `Shape` 형상까지 만들어준다. 
    
    어쨌든 결과적으로 이미지를 읽고 압축을 풀어서 `imgWrp.imgBuf` 에 저장하고 `Shape` 클래스로 형상을 만들어서 `imgWrp.imgShape` 에 저장한다.

- **8**:

    압축이 해제된 `.jpeg` 이미지와 그 형상이 저장된 `imgWrp` 을 `vision:Compose::DoTransform` 에 전달한다.

    이것은 `LFW/main.cpp` 의 `main` 함수에서 `vision::Compose *transform = new vision::Compose({new vision::Resize(224), new vision::CenterCrop(220)});` 로 생성된 `Compose` 객체이었다는 것을 기억하자.

- **9**:

    `imgWrp` 을 `LFWDataset<DTYPE>::Image2Tensor(ImageWrapper& imgWrp, int doValueScaling)` 에 전달하고 `Tensor<DTYPE> * image` 에 저장한다. 

    이 코드가 실질적으로 데이터셋을 `Tensor` 로 변환하는 코드인 것 같다.

- **10**:

    `DTYPE * pDest` 에 `(*image)[0]` 의 주소값을 기점으로 `INPUT_DIM * sizeof(DTYPE)` 바이트를 복사한다.

    !!! danger
    
        이 코드의 안정성에 대한 논의가 필요하다. 왜냐하면 `memcpy` 는 내부적으로 포인터 타입을 검증하지 않고 단순히 주어진 바이트 만큼을 주어진 주소값으로 복사할 뿐이기 때문이다.(https://stackoverflow.com/a/19439770/11218888)

!!! done "분석 결론"

    `LFWDataset::CopyData` 메소드는 그 이름과 다르게 
    
    `AllocImageBuffer` 를 통하여 이미지 압축을 해제하여 `imgWrp` 에 저장하고 이미지 형상을 `new Shape(tjPixelSize[pixelFormat], height, width);` 로 만들어서 `imgWrp.imgShape` 에 저장하고,

    `DoTransform` 을 통해 어떤 처리를 해주고, 

    `Image2Tensor` 로 데이터셋을 `Tensor` 로 변환해준다.

!!! danger
    
    필요한 처리들을 생성자 또는 `StartProcess` 에서 해주고 `CopyData` 에서는 데이터 복사 기능만 해야 할 것 같다. 왜냐하면 `CopyData` 메소드가 호출될 때마다 이미지 압축 해제와 데이터 처리, 그리고 `Tensor` 변환이 이루어지는데 만약 한번 이루어졌다면 이후에 불필요한 연산이 끝없이 반복되기 때문이다. 또한 소프트웨어 개발의 표준으로 널리 알려진 [유닉스 철학](https://ko.wikipedia.org/wiki/%EC%9C%A0%EB%8B%89%EC%8A%A4_%EC%B2%A0%ED%95%99) 에 따르면 하나의 함수는 하나의 기능만 해야 하기 때문이다.

!!! info "분석 방향"

    이제 실질적으로 데이터셋을 `Tensor` 로 변환해주는 `LFWDataset<DTYPE>::Image2Tensor` 를 분석해야 한다. 
    
    그런데 그에 앞서 이미지의 형상을 `Shape` 로 만들어서 `imgWrp.imgShape` 에 저장하는 것이 어떤 것인지, 그리고 데이터셋을 `vision:Compose::DoTransform` 에 전달하여 어떤 처리를 해주기 때문에 먼저 이 메소드를 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [x] `src/Dataset.hpp`: `Dataset` 생성자

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [x] `src/Dataset.hpp`: `Dataset::SetLabel` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [ ] `src/Shape.hpp`: `Shape` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `vision::Compose::DoTransform` 메소드

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/Shape.hpp`: `Shape` 생성자

!!! help "분석 목표"

    `imgWrp.imgShape = new Shape(tjPixelSize[pixelFormat], height, width);` 이해하기

먼저 [API](../../api.md) 에 `Shape` 에 대한 설명이 있으므로 이번에는 코드 분석에 앞서 API 의 설명을 살펴본다. API 에 따르면 `Shape` 는 `Tensor` 의 차원정보를 저장하고 있는 객체이다. 그러므로 `imgWrp.imgShape = new Shape(tjPixelSize[pixelFormat], height, width);` 이 데이터셋의 차원정보를 저장한다고 생각할 수 있다.

**API** 에 따르면 `publicShape(int pSize0,int pSize1,int pSize2)` 는 3개의 축의 Dimension을 매개변수로 받아 Shape 클래스를 생성하는 생성자이다. 또 `pSize0` 는 첫 번째 축의 Dimension 크기, `pSize1` 두 번째 축의 Dimension 크기, `pSize2` 세 번째 축의 Dimension 크기이다.

```c++ linenums="1"
class Shape {
private:
    int m_Rank; ///< Shape 클래스를 구성하는 Rank 멤버변수, 텐서를 구성하는 축의 개수
    int *m_aDim; ///< Shape 클래스를 구성하는 Dimension 멤버변수, 각 축의 차원
    Device m_Device; ///< 장치 사용 구분자, CPU 또는 GPU, Device 참고
    int m_idOfDevice; ///< GPU 사용 시, 사용하려는 GPU의 번호. CPU의 경우 -1
#ifdef __CUDNN__
    cudnnTensorDescriptor_t m_desc; ///< cudnn의 Tensor Descriptor, GPU 연산에서 사용하는 Tensor의 shape 정보를 담고 있는 포인터 변수
#endif  // if __CUDNN__
    int  Alloc(int pRank, ...);
    int  Alloc(Shape *pShape);
...
public:
    Shape(int pSize0, int pSize1, int pSize2, int pSize3, int pSize4);
    Shape(int pSize0, int pSize1, int pSize2, int pSize3);
    Shape(int pSize0, int pSize1, int pSize2);
    Shape(int pSize0, int pSize1);
    Shape(int pSize0);
    Shape(Shape *pShape);  // Copy Constructor
    virtual ~Shape();
    int                      GetRank();
    int                      GetDim(int pRanknum);
    int                    & operator[](int pRanknum); // operator[] overload
...
};
```

- **16**:

    지금 분석 목표가 `imgWrp.imgShape = new Shape(tjPixelSize[pixelFormat], height, width);` 를 이해하는 것이므로 이 생성자를 분석해야 한다.

```c++ linenums="1"
Shape::Shape(int pSize0, int pSize1, int pSize2) {
    m_Rank       = 0;
    m_aDim       = NULL;
    m_idOfDevice = -1;
#ifdef __CUDNN__
    m_desc = NULL;
#endif  // if __CUDNN__

    Alloc(3, pSize0, pSize1, pSize2);
}
```

- **2-4**:

    멤버 이니셜라이저를 사용하면 좋을 것 같다. 

- **9**:

    `Alloc` 메소드는 다음과 같다.

    ```c++ linenums="1"
    int Shape::Alloc(int pRank, ...) {
        try {
            if (pRank > 0) m_Rank = pRank;
            else throw pRank;
        } catch (int e) {
            printf("Receive invalid rank value %d in %s (%s %d)\n", e, __FUNCTION__, __FILE__, __LINE__);
            return FALSE;
        }

        try {
            m_aDim = new int[m_Rank];
        } catch (...) {
            printf("Failed to allcate memory in %s (%s %d)\n", __FUNCTION__, __FILE__, __LINE__);
            return FALSE;
        }

        va_list ap;
        va_start(ap, pRank);

        // need to check compare between pRank value and number of another parameter
        for (int i = 0; i < pRank; i++) {
            // need to check whether int or not
            m_aDim[i] = va_arg(ap, int);
        }
        va_end(ap);
        m_Device = CPU;
        return TRUE;
    }
    ```

    - **2-15**:

        !!! danger

            `try-catch` 문을 통일하면 코드를 축약시킬 수 있다.

        어쨌든 `m_Rank = 3` 으로 `int * m_aDim = new int[3]` 으로 초기화한다.
    
    - **17-25**:

        가변인자를 가져와서 `int * m_aDim` 에 저장한다. 가변인자는 `tjPixelSize[pixelFormat], height, width` 이므로 이 값들이 `m_aDim[i]` 에 각각 저장된다.

        !!! danger

            가변인자를 사용하기 위해서는 `C` 에서 `#include <stdarg.h>` 가 선언되어야 한다. 하지만 `C++` 에서는 호환성을 위하여 `#include <cstdarg>` 이 선언되어야만 한다. 이 선언은 `src/Common.h` 에 선언되어 있는데 이곳에는 대량의 `C` 언어의 헤더 선언문 `#include <....h>` 가 선언되어 있었다. 모두 다 `C++` 스타일 헤더 선언으로 바꿀 필요가 있다.

!!! done "분석 결론"

    `Shape` 는 데이터셋의 차원정보를 `int * m_aDim` 에 저장고, 축의 개수를 `m_Rank` 에 저장한다. 그러므로 `imgWrp.imgShape = new Shape(tjPixelSize[pixelFormat], height, width);` 는 데이터셋의 차원정보를 `Shape` 객체로 생성하여 `imgWrp.imgShape` 에 저장한다.

!!! info "분석 방향"

    이제 `vision:Compose::DoTransform` 을 분석하여 데이터셋에 어떤 처리를 해주는지 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [x] `src/Dataset.hpp`: `Dataset` 생성자

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [x] `src/Dataset.hpp`: `Dataset::SetLabel` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [x] `src/Shape.hpp`: `Shape` 생성자

    - [ ] `LFW/ImageProcess.hpp`: `vision::Compose::DoTransform` 메소드

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/ImageProcess.hpp`: `vision::Compose::DoTransform` 메소드

!!! help "분석 목표"

    `m_transform->DoTransform(imgWrp);` 로 데이터셋이 어떻게 처리되는지 이해하기

```c++ linenums="1"
class Compose : public Transform {
private:
    std::vector<Transform *> m_listOfTransform;
    int m_size;
...
    virtual void DoTransform(ImageWrapper& imgWrp) {
        for (int i = 0; i < m_size; i++) {
            m_listOfTransform[i]->DoTransform(imgWrp);
        }
    }
};
```

- **5**:

    `std::vector<Transform *> m_listOfTransform;` 의 원소들의 `DoTransform` 메소드를 `imgWrp` 을 입력하여 호출한다.

    `m_listOfTransform` 는 `{new vision::Resize(224), new vision::CenterCrop(220)}` 로 초기화되었으므로 `vision::Resize::DoTransform` 과 `vision::CenterCrop::DoTransform` 이 호출될 것이다.

!!! done "분석 결론"

    `vision::Compose::DoTransform` 메소드는 `m_listOfTransform` 의 `DoTransform` 메소드에 `imgWrp` 을 입력하며 호출해준다.

    `m_listOfTransform` 는 `{new vision::Resize(224), new vision::CenterCrop(220)}` 로 초기화되었으므로 `vision::Resize::DoTransform` 과 `vision::CenterCrop::DoTransform` 이 호출된다.

!!! info "분석 방향"

    `vision::Resize::DoTransform` 과 `vision::CenterCrop::DoTransform` 가 데이터셋에 어떤 처리를 하는지 분석해본다.

!!! tldr "분석 지도"

    - [x] `LFW/main.cpp`: `main` 함수

    - [x] `LFW/ImageProcess.hpp`: `Transform` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Resize` 생성자

    - [x] `LFW/ImageProcess.hpp`: `CenterCrop` 생성자

    - [x] `LFW/ImageProcess.hpp`: `Compose` 생성자

    - [x] `src/Dataset.hpp`: `Dataset` 생성자

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset` 생성자

    - [x] `src/Dataset.hpp`: `Dataset::SetLabel` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::CopyData` 메소드

    - [x] `src/Shape.hpp`: `Shape` 생성자

    - [x] `LFW/ImageProcess.hpp`: `vision::Compose::DoTransform` 메소드

    - [ ] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [ ] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드
