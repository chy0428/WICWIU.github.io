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

    `Dataset` 객체는 구현되어 있지 않은 추상 클래스이다. 그런데 `Dataset` 추상 클래스에 있으면 안되는 메소드들이 있는 것 같다.

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

    이 코드의 안정성에 대한 논의가 필요하다. 왜냐하면 `memcpy` 는 내부적으로 포인터 타입을 검증하지 않고 단순히 주어진 바이트 만큼을 주어진 주소값으로 복사할 뿐이기 때문이다.(https://stackoverflow.com/a/19439770/11218888)

!!! done "분석 결론"

    `LFWDataset::CopyData` 메소드는 그 이름과 다르게 
    
    `AllocImageBuffer` 를 통하여 이미지 압축을 해제하여 `imgWrp` 에 저장하고 이미지 형상을 `new Shape(tjPixelSize[pixelFormat], height, width);` 로 만들어서 `imgWrp.imgShape` 에 저장하고,

    `DoTransform` 을 통해 어떤 처리를 해주고, 

    `Image2Tensor` 로 데이터셋을 `Tensor` 로 변환해준다.

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
    int m_Rank;
    ///< Shape 클래스를 구성하는 Rank 멤버변수, 텐서를 구성하는 축의 개수
    int *m_aDim;
    ///< Shape 클래스를 구성하는 Dimension 멤버변수, 각 축의 차원
    Device m_Device;
    ///< 장치 사용 구분자, CPU 또는 GPU, Device 참고
    int m_idOfDevice;
    ///< GPU 사용 시, 사용하려는 GPU의 번호. CPU의 경우 -1

#ifdef __CUDNN__
    cudnnTensorDescriptor_t m_desc;
    ///< cudnn의 Tensor Descriptor, GPU 연산에서 사용하는 Tensor의 shape 정보를 담고 있는 포인터 변수
#endif  // if __CUDNN__

private:
    int  Alloc(int pRank, ...);
    int  Alloc(Shape *pShape);
    void Delete();

#ifdef __CUDNN__
    int  AllocOnGPU(unsigned int idOfDevice);
    void DeleteOnGPU();
    int  ReShapeOnGPU();
#endif  // if __CUDNN__

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
    Device                   GetDevice();
    int                      GetDeviceID();

    int                      ReShape(int pSize0, int pSize1, int pSize2, int pSize3, int pSize4);
    int                      ReShape(int pRank, ...);


    int                      SetDeviceCPU();
#ifdef __CUDNN__
    int                      SetDeviceGPU(unsigned int idOfDevice);
    cudnnTensorDescriptor_t& GetDescriptor();
#endif  // __CUDNN__
};
```

- **31**:

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

## `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

!!! help "분석 목표"

    `m_transform->DoTransform(imgWrp);` 로 데이터셋이 어떻게 처리되는지 이해하기

```c++ linenums="1"
class Resize : public Transform {
...
public:
...
    virtual void DoTransform(ImageWrapper& imgWrp) {
        unsigned char *oldImgBuf = imgWrp.imgBuf;
        Shape *oldImgShape       = imgWrp.imgShape;

        int oldWidth  = oldImgShape->GetDim(2);
        int oldHeight = oldImgShape->GetDim(1);
        int channel   = oldImgShape->GetDim(0);

        unsigned char *newImgBuf = new unsigned char[newWidth * newHeight * channel];
        Shape *NewImgShape       = new Shape(channel, newHeight, newWidth);


        for (int newy = 0; newy < newHeight; newy++) {
            int oldy = newy * oldHeight / newHeight;

            for (int newx = 0; newx < newWidth; newx++) {
                int oldx = newx * oldWidth / newWidth;

                for (int c = 0; c < channel; c++) {
                    newImgBuf[newy * newWidth * channel + newx * channel + c]
                        = oldImgBuf[oldy * oldWidth * channel + oldx * channel + c];
                }
            }
        }

        delete[] oldImgBuf;
        oldImgBuf = NULL;
        delete oldImgShape;
        oldImgShape = NULL;

        imgWrp.imgBuf   = newImgBuf;
        imgWrp.imgShape = NewImgShape;
    }
};
```

- **13-14**:

    `newWidth` 와 `newHeight` 로 새로운 이미지 버퍼를 만들고 새로운 `Shape` 를 만든다.

    객체가 `new vision::Resize(224)` 로 생성되었었기에 `newWidth` 와 `newHeight` 에는 `224` 가 저장되어 있다.

- **17-28**:

    이전 이미지 버퍼에 어떤 처리를 해줌과 동시에 새로운 이미지 버퍼를 만든다.

    하지만 주석도 없고 API 도 없을 뿐더러 지금의 목표는 데이터셋을 `Tensro` 로 변환하는 것이므로 그 처리를 정확히 이해하는 것은 지금은 불필요하다. 따라서 자세히 분석하지는 않는다.

- **35-36**:

    새로운 차원과 이미지 버퍼를 `imgWrp` 에 저장한다.

!!! done "분석 결론"

    `m_transform->DoTransform(imgWrp);` 은 데이터셋에 어떤 처리를 해주고 다시 데이터셋에 저장한다. 그러므로 데이터셋을 `Tensor` 를 변환하는 직접적인 코드는 아니다.

!!! info "분석 방향"

    `vision::CenterCrop::DoTransform` 가 데이터셋에 어떤 처리를 하는지 분석해본다.

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [ ] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

!!! help "분석 목표"

    `m_transform->DoTransform(imgWrp);` 로 데이터셋이 어떻게 처리되는지 이해하기

```c++ linenums="1"
class CenterCrop : public Transform {
...
public:
...
    virtual void DoTransform(ImageWrapper& imgWrp) {
        unsigned char *imgBuf = imgWrp.imgBuf;
        Shape *imgShape       = imgWrp.imgShape;

        int width = imgShape->GetDim(2);
        // assert(height >= m_heigth);
        int channel = imgShape->GetDim(0);

        unsigned char *newImgBuf = new unsigned char[m_width * m_heigth * channel];
        Shape *NewImgShape       = new Shape(channel, m_heigth, m_width);

        int start_h = (height - m_heigth) / 2;
        int start_w = (width - m_width) / 2;

        for (int h = 0; h < m_heigth; h++) {
            int oldh = start_h + h;
            for (int w = 0; w < m_width; w++) {
                int oldw = start_w + w;
                for (int ch = 0; ch < channel; ch++) {
                    newImgBuf[h * m_width * channel + w * channel + ch]
                        = imgBuf[oldh * width * channel + oldw * channel + ch];
                }
            }
        }

        delete[] imgBuf;
        imgBuf = NULL;
        delete imgShape;
        imgShape = NULL;

        imgWrp.imgBuf   = newImgBuf;
        imgWrp.imgShape = NewImgShape;
    }
};
```

- **13-37**:

    이전 이미지 버퍼에 어떤 처리를 해줌과 동시에 새로운 이미지 버퍼를 만든다. 그리고 새로운 차원과 이미지 버퍼를 `imgWrp` 에 저장한다.

    하지만 주석도 없고 API 도 없을 뿐더러 지금의 목표는 데이터셋을 `Tensro` 로 변환하는 것이므로 그 처리를 정확히 이해하는 것은 지금은 불필요하다. 따라서 자세히 분석하지는 않는다.

!!! done "분석 결론"

    `m_transform->DoTransform(imgWrp);` 은 데이터셋에 어떤 처리를 해주고 다시 데이터셋에 저장한다. 그러므로 데이터셋을 `Tensor` 를 변환하는 직접적인 코드는 아니다.

!!! info "분석 방향"

    이제 실질적으로 데이터셋을 `Tensor` 로 변환해주는 `LFWDataset<DTYPE>::Image2Tensor` 를 분석해본다.

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [x] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [ ] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

!!! help "분석 목표"

    `Tensor<DTYPE> * image = this->Image2Tensor(imgWrp, TRUE);` 로 데이터셋을 어떻게 `Tensor` 로 변환하는지 이해하기

```c++ linenums="1"
template<typename DTYPE> Tensor<DTYPE> *LFWDataset<DTYPE>::Image2Tensor(ImageWrapper& imgWrp, int doValueScaling) {
    unsigned char *imgBuf = imgWrp.imgBuf;
    Shape *imgShape       = imgWrp.imgShape;

    int width   = imgShape->GetDim(2);
    int height  = imgShape->GetDim(1);
    int channel = imgShape->GetDim(0);

    Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);

    if (doValueScaling) {
        for (int ro = 0; ro < height; ro++) {
            for (int co = 0; co < width; co++) {
                for (int ch = 0; ch < channel; ch++) {
                    (*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)] = imgBuf[ro * width * channel + co * channel + ch] / 255.0;
                }
            }
        }
    } else {
        for (int ro = 0; ro < height; ro++) {
            for (int co = 0; co < width; co++) {
                for (int ch = 0; ch < channel; ch++) {
                    (*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)] = imgBuf[ro * width * channel + co * channel + ch];
                }
            }
        }
    }

    return result;
}
```

- **1-11**:

    `imgWrp` 참조자와 `doValueScaling` 을 인자로 받는다. 
    
    !!! danger 
    
        `doValuerScaling` 은 `true` 와 `falst` 를 구분하는 용도로 쓰이기 때문에 `4` 바이트나 되는 `int` 타입이 아닌 `1` 바이트 `bool` 타입에 저장하는 것이 좋아 보인다.

- **5-7**:

    차원 정보를 가져온다.

- **9**:

    `Tensor::Zeros` 에 차원정보를 전달하여 `Tensor` 객체를 생성한다.

    !!! danger 

        그런데 **LFW** 데이터셋은 `.jpeg` 파일로써 실제로는 `3` 차원 텐저($\text{RGB} \times \text{width} \times \text{height}$) 로 되어 있다. 그런데도 왜 굳이 불필요한 연산이 추가되는 `5` 차원 텐저를 사용했는지 모르겠다.

- **12-15**:

    `doValuerScaling` 이 `TRUE` 이므로 이 코드가 실행된다.

    `imgBuf` 의 `ro * width * channel + co * channel + ch` 인덱스를 참조하여 `255.0` 로 나눈다. 단지 $1$ 차원 배열에 저장되어 있는 $3$ 차원 데이터를 참조하는 방식으로 보인다.

    이것은 **libjpeg-turbo** 가 압축 해제한 데이터셋이므로 $3$ 차원 데이터셋인 이미지의 실제 데이터를 참조할 때 왜 `ro * width * channel + co * channel + ch` 로 참조하는지는 **libjpeg-turbo** 를 참조해야 할 것 같다. 이는 만약 다른 라이브러리로(가령 `CImg`) 데이터셋을 $1$ 차원 배열로 만들고 그것을 다시 `Tensor` 로 변환한다면 또 다른 방식으로 $1$ 차원 배열의 인덱스를 참조해야 한다는 것을 의미한다.

    !!! danger

        `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 하지만 이렇게 하면 데이터 참조 과정이 번거롭고 불필요한 과정이 되지 않나 싶다.

        왜냐하면 `Index5D` 메소드를 `Tensor` 클래스 내부에서 처리할 수 있기 때문이다. 그렇게 한다면 사용자의 편의를 높일 수 있다.

    !!! danger

        한편 `imgBuf` 는 `unsigned char` 형 배열인데 이것을 명시적 형변환 없이 `double` 형으로 나누고 있으므로 이 코드는 [암시적 형변환](https://ko.wikipedia.org/wiki/%ED%98%95_%EB%B3%80%ED%99%98) 을 일으킨다. 암시적 형변환은 프로젝트의 안정성과 신뢰성을 파괴하는 주된 원인 중 하나이므로 고칠 필요가 있어 보인다.

    어쨌든 `255.0` 로 나눔으로써 데이터를 스케일링한 후 `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 에 저장한다.

!!! done "분석 결론"

    `Tensor<DTYPE> * image = this->Image2Tensor(imgWrp, TRUE);` 은 
    
    `Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);` 를 만들고

    $3$차원 데이터셋의 원소 하나 하나를 가져와서 `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 에 저장한다.

!!! info "분석 방향"

    `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 가 어떤 코드인지 이해해야 한다.

    하지만 그 전에 `Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);` 로써 `Tensor::Zeros` 메소드로 `Tensor` 객체를 생성하였으므로 이것부터 분석해본다.

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [x] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [ ] `src/Tensor.hpp`: `Tensor::Zeros` 메소드

    - [ ] `src/Tensor.hpp`: `Tensor::operator[]` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/Tensor.hpp`: `Tensor::Zeros` 메소드

!!! help "분석 목표"

    `Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);` 로써 `Tensor` 객체를 생성하는 과정 이해하기

```c++ linenums="1"
enum IsUseTime {
    UseTime,
    NoUseTime
};
...
template<typename DTYPE> class Tensor {
private:
    Shape *m_aShape; ///< Tensor를 구성하는 Shape 클래스, 텐서의 차원을 정의
    LongArray<DTYPE> *m_aLongArray; ///< Tensor를 구성하는 LongArray 클래스, 텐서의 원소들의 값을 저장
...
    IsUseTime m_IsUseTime; ///< time 축 사용 유무, IsUseTime 참고
    int  Alloc(Shape *pShape, IsUseTime pAnswer);
...
public:
    Tensor(int pSize0, int pSize1, int pSize2, int pSize3, int pSize4, IsUseTime pAnswer = UseTime);  // For 5D-Tensor
...
    Tensor(Shape *pShape, IsUseTime pAnswer = UseTime);
...
    static Tensor<DTYPE>* Zeros(int pSize0, int pSize1, int pSize2, int pSize3, int pSize4, IsUseTime pAnswer = UseTime);
    static Tensor<DTYPE>* Zeros(Shape *pShape, IsUseTime pAnswer = UseTime);
...
};
```

- **22**:

    `Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);` 는 이 메소드를 호출한다. 
    
    객체가 생성되기 전에 호출되어야 하므로 `static` 으로 정의되어 있다. 또한 `IsUseTime pAnswer = UseTime` 의 디폴트 파라미터를 사용한다.

```c++ linenums="1"
template<typename DTYPE> Tensor<DTYPE> *Tensor<DTYPE>::Zeros(int pSize0, int pSize1, int pSize2, int pSize3, int pSize4, IsUseTime pAnswer) {
    return Tensor<DTYPE>::Zeros(new Shape(pSize0, pSize1, pSize2, pSize3, pSize4), pAnswer);
}
```

- **2**:

    파라미터 `(1, 1, channel, height, width)` 를 받아서 오버로딩된 `Tensor::Zeros` 를 호출한다.

```c++ linenums="1"
template<typename DTYPE> Tensor<DTYPE> *Tensor<DTYPE>::Zeros(Shape *pShape, IsUseTime pAnswer) {
    return new Tensor<DTYPE>(pShape, pAnswer);
}
```

- **2**:

    파라미터 `new Shape(pSize0, pSize1, pSize2, pSize3, pSize4), pAnswer` 를 받아서 생성자를 호출한다. 

    !!! danger
    
        이럴거면 `Tensor<DTYPE>::Zeros(int pSize0, int pSize1, int pSize2, int pSize3, int pSize4, IsUseTime pAnswer)` 에서 바로 생성자를 호출하는 것이 더 빠를 것이다.

```c++ linenums="1"
template<typename DTYPE> Tensor<DTYPE>::Tensor(Shape *pShape, IsUseTime pAnswer) {
    m_aShape     = NULL;
    m_aLongArray = NULL;
    m_Device     = CPU;
    m_idOfDevice = -1;
    Alloc(pShape, pAnswer);
}
```

- **2-5**:

    멤버 변수를 초기화해준다. 

    !!! danger
    
        멤버 이니셜라이저를 쓰면 더 나은 성능을 기대할 수 있을 것 같다. 

- **6**:

    파라미터를 그대로 `Tensor::Alloc` 메소드로 전달한다.

```c++ linenums="1"
template<typename DTYPE> int Tensor<DTYPE>::Alloc(Shape *pShape, IsUseTime pAnswer) {
    if (pShape == NULL) {
        printf("Receive NULL pointer of Shape class in %s (%s %d)\n", __FUNCTION__, __FILE__, __LINE__);
        return FALSE;
    } else {
        m_aShape    = pShape;
        m_IsUseTime = pAnswer;

        int rank = pShape->GetRank();

        int pTime            = 1;
        int pCapacityPerTime = 1;

        if (m_IsUseTime == UseTime) {
            pTime = (*pShape)[0];

            for (int i = 1; i < rank; i++) {
                pCapacityPerTime *= (*pShape)[i];
            }
        } else if (m_IsUseTime == NoUseTime) {
            for (int i = 0; i < rank; i++) {
                pCapacityPerTime *= (*pShape)[i];
            }
        } else return FALSE;

        m_aLongArray = new LongArray<DTYPE>(pTime, pCapacityPerTime);
    }
    m_Device = CPU;
    return TRUE;
}
```

- **2-5**:

    !!! danger

        에러를 처리해주는데 `C++` 프로젝트이므로 `try-catch` 문을 사용하면 더 나은 성능과 가독성을 기대할 수 있다.

        또한 `printf` 는 표준출력인데 에러 처리 메시지이므로 표준에러스트림으로 메시지를 출력하면 에러 로그를 분류할 수 있다. 가령 `fprintf(stderr, ...)` 이나 `std::cerr << ...` 로 표준에러스트림으로 메시지를 출력하는 것이다.

- **6-7**:

    !!! danger

        멤버변수를 초기화하는데 멤버 이니셜라이저를 사용하면 더 나은 성능을 기대할 수 있다.

- **14-24**:

    !!! danger

        에러를 처리해주는데 `C++` 프로젝트이므로 `try-catch` 문을 사용하면 더 나은 성능과 가독성을 기대할 수 있다.

- **15-19**:

    `pAnswer = UseTime` 이므로 이 코드가 실행된다.

- **15**:

    `Shape::operator[]` 에 `0` 을 전달하여 `pTime` 을 초기화한다. `Shape::operator[]` 는 다음과 같다.

    ```c++ linenums="1"
    int& Shape::operator[](int pRanknum) {
        try {
            if (pRanknum >= 0) return m_aDim[pRanknum];
            else throw;
        }
        catch (...) {
            printf("Receive invalid pRanknum value in %s (%s %d)\n", __FUNCTION__, __FILE__, __LINE__);
            exit(0);
            // return FALSE;
        }
    }
    ```

    - **3**:

        단순히 `int * m_aDim` 를 `pRanknum` 인덱스로 참조하여 반환한다.
    
    - **6-8**:

        !!! danger

            에러 처리를 `try-catch` 로 했지만 에러 메시지를 표준출력스트림으로 보내고 있기 때문에 에러메시지 수집이 어려워 프로젝트 신뢰성과 편의성이 떨어진다. 
            
            또한 에러코드를 반환하는 것이 아니라 `exit(0)` 으로 프로그램을 강제로 종료해버리므로 사용자가 에러를 핸들링할 수 있는 기회가 박탈당할 수 있다. 
    
    그러므로 이 코드는 데이터셋의 `0` 번째 축의 크기를 `pTime` 에 저장하는 것이다.

- **18**:

    `Shape` 에 `operator[]` 로 `i` 인덱스를 가져와서 `pCapacityPerTime` 에 누적으로 곱해준다. 

    그러므로 이 코드는 데이터셋의 `1` 번째 축의 크기부터 마지막 축의 크기까지 `pCapacityPerTime` 에 저장하고 있다.

- **26**:

    `pTime`(`0`번째 축) 과 `pCapacityPerTime`(`1`번째 축부터 마지막 축의 크기까지의 곱) 으로 `LongArray` 를 만들고 `m_aLongArray` 에 저장한다.

- **29**:

    !!! danger

        메소드가 성공적으로 끝났을 때 `TRUE` 를 반환하는데 `4` 바이트 `int` 형이 아니라 `1` 바이트 `bool` 형 `true` 를 사용하면 메모리 효율을 높일 수 있어 보인다.

!!! done "분석 결론"

    `Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);` 는 파라미터를 받아서 자동으로 `Shape` 를 생성해준 다음 필요한 멤버 변수들을 초기화시키고 `LongArray` 를 만들어서 `LongArray<DTYPE> * m_aLongArray` 에 저장한다.

    그런데 `Tensor::Zeros` 가 텐저값들을 $0$ 으로 초기화해주는 메소드라고 했는데 어디에서 $0$ 으로 초기화되었는지 보이지 아직 않는다.

!!! info "분석 방향"

    `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 가 어떤 코드인지 분석하기 위하여 `Tensor::operator[]` 를 분석해본다.

    그런데 `Index5D` 가 `Tensor::operator[]` 에 인자로 전달되었으므로 `Index5D` 부터 분석해본다.

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [x] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::Zeros` 메소드

    - [ ] `src/Tensor.hpp`: `Index5D` 함수

    - [ ] `src/Tensor.hpp`: `Tensor::operator[]` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/Tensor.hpp`: `Index5D` 함수

!!! help "분석 목표"

    `Index5D(result->GetShape(), 0, 0, ch, ro, co)` 가 어떤 코드인지 이해하기

주석에 따르면 `Index5D` 는 5차원으로 정의된 `Tensor` 의 `LongArray` 에 접근하기 위한 인덱스를 계산하는 메소드이다. 즉 `Index5D` 는 5차원으로 정의된 `Tensor` 에 대해, `pShape` 과 각 축의 인덱스를 매개변수로 받아 이에 대응되는 `LongArray` 의 원소에 접근하기 위한 인덱스 번호를 계산하여 반환한다.

```c++ linenums="1"
inline unsigned int Index5D(Shape *pShape, int ti, int ba, int ch, int ro, int co) {
    return (((ti * (*pShape)[1] + ba) * (*pShape)[2] + ch) * (*pShape)[3] + ro) * (*pShape)[4] + co;
}
```

- **2**:

    이 코드를 이해하기 위하여 가장 단순한 형태의 `Index2D` 함수를 살펴보면 다음과 같다.

    ```c++ linenums="1"
    inline unsigned int Index2D(Shape *pShape, int ro, int co) {
        return ro * (*pShape)[1] + co;
    }   
    ```

    이것은 `2` 차원 배열을 `1` 차원 배열로 만든 것을 참조하기 위한 코드이다. 다음은 $(n+1) \times 8$ 형상의 행렬을 `1` 차원 배열로 만든 것이다.

    ![image](https://user-images.githubusercontent.com/16812446/89537962-f5aee400-d834-11ea-8121-c6ab875f594f.png)

    위 그림을 보면 `2` 차원 배열이 `1` 차원 배열로 변환되었다는 것을 알 수 있다. 각각의 인덱스는 `2` 차원 배열일 때 $(0,0)$ 부터 $(n, 7)$ 까지 였다.

    하지만 `1` 차원 배열로 변환되었으므로 인덱스를 $i \in \{0, 1, \dots, n\}, j \in \{0, 1, \dots, 7\}$ 인 $i, j$ 에 대하여 $i \times 8 + j$ 로 참조해야 한다.

    이것을 일반화하면 $n \in \mathbb{N}, m \in \mathbb{N}$ 에 대한 $n \times m$ 행렬을 $1 \times nm$ 배열로 변환하여 인덱스를 참조하기 위해서는 $i \in \{0, 1, \dots, n-1\}, j \in \{0, 1, \dots, m-1\}$ 인 $i, j$ 에 대하여 $i \times m + j$ 로 참조해야 한다는 것을 귀납적으로 알 수 있다. 이것을 코드로 변환하면 위와 같은 `Index2D` 함수가 되는 것이다. 

    !!! note 

        연역적인 증명은 생략한다.

    마찬가지로 `3` 차원 배열을 `1` 차원 배열로 변환하여 저장한 다음 인덱스를 참조하기 위한 `Index3D` 함수는 다음과 같다. 

    ```c++ linenums="1"
    inline unsigned int Index3D(Shape *pShape, int ch, int ro, int co) {
        return (ch * (*pShape)[1] + ro) * (*pShape)[2] + co;
    }   
    ```

    이것은 `3` 차원 배열을 `1` 차원 배열로 만든 것을 참조하기 위한 코드이다. 다음은 $(n+1) \times 3 \times 4$ 형상의 텐저를 `1` 차원 배열로 변환한 것이다.

    ![image](https://user-images.githubusercontent.com/16812446/89540506-13ca1380-d838-11ea-9b67-5873353f30ef.png)

    이 텐저의 인덱스는 $(0, 0, 0)$ 부터 $(n,2,3)$ 까지였다. 하지만 `1` 차원 배열로 변환되었으므로 인덱스를 $i \in \{0, 1, \dots, n\}, j \in \{0, 1, 2\}, k \in \{0,1,2,3\}$ 에 대하여 $i \times 3 \times 4 + j \times 4 + k = (i \times 3 + j) \times 4 + k$ 로 참조해야 한다.

    이것을 일반화하면 $t_1 \in \mathbb{N}, t_2 \in \mathbb{N}, t_3 \in \mathbb{N}$ 에 대한 $t_1 \times t_2 \times t_3$ 텐저를 $1 \times t_1t_2t_3$ 배열로 변환하여 인덱스를 참조하기 위해서는 $i \in \{0, 1, \dots, t_1-1\}, j \in \{0, 1, \dots, t_2-1\}, k \in \{0, 1, \dots, t_3-1\}$ 인 $i, j, k$ 에 대하여 $it_2t_3 + jt_3 + k = (it_2 + j)t_3 + k$ 로 참조해야 한다는 것을 귀납적으로 알 수 있다. 이것을 코드로 변환하면 위와 같은 `Index3D` 함수가 된다.

    그렇다면 마찬가지로 $t_1 \in \mathbb{N}, t_2 \in \mathbb{N}, t_3 \in \mathbb{N}, t_4 \in \mathbb{N}, t_5 \in \mathbb{N}$ 에 대한 $t_1 \times t_2 \times t_3 \times t_4 \times t_5$ 텐저를 $1 \times t_1t_2t_3t_4t_5$ 배열로 변환하여 인덱스를 참조하기 위해서는 
    
    $$i_1 \in \{0, 1, \dots, t_1-1\}$$ 
    
    $$i_2 \in \{0, 1, \dots, t_2-1\}$$ 
    
    $$i_3 \in \{0, 1, \dots, t_3-1\}$$ 

    $$i_4 \in \{0,1,\dots,t_4-1\}$$ 

    $$i_5 \in \{0, 1, \dots, t_5-1\}$$ 

    인 $i_1, i_2, i_3, i_4, i_5$ 에 대하여 
    
    $$i_1t_5t_4t_3t_2+i_2t_5t_4t_3+i_3t_5t_4+i_2t_5+i_5 = (((i_1t_2+i_2)t_3+i_3)t_4+i_2)t_5 + i_5$$
    
    로 참조해야 한다는 것을 귀납적으로 알 수 있다. 이것을 코드로 변환하면 위와 같은 `Index5D` 함수가 된다.

    !!! bug

        그런데 이에 따르면 `LFWDataset::Image2Tensor` 메소드의 다음의 코드는 좀 이상하다.

        ```c++ linenums="1"
        Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);
        ...
            for (int ro = 0; ro < height; ro++) {
                for (int co = 0; co < width; co++) {
                    for (int ch = 0; ch < channel; ch++) {
                        (*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)] = imgBuf[ro * width * channel + co * channel + ch] / 255.0;       
        ...
        ```

        왜냐하면 `Tensor` 의 형상을 정해줄 때 $\text{channel} \times \text{height} \times \text{width}$ 로 정해줬는데도 `Tensor` 에 `3` 차원 텐저가 `1` 차원 배열로 저장된 `imgBuf` 의 원소를 저장할 때 

        ```c++ 
        ch * height * width + ro * width + co
        ```

        로 인덱스를 참조하여 저장하는 것이 아니라 

        ```c++ 
        ro * width * channel + co * channel + ch
        ```

        로 인덱스를 참조하여 바이트들을 저장하기 때문이다. 만약 `ro * width * channel + co * channel + ch` 대로 데이터를 저장한다면 `1` 차원 배열 `imgBuf` 가 원래는 `3` 차원 텐저 $\text{height} \times \text{width} \times \text{channel}$ 였다는 의미이기 때문이다. 정말 그렇다면 형상을 `Tensor<DTYPE>::Zeros(1, 1, height, width, channel);` 로 정해주었어야 한다.

        내가 잘못 판단한 것일 수도 있기 때문에 논의가 필요하다.

        

!!! done "분석 결론"

    `Index5D` 는 `Shape` 와 데이터셋 각 축의 인덱스가 전달되면 그것에 대응되는 `LongArray` 의 원소의 인덱스를 반환해준다.

!!! info "분석 방향"

    `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 가 어떤 코드인지 분석하기 위하여 `Tensor::operator[]` 를 분석해야 한다.

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [x] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::Zeros` 메소드

    - [x] `src/Tensor.hpp`: `Index5D` 함수

    - [ ] `src/Tensor.hpp`: `Tensor::operator[]` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/Tensor.hpp`: `Tensor::operator[]` 메소드

!!! help "분석 목표"

    `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 가 어떤 코드인지 이해하기

```c++ linenums="1"
template<typename DTYPE> class Tensor {
...
    DTYPE                  & operator[](unsigned int index);
...
};
```

- **3**:

    `[]` 연산자는 `Tensor` 클래스에서 이렇게 오버로딩 되어 있다. 메소드의 구현은 다음과 같다.

```c++ linenums="1"
template<typename DTYPE> DTYPE& Tensor<DTYPE>::operator[](unsigned int index) {
    #ifdef __CUDNN__
    if (m_Device == GPU) {
        this->SetDeviceCPU();
    }
    #endif  // __CUDNN__
    return (*m_aLongArray)[index];
}
```

- **2-3**:

    !!! danger

        어차피 `if (m_Device == GPU)` 로 **GPU** 인지 검증해주는데 왜 `#ifdef __CUDNN__` 가 필요한지 모르겠다.

- **7**:
    
    `LongArray<DTYPE> * m_aLongArray` 의 `operator[]` 에 `index` 를 전달해주고 반환한다.

!!! done "분석 결론"

    `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 를 이해해보려 했는데 `Tensor::operator[]` 메소드가 인덱스를 그저 `LongArray::operator[]` 로 전달해준다.


!!! info "분석 방향"

    `LongArray::operator[]` 을 분석함으로써 `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 를 이해해야 한다. 

    그런데 `LongArray::operator[]` 을 분석하려면 먼저 `LongArray` 객체의 생성을 이해해야 한다.

    `LongArray` 객체는 `Tensor::Zeros` 메소드 분석 과정에서 `pTime`(`0`번째 축) 과 `pCapacityPerTime`(`1`번째 축부터 마지막 축의 크기까지의 곱) 변수로 `m_aLongArray = new LongArray<DTYPE>(pTime, pCapacityPerTime);` 와 같이 생성되었음을 기억하자.

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [x] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::Zeros` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::operator[]` 메소드

    - [ ] `src/LongArray.hpp`: `LongArray` 생성자

    - [ ] `src/LongArray.hpp`: `LongArray::operator[]` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/LongArray.hpp`: `LongArray` 생성자

!!! help "분석 목표"

    `LongArray` 객체 생성 과정인 `m_aLongArray = new LongArray<DTYPE>(pTime, pCapacityPerTime);` 을 이해하기

    파라미터의 의미는 `pTime`(`0`번째 축) 과 `pCapacityPerTime`(`1`번째 축부터 마지막 축의 크기까지의 곱) 이었음을 기억하자.

```c++ linenums="1"
template<typename DTYPE> class LongArray {
private:
    DTYPE **m_aaHostLongArray; ///< 메모리에 올라가 있는 데이터의 주소 값.
    int m_CapacityOfLongArray; ///< LongArray의 총 용량.
    int m_TimeSize; ///< Tensor의 TimeSize
    int m_CapacityPerTime; ///< Time으로 나누어진 data의 Capacity
    Device m_Device; ///< 장치 사용 구분자 (CPU or GPU)
    int m_idOfDevice; ///< GPU사용 시, 사용하려는 GPU의 번호.
#ifdef __CUDNN__
    DTYPE **m_aaDevLongArray; ///< GPU메모리에 올라가있는 데이터의 주소 값. m_aaHostLongArray와 비슷한 역할을 한다.
#endif  // __CUDNN
    int  Alloc(unsigned int pTimeSize, unsigned int pCapacityPerTime);
    int  Alloc(LongArray *pLongArray);
    void Delete();
...
public:
    LongArray(unsigned int pCapacity);
    LongArray(unsigned int pTimeSize, unsigned int pCapacityPerTime);
    LongArray(LongArray *pLongArray);  // Copy Constructor
...
    DTYPE& operator[](unsigned int index);
...
};
```

- **18**:

    이 생성자가 호출된다.

- **19**:

    !!! danger
    
        또한 `LongArray(unsigned int pCapacity);` 로 선언된 생성자는 사용되고 있지 않다.

```c++ linenums="1"
template<typename DTYPE> LongArray<DTYPE>::LongArray(unsigned int pTimeSize, unsigned int pCapacity) {
    m_TimeSize        = 0;
    m_CapacityPerTime = 0;
    m_aaHostLongArray = NULL;
    m_Device          = CPU;
    m_idOfDevice      = -1;
#ifdef __CUDNN__
    m_aaDevLongArray = NULL;
#endif  // __CUDNN
    Alloc(pTimeSize, pCapacity);
}
```

- **10**:

    파라미터를 그대로 `Alloc` 메소드로 보내준다.

```c++ linenums="1"
template<typename DTYPE> int LongArray<DTYPE>::Alloc(unsigned int pTimeSize, unsigned int pCapacityPerTime) {
    m_TimeSize        = pTimeSize;
    m_CapacityPerTime = pCapacityPerTime;
    m_aaHostLongArray = new DTYPE *[m_TimeSize];

    for (int i = 0; i < m_TimeSize; i++) {
        m_aaHostLongArray[i] = new DTYPE[m_CapacityPerTime];

        for (int j = 0; j < m_CapacityPerTime; j++) {
            m_aaHostLongArray[i][j] = 0.f;
        }
    }
    m_CapacityOfLongArray = m_TimeSize * m_CapacityPerTime;
    m_Device = CPU;
    return TRUE;
}
```

- **2-3**:

    파라미터(`pTime`:`0`번째 축, `pCapacityPerTime`:`1`번째 축부터 마지막 축의 크기까지의 곱) 를 멤버변수 `m_TimeSize`, `m_CapacityPerTime` 에 저장한다.

    !!! danger

        그러나 멤버 이니셜라이저를 사용하면 성능이 더 좋아진다.

- **6-7**:

    `m_TimeSize` 만큼 `for` 문을 돌면서 `DTYPE ** m_aaHostLongArray` 더블포인터를 `m_CapacityPerTime` 크기의 `DTYPE` 배열의 배열로 초기화해준다.

    !!! danger
    
        왜 `LongArray` 를 이렇게 `2` 차원 배열로 만들었을까?

- **9-10**:

    `m_aaHostLongArray` 를 `0` 으로 초기화해준다. 

    !!! danger
    
        그러나 이렇게 `for` 문으로 메모리를 `0` 으로 초기화하는 것은 시간이 오래걸리므로 `memset` 함수를 사용하는 것이 더 빠르다. 하지만 `C++` 에서는 `memset` 보다 `std:fill` 이 권장된다.

        한편 `LongArray` 생성자가 반드시 `Alloc()` 메소드를 호출하는데 이 메소드가 항상 메모리를 `0` 으로 초기화시키므로 `Tensor::Zeros` 메소드의 의미가 무엇인지 알 수 없다. 왜냐하면 다른 `Tensor` 생성자를 호출해도 반드시 `0` 으로 초기화 되기 때문이다.


- **13**:

    `m_CapacityOfLongArray` 에 `LongArray` 의 총 크기를 저장해준다.

    `pTime`(`0`번째 축) 과 `pCapacityPerTime`(`1`번째 축부터 마지막 축의 크기까지의 곱) 이 `m_TimeSize` 와 `m_CapacityPerTime` 이 되었으므로 즉, 데이터셋의 형상을 모두 곱한 값을 저장해주는 것이다.

- **15**:

    !!! danger
    
        `1` 바이트 `bool` 이 아니라 `4` 바이트 `int` 형을 사용하므로 메모리가 낭비된다. 

        또한 메소드에서 에러가 발생했을 경우 `return FALSE` 해주는 코드가 없으므로 비대칭적인 메소드로 볼 수 있다.

!!! done "분석 결론"

    `m_TimeSize` $\times$ `m_CapacityPerTime` 형상의 배열을 만들어서 `DTYPE ** m_aaHostLongArray` 에 저장해주고 `0` 으로 초기화시킨다.

    `pTime`(`0`번째 축) 과 `pCapacityPerTime`(`1`번째 축부터 마지막 축의 크기까지의 곱) 이 `m_TimeSize` 와 `m_CapacityPerTime` 이 되었으므로 "첫번째 축의 크기 X 두번째 축부터 마지막 축까지의 곱" 의 배열이 생성되고 `0` 으로 초기화된 것이다.

    이 `m_aaHostLongArray` 가 `LongArray` 의 실체라고 할 수 있다. 
    
!!! info "분석 방향"

    이제 `LongArray::operator[]` 을 분석함으로써 `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 를 이해해야 한다. 

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [x] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::Zeros` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::operator[]` 메소드

    - [x] `src/LongArray.hpp`: `LongArray` 생성자

    - [ ] `src/LongArray.hpp`: `LongArray::operator[]` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

## `src/LongArray.hpp`: `LongArray::operator[]` 메소드

!!! help "분석 목표"

    `LongArray::operator[]` 을 분석함으로써 `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 를 이해하기

```c++ linenums="1"
template<typename DTYPE> class LongArray {
...
    DTYPE& operator[](unsigned int index);
...
}; 
```

- **3**:

    `[]` 연산자는 이렇게 선언되어 있다.

```c++ linenums="1"
template<typename DTYPE> DTYPE& LongArray<DTYPE>::operator[](unsigned int index) {
    #ifdef __CUDNN__
    if (m_Device == GPU) {
        this->SetDeviceCPU();
    }
    #endif  // __CUDNN__
    return m_aaHostLongArray[index / m_CapacityPerTime][index % m_CapacityPerTime];
}
```

- **1**:

    파라미터로 전달된 `index` 는 `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 에서 전달된 `Index5D(result->GetShape(), 0, 0, ch, ro, co)` 이었음을 기억하자. 

    그리고 `Index5D(result->GetShape(), 0, 0, ch, ro, co)` 는 `5` 차원 배열을 `1` 차원 배열로 변환했을 때 참조하는 방식이었음을 기억하자.

    그런데 실제로 `LongArray` 는 `m_TimeSize` $\times$ `m_CapacityPerTime` 형상의 배열로 저장되어있다. `m_TimeSize` 는 `0`번째 축을 뜻하고, `m_CapacityPerTime` 은 `1`번째 축부터 마지막 축의 크기까지의 곱을 뜻한다. 
    
    **LFW** 데이터셋(`.jpeg` 파일)을 `Tensor` 로 변환하는 이 코드 맥락에서는 `m_TimeSize` 가 **RGB** 채널인 $3$ 이고 `m_CapacityPerTime` 은 이미지의 가로와 세로를 곱한 $\text{width} \times \text{height}$ 이다.

!!! done "분석 결론"

    dd

!!! info "분석 방향"

    dd

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

    - [x] `LFW/ImageProcess.hpp`: `vision::Resize::DoTransform` 메소드

    - [x] `LFW/ImageProcess.hpp`: `vision::CenterCrop::DoTransform` 메소드

    - [x] `LFW/LFWDataset.hpp`: `LFWDataset::Image2Tensor` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::Zeros` 메소드

    - [x] `src/Tensor.hpp`: `Tensor::operator[]` 메소드

    - [x] `src/LongArray.hpp`: `LongArray` 생성자

    - [x] `src/LongArray.hpp`: `LongArray::operator[]` 메소드

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

---

---

---


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
