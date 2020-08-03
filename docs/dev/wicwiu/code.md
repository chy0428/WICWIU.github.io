
이곳에서는 이전에 설명한 [**WICWIU**](https://github.com/WICWIU/WICWIU) 로 신경망을 구성하고, [**WICWIU**](https://github.com/WICWIU/WICWIU) 로 딥러닝을 하는 것을 코드로 함께 보면서 이해해보겠습니다.

먼저 [**WICWIU**](https://github.com/WICWIU/WICWIU) 의 레이아웃을 다시 살펴보겠습니다.

## Project layout

[**WICWIU**](https://github.com/WICWIU/WICWIU) 는 크게 `lib/`, `tutorials/`, `src/` 로 구성되어 있습니다. 세부 디렉토리에 대한 설명은 다음과 같습니다.

    lib/                # 컴파일 후 정적 라이브러리가 생성되는 디렉토리.

    tutorials/          # WICWIU 로 제작된 여러 신경망을 학습해볼 수 있는 코드들.
                        # net/ 하위 디렉토리에 사전에 정의된 인공신경망이 있습니다.
                        # data/ 하위 디렉토리에 인공신경망이 학습할 데이터셋이 있습니다.
        CIFAR10/
        CIFAR100Reader/
        ImageNet/       # 포함된 파일을 이용하여 사전에 정의된 인공신경망을 학습 가능.
        MNIST/          # 포함된 파일을 이용하여 사전에 정의된 인공신경망을 학습 가능.
        GAN/            # 하위 디렉토리 내 포함된 파일을 이용하여 사전에
                        # 정의된 인공신경망을 학습할 수 있습니다.
            VanillaGAN/
            DCGAN/
            WGAN/
            BEGAN/

    src/                # LossFunction, Operator, Optimizer, 그리고 Module
                        # 을 비롯한 소스파일이 있는 디렉토리.
        LossFunction/
        Operator/
        Optimizer/
        Module/

# WICWIU 코드 살펴보기

!!! tip

    `makefile` 의 문법에 대한 기초가 부족하다면 [Makefile 기초 문법](../makefile/makefile.md) 를 참고하세요!

## Compile `src/` 

`src/` 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 라이브러리 디렉토리입니다. 이것을 컴파일하는 `makefile` 를 같이 살펴보겠습니다.

!!! info 

    [**WICWIU**](https://github.com/WICWIU/WICWIU) 는 계속 업데이트 되고 있기 때문에 최신 버전의 소스코드와 다를 수도 있습니다.

[:octicons-file-code-24: Source](https://github.com/WICWIU/WICWIU/blob/master/makefile)

```makefile linenums="1"
.SUFFIXES = .cpp .o

FRAMEWORK_LIB = lib/library.a
CFLAGS = -O2 -std=c++11

ENABLE_CUDNN = -D__CUDNN__
DFLAGS = -g -D__DEBUG__
```

- **1행** : 

    `Suffix`, `CPP` 파일을 Object 파일로 변환시켜주는 내장 규칙입니다.

- **3행** :

    [**WICWIU**](https://github.com/WICWIU/WICWIU) 의 정적 라이브러리입니다.

- **4행** :

    컴파일 옵션입니다.

- **6행** :

    cuDNN 사용 여부 플래그입니다. 

    !!! warning

        cuDNN 미 설치 및 미 사용 시 주석처리를 해야합니다.

- **7행** : 

    디버그 코드 사용 여부 플래그입니다. 

    !!! warning

        미 사용 시 주석처리를 해야합니다.

```makefile linenums="9"
INCLUDE_PATH = -I/usr/local/cuda/include
LIB_PATH = -L. -L/usr/local/cuda/lib64

CC = g++
NVCC = nvcc

ifdef	ENABLE_CUDNN
	LINKER = nvcc
	LFLAGS = -lcudart -lcudnn -lpthread
else
	LINKER = g++
	LFLAGS = -lpthread
endif
```

- **9행** :

    전처리 과정에서 CUDA 헤더 파일을 탐색할 디렉토리를 설정합니다.

- **10행** :

    CUDA 라이브러리를 탐색할 디렉토리를 설정합니다.

- **12행** :

    컴파일러를 정의합니다.

- **13행** :

    CUDA 파일 용 컴파일러를 정의합니다.

- **15행~21행** :

    cuDNN 사용 시, NVCC 링커 사용 및 `cudart`, `cudnn`, `pthread` 라이브러리를 사용합니다.

    cuDNN 미 사용 시, `g++` 링커 사용 및 `pthread` 라이브러리를 사용합니다.

```makefile linenums="23"
AR = ar

SRCS = \
	src/Utils.cpp	\
	src/Shape.cpp	\

OBJS = ${SRCS:.cpp=.o}

ifdef	ENABLE_CUDNN
	CUDA_SRCS = \
		src/Utils_CUDA.cu \
		src/Optimizer/AdamOptimizer_CUDA.cu \
		src/Operator/Concatenate_CUDA.cu
		
	CUDA_OBJS = ${CUDA_SRCS:.cu=.o}
endif

all:	$(FRAMEWORK_LIB)
```

- **25행~27행** :

    `.cpp` 소스 코드 파일을 정의합니다.

- **29행** :

    `SRCS` 의 `.cpp` 파일을 각각 컴파일해 `.o` 파일(오브젝트 파일)들을 생성합니다.

- **31행~38행** :

    cuDNN 사용 시, `CUDA_SRC/` 의 `.cu` 파일을 각각 컴파일해 `.o` 파일들을 생성합니다.

- **40행** : 

    컴파일 시작 타겟입니다. `FRAMEWORK_LIB` 의 의존성을 확인합니다.

```makefile linenums="42"
.cpp.o:
	$(CC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) $(LIB_PATH) -c $< -o $@

src/Utils_CUDA.o: src/Utils_CUDA.cu
	$(NVCC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) -c $< -o $@
src/Optimizer/AdamOptimizer_CUDA.o: src/Optimizer/AdamOptimizer_CUDA.cu
	$(NVCC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) -c $< -o $@
src/Operator/Concatenate_CUDA.o: src/Operator/Concatenate_CUDA.cu
	$(NVCC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) -c $< -o $@

$(FRAMEWORK_LIB): $(OBJS) $(CUDA_OBJS)
	$(AR) rcs $@ $(OBJS) $(CUDA_OBJS)

clean:
	rm -rf *.o $(OBJS) $(CUDA_OBJS) $(FRAMEWORK_LIB)
```

- **42행~43행** : 

    주어진 파일을 옵션들을 이용해 컴파일하여 같은 이름의 오브젝트 파일을 생성합니다.

- **45행~49행** :

    해당 `.cu` 파일의 의존성을 확인하고 옵션들을 이용해 컴파일하여 같은 이름의 오브젝트 파일을 생성합니다.

- **52행~53행** :

    `OBJS`, `CUDA_OBJS` 의 의존성을 확인하고, `FRAMEWORK_LIB`, `OBJS`, `CUDA_OBJS` 의 `.o` 파일들을 가지고 아카이브 파일을 만듭니다.

---

## Compile `tutorials/ImageNet/` 

`tutorials/ImageNet/` 은 [**WICWIU**](https://github.com/WICWIU/WICWIU) 신경망 모델 예제입니다. 이것을 컴파일하는 `makefile` 를 같이 살펴보겠습니다.

!!! info 

    [**WICWIU**](https://github.com/WICWIU/WICWIU) 는 계속 업데이트 되고 있기 때문에 최신 버전의 소스코드와 다를 수도 있습니다.

[:octicons-file-code-24: Source](https://github.com/WICWIU/WICWIU/blob/master/tutorials/ImageNet/makefile)

```makefile linenums="1"
.SUFFIXES = .cpp .o

CFLAGS = -O2 -std=c++11 -g
ENABLE_CUDNN = -D__CUDNN__
DFLAGS = -g -D__DEBUG__
LFLAGS = -lcudart -lcudnn -lpthread -ljpeg -lturbojpeg

INCLUDE_PATH = -I/usr/local/cuda/include -I/opt/libjpeg-turbo/include -I/opt/libjpeg-turbo/lib64 
LIB_PATH = -L. -L/usr/local/cuda/lib64 -L/opt/libjpeg-turbo/lib64

CC = g++
NVCC = nvcc

FRAMEWORK_LIB = ../../lib/library.a
```

- **6행** :

    라이브러리 사용 플래그, `cudart`, `cudnn`, `pthread`, `jpeg`, `turbojpeg` 라이브러리를 사용합니다.

- **8행** :

    전처리 과정에서 CUDA 헤더 파일을 탐색할 디렉토리를 설정합니다.

- **9행** :

    CUDA 라이브러리를 탐색할 디렉토리를 설정합니다.

- **14행** :

    프레임워크 라이브러리 아카이브 파일을 정의합니다.

```makefile linenums="17"
SRCS = \
	../../src/Shape.cpp	\
	../../src/LongArray.cpp	\
	../../src/Tensor.cpp	\
	../../src/Operator.cpp	\
	../../src/LossFunction.cpp	\
	../../src/Optimizer.cpp	\
	../../src/Module.cpp	\
	../../src/NeuralNetwork.cpp

all: main

.cpp.o:
	$(CC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) $(LIB_PATH) -c $< -o $@

main: main.o $(FRAMEWORK_LIB)
	$(NVCC) $(CFLAGS) $(ENABLE_CUDNN) $(DFLAGS) $(LFLAGS) $(INCLUDE_PATH) $(LIB_PATH) -o $@ $(FRAMEWORK_LIB) main.o

$(FRAMEWORK_LIB): $(SRC)
	make -C ../..

clean:
	rm -rf *.o main

clean_all:
	rm -rf *.o main
	make clean -C ../..
```

- **17행~25행** : 

    `.cpp` 소스 코드 파일, 아카이브 파일의 의존성 확인을 위해 정의하는 변수입니다.

- **27행** :

    시작 타겟, `main` 파일의 의존성을 확인합니다.

- **29행~30행** :

    주어진 파일을 옵션들을 이용해 컴파일하여 같은 이름의 오브젝트 파일을 생성합니다.

- **32행~33행** :

    `main.o` 파일과 `FRAMEWORK_LIB` 의 의존성을 확인하고,  옵션들을 이용해 `FRAMEWORK_LIB` 과 `main.o` 파일을 `main` 파일로 링크한다.

- **35행~36행** :

    지정된 경로에서 `make` 실행

---

## Tutorials `tutorials/MNIST`

`tutorials/MNIST` 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 신경망 모델 예제입니다.

### Tutorials `tutorials/MNIST/net/my_CNN.hpp`

`tutorials/MNIST/net/my_CNN.hpp` 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 에서 **CNN** 으로 MNIST 데이터셋을 학습하기 위한 인공신경망을 구성하는 예제입니다. MNIST 튜토리얼의 신경망 모델은 다음과 같이 정의됩니다. 

!!! info 

    [**WICWIU**](https://github.com/WICWIU/WICWIU) 는 계속 업데이트 되고 있기 때문에 최신 버전의 소스코드와 다를 수도 있습니다.

[:octicons-file-code-24: Source](https://github.com/WICWIU/WICWIU/blob/master/tutorials/MNIST/net/my_CNN.hpp)

```c++ linenums="1"
class my_CNN : public NeuralNetwork<float>{
private:
public:
    my_CNN(Tensorholder<float> *x, Tensorholder<float> *label) {
        SetInput(2, x, label);

        Operator<float> *out = NULL;

        out = new ReShape<float>(x, 28, 28, "Flat2Image");

        // ======================= layer 1=======================
        out = new ConvolutionLayer2D<float>(out, 1, 32, 3, 3, 1, 1, 0, TRUE, "Conv_1");
        out = new BatchNormalizeLayer<float>(out, TRUE, "BN_1");
        out = new Relu<float>(out, "Relu_1");
        out = new Maxpooling2D<float>(out, 2, 2, 2, 2, "MaxPool_1");

        // ======================= layer 2=======================
        out = new ConvolutionLayer2D<float>(out, 32, 64, 3, 3, 1, 1, 0, TRUE, "Conv_2");
        out = new BatchNormalizeLayer<float>(out, TRUE, "BN_2");
        out = new Relu<float>(out, "Relu_2");
        out = new Maxpooling2D<float>(out, 2, 2, 2, 2, "MaxPool_2");

        // ======================= layer 3=======================
        out = new ReShape<float>(out, 1, 1, 5 * 5 * 64, "Image2Flat");

        // ======================= layer 3=======================
        out = new Linear<float>(out, 5 * 5 * 64, 1024, TRUE, "Fully-Connected_1");
        out = new Relu<float>(out, "Relu_3");
        //// ======================= layer 4=======================
        out = new Linear<float>(out, 1024, 10, TRUE, "Fully-connected_2");

        AnalyzeGraph(out);

        // ======================= Select LossFunction Function ===================
        SetLossFunction(new SoftmaxCrossEntropy<float>(out, label, "SCE"));


        // ======================= Select Optimizer ===================  
        SetOptimizer(new RMSPropOptimizer<float>(GetParameter(), 0.01, 0.9, 1e-08, FALSE, MINIMIZE));
    }
    virtual ~my_CNN() {}
};
```

- **5행** :

    `SetInput` 함수를 통해 $2$ 가지 입력(`data`, `label`) 이 모델의 학습에 들어간다는 것을 명시합니다.

- **9행** :

    `ReShape` 함수로 MNIST 손글씨 이미지 `x` 를 `Tensor` 형태로 변환합니다.

- **12행~30행** :

    `ConvolutionLayer2D`, `BatchNormalizeLayer`, `Relu`, `Maxpooling` 등의 `Operator` 들로 신경망을 구성합니다. 

- **35행** :

    `SetLossFunction` 함수로 손실함수를 정의합니다.

- **39행** :

    `SetOptimizer` 함수로 `Optimizer` 를 정의합니다.

### Tutorials `tutorials/MNIST/main.cpp`

`tutorials/MNIST/main.cpp` 는 `tutorials/MNIST/net/my_CNN.hpp` 에서 정의한 인공신경망을 사용하여 MNIST 손글씨 데이터셋을 학습합니다.

[:octicons-file-code-24: Source](https://github.com/WICWIU/WICWIU/blob/master/tutorials/MNIST/main.cpp)

```c++ linenums="19"
// create input, label data placeholder -> Tensorholder
Tensorholder<float> *x     = new Tensorholder<float>(1, BATCH, 1, 1, 784, "x");
Tensorholder<float> *label = new Tensorholder<float>(1, BATCH, 1, 1, 10, "label");

// ======================= Select net ===================
NeuralNetwork<float> *net = new my_CNN(x, label);
// ======================= Prepare Data ===================
MNISTDataSet<float> *train_dataset = new MNISTDataSet<float>("data/train-images-idx3-ubyte", "data/train-labels-idx1-ubyte", TRAINING);
DataLoader<float> * train_dataloader = new DataLoader<float>(train_dataset, BATCH, TRUE, 20, FALSE);

MNISTDataSet<float> *test_dataset = new MNISTDataSet<float>("data/t10k-images-idx3-ubyte", "data/t10k-labels-idx1-ubyte", TESTING);
DataLoader<float> * test_dataloader = new DataLoader<float>(test_dataset, BATCH, FALSE, 20, FALSE);
```

- **20행~21행** :

    `Tensorholder` (placeholder) 클래스로 손글씨 이미지와 정답레이블을 저장 할 변수를 생성합니다.

- **24행** :

    사전에 정의한 `CNN` 신경망을 생성합니다.

- **26~30행** :

    MNIST 데이터셋과 데이터로더를 생성합니다.

```c++ linenums="62"
// ======================= Train =======================
float train_accuracy = 0.f;
float train_avg_loss = 0.f;

net->SetModeTrain();

startTime = clock();

for (int j = 0; j < LOOP_FOR_TRAIN; j++) {
    //dataset->CreateTrainDataPair(BATCH);
    std::vector<Tensor<float> *> * temp =  train_dataloader->GetDataFromGlobalBuffer();
    // printf("%d\r\n", temp->size());

    Tensor<float> *x_t = (*temp)[0];
    Tensor<float> *l_t = (*temp)[1];
    delete temp;

#ifdef __CUDNN__
    x_t->SetDeviceGPU(GPUID); 
    l_t->SetDeviceGPU(GPUID);
#endif  // __CUDNN__
    // std::cin >> temp;
    net->FeedInputTensor(2, x_t, l_t);
    net->ResetParameterGradient();
    net->Train();
    // std::cin >> temp;
    train_accuracy += net->GetAccuracy();
    train_avg_loss += net->GetLoss();

    printf("\rTrain complete percentage is %d / %d -> loss : %f, acc : %f"  /*(ExcuteTime : %f)*/,
            j + 1, LOOP_FOR_TRAIN,
            train_avg_loss / (j + 1),
            train_accuracy / (j + 1)
            /*nProcessExcuteTime*/);
    fflush(stdout);
}
endTime            = clock();
nProcessExcuteTime = ((double)(endTime - startTime)) / CLOCKS_PER_SEC;
printf("\n(excution time per epoch : %f)\n\n", nProcessExcuteTime);
```

- **72행~77행**:

    MNIST 데이터셋으로부터 이미지와 정답레이블을 받아 저장합니다.

- **79행~82행**:

    cuDNN 을 사용 할 경우,  `placeholder` 의 `device` 를 `GPU` 로 설정한다.

- **84행~86행**:

    신경망에 데이터셋(손글씨 이미지, 정답레이블)를 만들어 넣고 신경망의 Gradient 값을 초기화 하고 학습하는 과정을 반복한다.

```c++ linenums="102"
// ======================= Test ======================
float test_accuracy = 0.f;
float test_avg_loss = 0.f;

net->SetModeInference();

for (int j = 0; j < (int)LOOP_FOR_TEST; j++) {
    //dataset->CreateTestDataPair(BATCH);
    std::vector<Tensor<float> *> * temp =  test_dataloader->GetDataFromGlobalBuffer();
    // printf("%d\r\n", temp->size());

    Tensor<float> *x_t = (*temp)[0];
    Tensor<float> *l_t = (*temp)[1];
    delete temp;

#ifdef __CUDNN__
    x_t->SetDeviceGPU(GPUID);
    l_t->SetDeviceGPU(GPUID);
#endif  // __CUDNN__

    net->FeedInputTensor(2, x_t, l_t);
    net->Test();

    test_accuracy += net->GetAccuracy();
    test_avg_loss += net->GetLoss();

    printf("\rTest complete percentage is %d / %d -> loss : %f, acc : %f",
            j + 1, LOOP_FOR_TEST,
            test_avg_loss / (j + 1),
            test_accuracy / (j + 1));
    fflush(stdout);
}
```

- **106행**:

    신경망을 테스트 모드(gradient 를 계산하지 않음)로 전환합니다.
    
- **110행~115행**:
    
    MNIST 데이터셋으로부터 이미지와 정답레이블을 받아 저장합니다.

- **122행~123행**:

    신경망에 데이터(image, label)를 입력하고 테스트를 진행합니다.  
    
- **125행~126행**:

    정확도와 손실을 측정한다.

---

## Tutorials `tutorials/ImageNet`

`tutorials/ImageNet` 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 신경망 모델 예제입니다.

### Tutorials `tutorials/ImageNet/net/my_Resnet.hpp`
`tutorials/ImageNet/net/my_Resnet.hpp` 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 에서 **ResNet** 으로 ImageNet 데이터셋을 학습하기 위한 인공신경망을 구성하는 예제입니다. ImageNet 튜토리얼의 신경망 모델은 다음과 같이 정의됩니다. 

[:octicons-file-code-24: Source](https://github.com/WICWIU/WICWIU/blob/master/tutorials/ImageNet/net/my_Resnet.hpp)


```c++ linenums="3"
template<typename DTYPE> class BasicBlock :
    public Module<DTYPE>{
private:
public:
    BasicBlock(Operator<DTYPE> *pInput, int pNumInputChannel, int pNumOutputChannel, int pStride = 1, std::string pName = NULL) {
        Alloc(pInput, pNumInputChannel, pNumOutputChannel, pStride, pName);
    }

    virtual ~BasicBlock() {}

    int Alloc(Operator<DTYPE> *pInput, int pNumInputChannel, int pNumOutputChannel, int pStride, std::string pName) {
        this->SetInput(pInput);

        Operator<DTYPE> *remember = pInput;
        Operator<DTYPE> *out      = pInput;

        // 1
        out = new ConvolutionLayer2D<DTYPE>(out, pNumInputChannel, pNumOutputChannel, 3, 3, pStride, pStride, 1, FALSE, "BasicBlock_Conv1" + pName);
        out = new BatchNormalizeLayer<DTYPE>(out, TRUE, "BasicBlock_BN1" + pName);
        out = new Relu<DTYPE>(out, "BasicBlock_Relu1" + pName);

        // 2
        out = new ConvolutionLayer2D<DTYPE>(out, pNumOutputChannel, pNumOutputChannel, 3, 3, 1, 1, 1, FALSE, "BasicBlock_Conv2" + pName);
        out = new BatchNormalizeLayer<DTYPE>(out, TRUE, "BasicBlock_BN2" + pName);
        // out = new Relu<DTYPE>(out, "BasicBlock_Relu2" + pName);

        // ShortCut
        if ((pStride != 1) || (pNumInputChannel != pNumOutputChannel)) {
            remember = new ConvolutionLayer2D<DTYPE>(remember, pNumInputChannel, pNumOutputChannel, 1, 1, pStride, pStride, 0, FALSE, "BasicBlock_Conv3_Shortcut" + pName);
            remember = new BatchNormalizeLayer<DTYPE>(remember, TRUE, "BasicBlock_BN3_Shortcut" + pName);
            // remember = new Relu<DTYPE>(remember, "BasicBlock_Relu3_Shortcut" + pName);
        }

        // Add (for skip Connection)
        out = new Addall<DTYPE>(remember, out, "ResNet_Skip_Add" + pName);
        // out = new Addall<DTYPE>(remember, out, "ResNet_Skip_Add");

        // Last Relu
        out = new Relu<DTYPE>(out, "BasicBlock_Relu3" + pName);

        this->AnalyzeGraph(out);

        return TRUE;
    }
};
```

[**WICWIU**](https://github.com/WICWIU/WICWIU) 의 ResNet 은 여러 개의 `BasicBlock(residual block)` 을 적층시켜 구성합니다.

- **20행~32행**:

    `BasicBlock` 은 **Convolution layer**, **BatchNormailze layer**, **Relu** 로 이루어진 2개의 layer와 **skip connection(Short cut)** 으로 이루어집니다.

- **37행**:

    **skip connection** 은 `Addall` `Operator` 로 구현됩니다.

```c++ linenums="49"
template<typename DTYPE> class ResNet :
    public NeuralNetwork<DTYPE>{
private:
    int m_numInputChannel;

public:
    ResNet(Tensorholder<DTYPE> *pInput, Tensorholder<DTYPE> *pLabel, std::string pBlockType, int pNumOfBlock1, int pNumOfBlock2, int pNumOfBlock3, int pNumOfBlock4, int pNumOfClass) {
        Alloc(pInput, pLabel, pBlockType, pNumOfBlock1, pNumOfBlock2, pNumOfBlock3, pNumOfBlock4, pNumOfClass);
    }

    virtual ~ResNet() {}

    int Alloc(Tensorholder<DTYPE> *pInput, Tensorholder<DTYPE> *pLabel, std::string pBlockType, int pNumOfBlock1, int pNumOfBlock2, int pNumOfBlock3, int pNumOfBlock4, int pNumOfClass) {
        this->SetInput(2, pInput, pLabel);

        m_numInputChannel = 64;

        Operator<DTYPE> *out = pInput;

        // ReShape
        out = new ReShape<DTYPE>(out, 3, 224, 224, "ReShape");
        // out = new BatchNormalizeLayer<DTYPE>(out, TRUE, "BN0");

        // 1
        out = new ConvolutionLayer2D<DTYPE>(out, 3, m_numInputChannel, 7, 7, 2, 2, 3, FALSE, "Conv");
        out = new BatchNormalizeLayer<DTYPE>(out, TRUE, "BN0");
        out = new Relu<DTYPE>(out, "Relu0");

        out = new Maxpooling2D<float>(out, 3, 3, 2, 2, 1, "MaxPool_2");
        // out = new BatchNormalizeLayer<DTYPE>(out, TRUE, "BN1");

        out = this->MakeLayer(out, m_numInputChannel, pBlockType, pNumOfBlock1, 1, "Block1");
        out = this->MakeLayer(out, 128, pBlockType, pNumOfBlock2, 2, "Block2");
        out = this->MakeLayer(out, 256, pBlockType, pNumOfBlock3, 2, "Block3");
        out = this->MakeLayer(out, 512, pBlockType, pNumOfBlock3, 2, "Block4");

        // out = new BatchNormalizeLayer<DTYPE>(out, TRUE, "BN1");
        // out = new Relu<DTYPE>(out, "Relu1");

        out = new GlobalAvaragePooling2D<DTYPE>(out, "Avg Pooling");

        out = new ReShape<DTYPE>(out, 1, 1, 512, "ReShape");

        out = new Linear<DTYPE>(out, 512, pNumOfClass, FALSE, "Classification");
        // out = new BatchNormalizeLayer < DTYPE > (out, FALSE, "BN0");

        this->AnalyzeGraph(out);

        // ======================= Select LossFunction Function ===================
        this->SetLossFunction(new SoftmaxCrossEntropy<float>(out, pLabel, "SCE"));
        // SetLossFunction(new MSE<float>(out, label, "MSE"));

        // ======================= Select Optimizer ===================
        // this->SetOptimizer(new GradientDescentOptimizer<float>(this->GetParameter(), 0.1, 0.9, 5e-4, MINIMIZE));
        // this->SetOptimizer(new GradientDescentOptimizer<float>(this->GetParameter(), 0.001, MINIMIZE));
        this->SetOptimizer(new AdamOptimizer<float>(this->GetParameter(), 0.001, 0.9, 0.999, 1e-08, 5e-4, MINIMIZE));

        return TRUE;
    }

    Operator<DTYPE>* MakeLayer(Operator<DTYPE> *pInput, int pNumOfChannel, std::string pBlockType, int pNumOfBlock, int pStride, std::string pName = NULL) {
        if (pNumOfBlock == 0) {
            return pInput;
        } else if ((pBlockType == "BasicBlock") && (pNumOfBlock > 0)) {
            Operator<DTYPE> *out = pInput;

            out = new BasicBlock<DTYPE>(out, m_numInputChannel, pNumOfChannel, pStride, pName);
            int pNumOutputChannel = pNumOfChannel;

            for (int i = 1; i < pNumOfBlock; i++) {
                out = new BasicBlock<DTYPE>(out, pNumOutputChannel, pNumOutputChannel, 1, pName);
            }

            m_numInputChannel = pNumOutputChannel;

            return out;
        } else if ((pBlockType == "Bottleneck") && (pNumOfBlock > 0)) {
            return NULL;
        } else return NULL;
    }
};
```

- **73행~83행**:

    [**WICWIU**](https://github.com/WICWIU/WICWIU) 의 `ResNet` 튜토리얼의 인공 신경망은 **Conv**, **BatchNorm** 등의 `Operator` 들과 사전에 정의한 4개의 `BasicBlock` 으로 모델을 구성합니다.

- **98행~104행**:

    `SetLossFunction` 과 `SetOptimizer` 를 이용해 손실함수와 `Optimizer` 를 정의합니다.

```c++ linenums="131"
template<typename DTYPE> NeuralNetwork<DTYPE>* Resnet18(Tensorholder<DTYPE> *pInput, Tensorholder<DTYPE> *pLabel, int pNumOfClass) {
    return new ResNet<DTYPE>(pInput, pLabel, "BasicBlock", 2, 2, 2, 2, pNumOfClass);
}

template<typename DTYPE> NeuralNetwork<DTYPE>* Resnet34(Tensorholder<DTYPE> *pInput, Tensorholder<DTYPE> *pLabel, int pNumOfClass) {
    return new ResNet<DTYPE>(pInput, pLabel, "BasicBlock", 3, 4, 6, 3, pNumOfClass);
}
```

- **131행~137행** 

    `ResNet` 의 종류는 `BasicBlock` 내부의 채널 수를 다르게 함으로써 나누어집니다.