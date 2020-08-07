# Analysis: Dataset to Tensor

fewshot 팀은 LFW 팀이 개발해둔 코드를 참고할 수 있기 때문에 먼저 LFW 코드를 분석해보았다. [**WICWIU**](https://github.com/WICWIU/WICWIU) 개발 가이드의 [**WICWIU 로 학습하기**](../../dev/wicwiu/learn.md) 의 첫번째 과정이 "**Step 1. 학습 데이터 &rarr; `Tensor`**" 이기 때문에 먼저 학습시켜야할 데이터셋인 **Casia Web Face** 를 `Tensor` 로 변환해야 했다. 그래서 LFW 팀의 코드에서 데이터셋을 `Tensor` 로 변환하는 코드 흐름을 중점으로 분석을 시도해보았다.

!!! note

    `tutorials/LFW/` 경로를 `LFW/` 로 축약하여 사용하였다.

!!! info "분석 방향"

    `LFW` 를 사용하여 인공신경망을 학습하고 테스트하는 `main` 함수를 ^^데이터셋을 `Tensor` 로 변환하여 인공신경망에 입력하는 것을 중심으로 분석^^ 해본다.

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

    하지만 주석도 없고 API 도 없을 뿐더러 지금의 목표는 데이터셋을 `Tensor` 로 변환하는 것이므로 그 처리를 정확히 이해하는 것은 지금은 불필요하다. 따라서 자세히 분석하지는 않는다.

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

    하지만 주석도 없고 API 도 없을 뿐더러 지금의 목표는 데이터셋을 `Tensor` 로 변환하는 것이므로 그 처리를 정확히 이해하는 것은 지금은 불필요하다. 따라서 자세히 분석하지는 않는다.

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

        그리고 나중에 살펴보겠지만 `Tensor::Zeros` 는 내부적으로 `Shape` 객체를 생성한다. 그러므로 동일한 데이터셋을 표현하는 `Shape` 객체가 $2$ 번이나 불필요하게 생성된 것이다.

- **12-15**:

    `doValuerScaling` 이 `TRUE` 이므로 이 코드가 실행된다.

    `imgBuf` 의 `ro * width * channel + co * channel + ch` 인덱스를 참조하여 `255.0` 로 나눈다. 단지 $1$ 차원 배열에 저장되어 있는 $3$ 차원 데이터를 참조하는 방식으로 보인다.

    이것은 **libjpeg-turbo** 가 압축 해제한 데이터셋이므로 $3$ 차원 데이터셋인 이미지의 실제 데이터를 참조할 때 왜 `ro * width * channel + co * channel + ch` 로 참조하는지는 **libjpeg-turbo** 를 참조해야 할 것 같다. 이는 만약 다른 라이브러리로(가령 `CImg`) 데이터셋을 $1$ 차원 배열로 만들고 그것을 다시 `Tensor` 로 변환한다면 또 다른 방식으로 $1$ 차원 배열의 인덱스를 참조해야 한다는 것을 의미한다.

    !!! danger

        `(*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)]` 하지만 이렇게 하면 데이터 참조 과정이 번거롭고 불필요한 과정이 되지 않나 싶다.

        왜냐하면 `Index5D` 메소드를 `Tensor` 클래스 내부에서 처리할 수 있기 때문이다. 그렇게 한다면 사용자의 편의를 높일 수 있다.

    !!! danger

        `imgBuf` 는 `unsigned char` 형 배열인데 이것의 원소를 명시적 형변환 없이 `double` 형으로 나누고 있으므로 이 코드는 [암시적 형변환](https://ko.wikipedia.org/wiki/%ED%98%95_%EB%B3%80%ED%99%98) 을 일으킨다. 암시적 형변환은 프로젝트의 안정성과 신뢰성을 파괴하는 주된 원인 중 하나이므로 고칠 필요가 있어 보인다.

        저장 대상인 `LongArray` 의 `DTYPE ** m_aaHostLongArray` 의 추상자료형 `DTYPE` 은 `Tensor` 가 결정하고, `Tensor` 의 추상자료형은 `LFWDataset` 이 결정하고, `LFWDataset` 의 추상자료형은 `LFW/main.cpp` 의 `main` 함수의 호출형태에서 결정된다. 
        
        그런데 심지어 그 `LFWDataset` 호출형태가 `LFWDataset<float> *train_dataset = new LFWDataset<float>("./data", "lfw_funneled", NUMBER_OF_CLASS, transform);` 이었던 것을 기억하자. 그러므로 `double` 에서 `float` 에서 암시적 형변환이 일어나면서 데이터 손실까지 발생할 수도 있다.

        좀 더 큰 자료형에 대한 암시적 형변환은 애교로 봐줄만 하지만 더 작은 자료형에 대한 암시적 형변환은 프로젝트의 안정성을 심각하게 해친다.
        
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

    이것을 일반화하면 $t_1 \in \mathbb{N}, t_2 \in \mathbb{N}, t_3 \in \mathbb{N}$ 에 대한 $t_1 \times t_2 \times t_3$ 텐저를 $1 \times t_1t_2t_3$ 배열로 변환하여 인덱스를 참조하기 위해서는 $i_1 \in \{0, 1, \dots, t_1-1\}, i_2 \in \{0, 1, \dots, t_2-1\}, i_3 \in \{0, 1, \dots, t_3-1\}$ 인 $i_1, i_2, i_3$ 에 대하여 
    
    $$i_1t_2t_3 + i_2t_3 + i_3 = (i_1t_2 + i_2)t_3 + i_3$$
    
    로 참조해야 한다는 것을 귀납적으로 알 수 있다. 이것을 코드로 변환하면 위와 같은 `Index3D` 함수가 된다.

    그렇다면 마찬가지로 $t_1 \in \mathbb{N}, t_2 \in \mathbb{N}, t_3 \in \mathbb{N}, t_4 \in \mathbb{N}, t_5 \in \mathbb{N}$ 에 대한 $t_1 \times t_2 \times t_3 \times t_4 \times t_5$ 텐저를 $1 \times t_1t_2t_3t_4t_5$ 배열로 변환하여 인덱스를 참조하기 위해서는 
    
    $$i_1 \in \{0, 1, \dots, t_1-1\}$$ 
    
    $$i_2 \in \{0, 1, \dots, t_2-1\}$$ 
    
    $$i_3 \in \{0, 1, \dots, t_3-1\}$$ 

    $$i_4 \in \{0,1,\dots,t_4-1\}$$ 

    $$i_5 \in \{0, 1, \dots, t_5-1\}$$ 

    인 $i_1, i_2, i_3, i_4, i_5$ 에 대하여 
    
    $$i_1t_5t_4t_3t_2+i_2t_5t_4t_3+i_3t_5t_4+i_4t_5+i_5 = (((i_1t_2+i_2)t_3+i_3)t_4+i_4)t_5 + i_5$$
    
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

    `LFWDataset::Image2Tensor` 메소드의

    ```c++ 
    for (int ro = 0; ro < height; ro++) {
        for (int co = 0; co < width; co++) {
            for (int ch = 0; ch < channel; ch++) {
                (*result)[Index5D(result->GetShape(), 0, 0, ch, ro, co)] = imgBuf[ro * width * channel + co * channel + ch] / 255.0;
    ```

    에서 `Index5D(result->GetShape(), 0, 0, ch, ro, co)` 가 `index` 로 전달되었음을 기억하자. 

- **7**:

    결국 `LFWDataset::Image2Tensor` 란 `Index5D(result->GetShape(), 0, 0, ch, ro, co)` 으로 전달된 `index` 로써 `2` 차원 배열 `m_aaHostLongArray[index / m_CapacityPerTime][index % m_CapacityPerTime]` 에 데이터셋 `imgBuf` 의 원소를 하나하나 복사하고 있는 것이다.

    ^^이로써 우리는 데이터셋을 `Tensor`로 변환하는 방법을 이해했다.^^

    데이터셋을 `Tensor` 로 변환하는 방법이란 (1) 데이터셋을 적절한 방식으로 읽고 (2) 메모리에 저장한 다음 (3) `Tensor` 객체를 데이터셋 형상에 맞춰서 적절히 만들고 (4) 그냥 `Tensor[Index5D(i1, i2, i3, i4, i5)]` 라는 식으로 복사하면 끝이다.

    !!! danger
    
        근데 `[index / m_CapacityPerTime][index % m_CapacityPerTime]` 라는 인덱싱 방식이 무슨 의미를 갖는거지? `5` 차원 데이터를 참조하는 인덱싱 방식을 가져와서 어떻게 처리를 하길래 `2` 차원 배열에 저장해줄 수 있는거지?

!!! danger

    그런데 실제로 `LongArray` 의 `DTYPE ** m_aaHostLongArray` 는 `m_TimeSize` $\times$ `m_CapacityPerTime` 형상의 배열로 저장되어있다. `m_TimeSize` 는 `0`번째 축을 뜻하고, `m_CapacityPerTime` 은 `1`번째 축부터 마지막 축의 크기까지의 곱을 뜻했다.

    `Index5D` 에서 전달된 `5` 차원 텐저는 실제로 `Tensor<DTYPE> *result = Tensor<DTYPE>::Zeros(1, 1, channel, height, width);` 로 정의 되었으므로 $t_1 = t_2 = 1$ 이고, 첫번째와 두번째 인덱스가 항상 $0$ 이므로 $i_1=i_2=0$ 이다. 따라서 `5` 차원 텐저가 `1` 차원 배열로 저장하기 위한 인덱스는
    
    $$i_1t_5t_4t_3t_2+i_2t_5t_4t_3+i_3t_5t_4+i_2t_5+i_5 = (((i_1t_2+i_2)t_3+i_3)t_4+i_2)t_5 + i_5$$

    $$\iff 0 + 0 + i_3t_5t_4+i_2t_5+i_5 $$

    가 되어 `3` 차원  배열을 저장하기 위한 인덱스로 바뀐다.

    > 왜 이렇게 번거롭게 하는거지? 불필요한 연산들이 성능을 저하시킬 수도 있다.
    
    어쨌든 그 `3` 차원 배열, 즉 `3` 차원 데이터셋을 `1` 차원 배열에 저장하기 위한 `index` 가 다시 `2` 차원 배열 `DTYPE ** m_aaHostLongArray` 에 저장되기 위한 인덱스 연산 `[index / m_CapacityPerTime][index % m_CapacityPerTime]` 을 거쳐간다.

    > 대체 왜 `3` 차원 데이터셋을 `5` 차원 `Tensor` 에 저장한 다음 `1` 차원 배열에 저장하기 위한 인덱스 연산을 한 다음 `2` 차원 배열에 저장하는 거지???????????????????????? 왜왜 왜 이렇게 하는거지?
    
!!! done "분석 결론"

    ^^이로써 우리는 데이터셋을 `Tensor`로 변환하는 방법을 이해했다.^^

    **데이터셋을 `Tensor` 로 변환하는 방법이란 (1) 데이터셋을 적절한 방식으로 읽고 (2) 메모리에 저장한 다음 (3) `Tensor` 객체를 데이터셋 형상에 맞춰서 적절히 만들고 (4) 그냥 `Tensor[Index5D(i1, i2, i3, i4, i5)]` 라는 식으로 복사하면 끝이다.**

!!! info "분석 방향"

    분석 지도에 따르면 아직 

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler` 생성자

    - [ ] `LFW/LFWSampler.hpp`: `LFWSampler::GetDataFromGlobalBuffer` 메소드

    을 분석하지 않았지만 데이터셋을 `Tensro` 로 변환하는 과정을 충분히 이해했으므로 이쯤에서 다른 코드 분석을 그만두고, 코딩을 시작해본다.

    하지만 이후에 물론 `DataLoader` 를 정의해야 할 것이다. 그러나 모든 건 인공신경망 구현을 위한 것이었으므로 코딩을 시작할 기본적인 준비라도 끝나면 일단 할 수 있는 수준까지의 코딩은 해두는 것이 옳은 방향인 것 같다.

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