
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

- **1행** : `.SUFFIXES = .cpp .o`

    `Suffix`, `CPP` 파일을 Object 파일로 변환시켜주는 내장 규칙입니다.

- **3행** : `FRAMEWORK_LIB = lib/library.a`

    [**WICWIU**](https://github.com/WICWIU/WICWIU) 의 정적 라이브러리입니다.

- **4행** : `CFLAGS = -O2 -std=c++11`

    컴파일 옵션입니다.

- **6행** : `ENABLE_CUDNN = -D__CUDNN__`

    cuDNN 사용 여부 플래그입니다. 

    !!! warning

        cuDNN 미 설치 및 미 사용 시 주석처리를 해야합니다.

- **7행** : `DFLAGS = -g -D__DEBUG__`

    디버그 코드 사용 여부 플래그입니다. 

    !!! warning

        미 사용 시 주석처리를 해야합니다.

- **9행** : `INCLUDE_PATH = -I/usr/local/cuda/include`

    전처리 과정에서 CUDA 헤더 파일을 탐색할 디렉토리를 설정합니다.

- **10행** : `LIB_PATH = -L. -L/usr/local/cuda/lib64`

    CUDA 라이브러리를 탐색할 디렉토리를 설정합니다.

- **12행** : `CC = g++`

    컴파일러를 정의합니다.

- **13행** : `NVCC = nvcc`

    CUDA 파일 용 컴파일러를 정의합니다.

- **15행~21행** :

    ```
    ifdef	ENABLE_CUDNN
        LINKER = nvcc
        LFLAGS = -lcudart -lcudnn -lpthread
    else
        LINKER = g++
        LFLAGS = -lpthread
    endif
    ```

    cuDNN 사용 시, NVCC 링커 사용 및 `cudart`, `cudnn`, `pthread` 라이브러리를 사용합니다.

    cuDNN 미 사용 시, `g++` 링커 사용 및 `pthread` 라이브러리를 사용합니다.

- **25행~27행** :

    ```
    SRCS = \
        src/Utils.cpp	\
        src/Shape.cpp	\
    ```

    `.cpp` 소스 코드 파일을 정의합니다.

- **29행** : `OBJS = ${SRCS:.cpp=.o}`

    `SRCS` 의 `.cpp` 파일을 각각 컴파일해 `.o` 파일(오브젝트 파일)들을 생성합니다.

- **31행~38행** :

    ```
    ifdef	ENABLE_CUDNN
        CUDA_SRCS = \
            src/Utils_CUDA.cu \
            src/Optimizer/AdamOptimizer_CUDA.cu \
            src/Operator/Concatenate_CUDA.cu
            
        CUDA_OBJS = ${CUDA_SRCS:.cu=.o}
    endif
    ```

    cuDNN 사용 시, `CUDA_SRC/` 의 `.cu` 파일을 각각 컴파일해 `.o` 파일들을 생성합니다.

- **40행** : `all:	$(FRAMEWORK_LIB)`

    컴파일 시작 타겟입니다. `FRAMEWORK_LIB` 의 의존성을 확인합니다.

- **42행~43행** : 

    ```
    .cpp.o:
        $(CC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) $(LIB_PATH) -c $< -o $@
    ```

    주어진 파일을 옵션들을 이용해 컴파일하여 같은 이름의 오브젝트 파일을 생성합니다.

- **45행~49행** :

    ```
    src/Utils_CUDA.o: src/Utils_CUDA.cu
        $(NVCC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) -c $< -o $@
    src/Optimizer/AdamOptimizer_CUDA.o: src/Optimizer/AdamOptimizer_CUDA.cu
        $(NVCC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) -c $< -o $@
    src/Operator/Concatenate_CUDA.o: src/Operator/Concatenate_CUDA.cu
        $(NVCC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) -c $< -o $@
    ```

    해당 `.cu` 파일의 의존성을 확인하고 옵션들을 이용해 컴파일하여 같은 이름의 오브젝트 파일을 생성합니다.

- **52행~53행** :

    ```
    $(FRAMEWORK_LIB): $(OBJS) $(CUDA_OBJS)
        $(AR) rcs $@ $(OBJS) $(CUDA_OBJS)
    ```

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

- **6행** : `LFLAGS = -lcudart -lcudnn -lpthread -ljpeg -lturbojpeg`

    라이브러리 사용 플래그, `cudart`, `cudnn`, `pthread`, `jpeg`, `turbojpeg` 라이브러리를 사용합니다.

- **8행** : `INCLUDE_PATH = -I/usr/local/cuda/include -I/opt/libjpeg-turbo/include -I/opt/libjpeg-turbo/lib64`

    전처리 과정에서 CUDA 헤더 파일을 탐색할 디렉토리를 설정합니다.

- **9행** : `LIB_PATH = -L. -L/usr/local/cuda/lib64 -L/opt/libjpeg-turbo/lib64`

    CUDA 라이브러리를 탐색할 디렉토리를 설정합니다.

- **14행** : `FRAMEWORK_LIB = ../../lib/library.a`

    프레임워크 라이브러리 아카이브 파일을 정의합니다.

- **17행~25행** : 

    ```makefile
    SRCS = \
        ../../src/Shape.cpp	\
        ../../src/LongArray.cpp	\
        ../../src/Tensor.cpp	\
        ../../src/Operator.cpp	\
        ../../src/LossFunction.cpp	\
        ../../src/Optimizer.cpp	\
        ../../src/Module.cpp	\
        ../../src/NeuralNetwork.cpp
    ```

    `.cpp` 소스 코드 파일, 아카이브 파일의 의존성 확인을 위해 정의하는 변수입니다.

- **27행** : `all: main`

    시작 타겟, `main` 파일의 의존성을 확인합니다.

- **29행~30행** :

    ```makefile
    .cpp.o:
        $(CC) $(CFLAGS) $(DFLAGS) $(ENABLE_CUDNN) $(INCLUDE_PATH) $(LIB_PATH) -c $< -o $@
    ```

    주어진 파일을 옵션들을 이용해 컴파일하여 같은 이름의 오브젝트 파일을 생성합니다.

- **32행~33행** :

    ```makefile
    main: main.o $(FRAMEWORK_LIB)
        $(NVCC) $(CFLAGS) $(ENABLE_CUDNN) $(DFLAGS) $(LFLAGS) $(INCLUDE_PATH) $(LIB_PATH) -o $@ $(FRAMEWORK_LIB) main.o
    ```

    `main.o` 파일과 `FRAMEWORK_LIB` 의 의존성을 확인하고,  옵션들을 이용해 `FRAMEWORK_LIB` 과 `main.o` 파일을 `main` 파일로 링크한다.

-**35행~36행** :

    ```makefile
    $(FRAMEWORK_LIB): $(SRC)
        make -C ../..
    ```

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
