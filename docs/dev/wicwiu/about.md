
## 설계 목표

[**WICWIU**](https://github.com/WICWIU/WICWIU) 는 국내 딥러닝 사용자들이 쉽게 이해하고 수정 및 확장이 용이한 프레임워크를 목표로 설계되었습니다. 이를 위한 [**WICWIU**](https://github.com/WICWIU/WICWIU) 의 특징은 다음과 같습니다.

1. 국내 개발자들에게 친숙한 C++을 중심으로 개발되었다. C++ 환경은 메모리 및 성능 최적화에 용이하며 다양한 환경에 이식하기도 용이하다. 

2. 확장성이 높아 사용자가 새로운 신경망 구조나 알고리즘을 구현하기 용이하다. 뉴럴 네트워크를 구성하는 연산자, 최적화 함수, 손실 함수는 모두 클래스 구조로 설계하여 사용자가 딥러닝 알고리즘의  확장/수정을 용이하게 하였다. 

3. 본 프레임워크의 코드는 문서와 주석 등을 한글로 제공하여 국내 개발자가 이해하기 쉽다. 

4. GPU를 이용한 대규모 병렬 계산을 통해 신경망을 빠른 속도로 학습할 수 있다. GPU 연산은 cuDNN과 cuda를 이용해 구현하였다. 또한, 호스트 메모리와 GPU 메모리 간 동기화를 자동으로 수행해 개발자 편의성이 우수하다.

## WICWIU 의 특징

### 네트워크 자동 미분

딥러닝을 사용하여 네트워크를 학습시키기 위해서는 손실에 대한 기울기 벡터를 구하여야 하며, 경사하강법을 사용하여서 네트워크를 최적화 하는 과정을 거쳐야 합니다.

[**WICWIU**](https://github.com/WICWIU/WICWIU) 는 사용자가 구성한 네트워크에 대해서 기울기 벡터를 손쉽게 구할 수 있도록, 각 노드마다 `BackPropagation` 메소드를 제공하고 있습니다. 또한 이 메소드는 신경망 출력부에서 역전파되는 미분을 사용한 연쇄법칙으로 전체 미분 값을 구해줍니다.

### 신경망 모델 디자인 툴

[**WICWIU**](https://github.com/WICWIU/WICWIU) 는 사용자가 딥러닝에서 사용되는 구성 요소(`Operator`, `Layer`, `Loss Function`, `Optimizer` 등)를 조합하여 신경망(Computational NeuralNetwork) 을 구성할 수 있도록 신경망 모델 디자인 툴을 제공합니다.

인터페이스의 기능은 다음과 같습니다.

-	블록 사이의 링크 연결 및 링크 추가, 링크 제거

-	블록 툴바에서 마우스 드래그를 통한 블록 생성

-	블록 선택 시 블록에 대한 정보 출력

-	블록 연결 상태 분석 (BFS 알고리즘 사용)

-	블록 연결 상태 및 블록 종류에 따라 코드 생성

## 시스템 요구사항

### 지원 플랫폼 및 운영체제

[**WICWIU**](https://github.com/WICWIU/WICWIU) 는 **Ubuntu 16.04** 환경에서 설계되었고 그 이상 버전에서 사용하는 것을 권장합니다.

### Hardware 요구사항

- Intel i5 이상의 CPU 를 사용하는 환경에서 사용하기를 권장합니다.

- CUDA 9.0, cudnn 7.0.5 을 지원하는 NVidia GPU 사용을 권장합니다.

### Software 요구사항

- C++11 이상, gcc 5.4.0 이상을 권장합니다.

- NVIDIA GPU 사용 시 설치를 요구합니다.

    - NVIDIA Grahpic Driver

    - CUDA (tested on v9.0 / 10.0)

    - cudnn (tested on v7.0.5 / 7.4.1)

# Project layout

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
