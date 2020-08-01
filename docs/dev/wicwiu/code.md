
이곳에서는 이전에 설명한 [**WICWIU**](https://github.com/WICWIU/WICWIU) 로 신경망을 구성하고, [**WICWIU**](https://github.com/WICWIU/WICWIU) 로 딥러닝을 하는 것을 코드로 함께 보면서 이해해보겠습니다.

# WICWIU 코드 살펴보기

## Compile

이 단락에서는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 를 컴파일하고 라이브러리를 생성하는 `makefile` 들이 어떻게 구성되었는지 같이 살펴보겠습니다.

### Compile `src/` 

`src/` 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 라이브러리 디렉토리입니다. 이것을 컴파일하는 `makefile` 를 같이 살펴보겠습니다.

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