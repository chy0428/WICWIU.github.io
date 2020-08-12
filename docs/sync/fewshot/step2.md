
!!! info

    이곳은 **fewshot-learning** 을 구현하기 위한 [**WICWIU**](https://github.com/WICWIU/WICWIU) 개발팀의 [**WICWIU**](https://github.com/WICWIU/WICWIU) 분석/코딩 과정을 기록해두는 곳입니다.

[**WICWIU** 의 학습 과정은](../../dev/wicwiu/learn.md) 다음과 같이 이루어졌다는 것을 이미 알아보았습니다.

- [Step 1. 학습 데이터 &rarr; `Tensor`](step1-1.md)

- Step 2. 순전파

- [Step 3. 역전파](step3.md)

- [Step 4. Weight 파라미터 갱신](step4.md)

여기는 fewshot 팀이 "**Step 2. 순전파**" 을 구현하기 위한 과정을 기록해두는 곳입니다.

---

순전파를 구현하기 위해서는 **FaceNet** 에 대한 이해가 필요하므로 **FaceNet** 논문을 읽어야 한다. 하지만 실제 논문을 읽기 전에 얼굴 인식에 대한 배경지식이 부족하여 [**Keras** 로 **FaceNet** 을 구현하여 얼굴 인식 시스템을 개발하는 블로그 글](https://machinelearningmastery.com/how-to-develop-a-face-recognition-system-using-facenet-in-keras-and-an-svm-classifier/) 을 참고하면서 **FaceNet** 을 이해하기 위한 사전작업을 해보았다.

# FaceNet 사전지식

**FaceNet** 은 2015년 구글에서 개발한 얼굴 인식 시스템이다. **FaceNet** 은 얼굴 인식 시스템의 학습에 사용되는 얼굴에서 특징을 고퀼리티로 추출(face enbedding) 할 수 있다.

## 얼굴 인식

얼굴 인식의 일반적인 기능은 사진 또는 영상으로부터 자동으로 얼굴을 확인(인식)하는 것과 얼굴을 검증하는 것이다.

- 얼굴 검증 : 알려진 신원에 얼굴을 one-to-one 매핑하는 것 (*이 사람이 이 사람인가?*)

- 얼굴 확인(인식) : 알려진 얼굴들로부터 얼굴을 one-to-many 매핑하는 것 (*이 사람이 누구인가?*)

## **FaceNet** 모델

**FaceNet** 은 2015년 구글의 연구원 [Florian Schroff](http://www.florian-schroff.de/) 의 논문 [FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/abs/1503.03832) 에서 발표된 얼굴 인식 시스템이다.

**FaceNet** 은 얼굴 사진이 주어지면 얼굴로부터 고퀼리티의 특징들(features)을 추출하여 이 특징을 표현하는 128 개 원소를 갖는 벡터(face embedding)를 만들어낸다. 기술적으로는 각 원소가 `1` 바이트를 가지므로 각 벡터가 단지 `128` 바이트만으로 얼굴을 표현하는 것이다. **FaceNet** 은 이 face embedding 을 통하여 얼굴 사진을 거리가 얼굴 유사도를 뜻하는 유클리드 공간에 매핑시킨다.

**FaceNet** 은 triplet loss 를 통한 deep CNN 이다. 이 모델로 비슷한 신원의 벡터(얼굴)는 가깝게, 다른 신원의 벡터(얼굴)는 멀게 만든다.

이 모델의 학습은 모델의 중간층으로부터 그것을 추출하는 것이 아니라 embedding 을 직접적을 만드는 것에 초점을 두었는데 이것은 중요한 혁명이다. **FaceNet** 은 이전의 접근에서 했던 것과 달리 중간의 좁은 층이 아니라 embedding 그 자체를 최적화시키는 것을 직접적으로 학습한다.

이 얼굴 embedding 은 표준 얼굴 인식 벤치마킹에서 최고의 성과를 내게 하는 분류 시스템을 학습시키는 기반이 된다.

**FaceNet** 의 논문은 얼굴에서 추출한 같은 얼굴의 특징을 군집화하는 등 embedding 을 다른 용도로 사용하는 방식도 보여주었다.

## **FaceNet** 구현 오픈소스

**FaceNet** 모델을 제공하는 프로젝트는 많이 있다. 

- 가장 유명한 프로젝트는 [OpenFace](https://cmusatyalab.github.io/openface/) 인데 이 프로젝트는 **PyTorch** 를 사용하여 **FaceNet** 모델을 제공한다. 

- 또 유명한 프로젝트는 [FaceNet by David Sandberg](https://github.com/davidsandberg/facenet) 인데 David 는 **TensorFlow** 를 사용하여 **FaceNet** 모델을 제공한다.

- 주목할만한 **Keras** **FaceNet** 예제는 [FaceNet by Hiroki Taniai](https://github.com/nyoki-mtl/keras-facenet) 이다. 

    그는 Inception ResNet v1 을 **TensorFlow** 에서 **Keras** 로 변환해주는 스크립트를 제공했다. 또 이미 학습된 **Keras** 모델을 제공했다.

    !!! info
    
        이 모델은 [MS-Celeb-1M 데이터셋](https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/) 에서 사전학습되었다. 그리고 입력된 이미지를 컬러가 되게 하고 3개의 채널에 대한 표준화된 화이트닝 된 픽셀 값을 갖게 하고 $160 \times 160$ 형상을 갖게 한다.

        [여기](https://drive.google.com/drive/folders/1pwQ3H4aJ8a6yyJHZkTwtjcL4wYWQb7bn) 에서 미리 학습된 **Keras** **FaceNet** 모델을 다운로드할 수 있다. 

## 얼굴 인식을 위한 얼굴 탐색

실질적으로 얼굴 인식을 하기 전에 먼저 얼굴을 탐색해야만 한다. 얼굴 탐색이란 사진에서 얼굴을 자동으로 찾고 얼굴에 네모 박스를 그려서 나머지 영역들은 제외하는 작업이다.

얼굴 탐색을 위하여 MTCNN(Multi-Task Cascaded Convolutional Neural Network) 을 사용하면 좋다. 이것으로 사진에서 얼굴만 추출해낼 수 있다. MTCNN 은 2016년 논문 [Joint Face Detection and Alignment Using Multitask Cascaded Convolutional Networks](https://arxiv.org/abs/1604.02878) 에서 설명된 얼굴 탐색에 사용되는 최적의 기법이다.

### MTCNN 구현 오픈소스

- Iván de Paz Centeno 이 구현한 [ipazc/mtcnn](https://github.com/ipazc/mtcnn) 이 있는데 이것은 `pip` 로도 설치할 수 있다. 

    ```shell
    $ sudo pip install mtcnn
    ```

*참고 및 출처*: 

:   [FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/abs/1503.03832)

---

# **FaceNet** 논문을 위한 사전 수학지식

!!! info 

    이 글은 [저의 블로그 글](https://ccss17.github.io)을 재작성 한 것입니다.

## 노름거리

!!! note ""

    $L_1$ 노름(norm) 거리, 맨해튼 거리 : 벡터 $a$ 에 대한 $L_1$ 노름은 

    $$ ||a|| _{1} = |a_1| + |a_2| + |a_3| + \dots + |a_n| = \sum_{i=1}^{n}|a_i| $$

    이다. 

*Example:*

벡터 $a = (4, 3)$ 에 대한 $L_1$ 노름은 오른쪽으로 $4$, 위로 $3$ 움직인 것과 같이 $7$ 이다.

이처럼 $L_1$ 노름은 

![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/Manhattan_distance.svg/300px-Manhattan_distance.svg.png)

와 같이 바둑판 모양으로 움직인 최단거리를 뜻한다. 

!!! note ""

    $L_2$ 노름(norm) 거리, 유클리드 거리, **Squared Distance** : 벡터 $a$ 에 대한 $L_2$ 노름은 벡터의 크기에서의 정의와 동일하게 

    $$ ||a|| _{2} = \sqrt[]{\sum_{i=1}^{n}a _ i ^{2}} = \sqrt[]{a_1 ^{2}+a_2 ^{2}+\dots+a_n ^{2}} $$

    이다.

- $L_2$ 노름은 유클리드 기하학에서 사용하던 거리와 똑같고 우리가 일상생활에서 직관적으로 생각하던 거리와 동일하다.

- $L_1, L_2$ 노름은 선형회귀 모델의 정규화 항에서 사용된다.

!!! note ""

    $L_p$ 노름 : 점 $(x_1, x_2, \dots, x_n)$ 과 점 $(y_1, y_2, \dots, y_n)$ 의 $L_p$ 노름 거리는 다음과 같이 정의된다. 

    $$ \Bigg ( \sqrt[]{\sum_{i=1}^{n}|x_i - y_i| ^{p}} \Bigg ) ^{1/p} $$

$L_1$ 노름 거리가 

$$ \sum_{i=1}^{n}|x_i - y_i| ^{p} $$

로 정의되고 $L_2$ 노름 거리가 

$$ \Bigg ( \sqrt[]{\sum_{i=1}^{n}|x_i - y_i| ^{2}} \Bigg ) ^{1/2} $$

로 정의된 것에서 일반화 된 것이다. 

!!! note ""

    무한 $L _{\infty }$ 노름, 체비쇼프 거리(chebyshev distance) : 점 $(x_1, x_2, \dots, x_n)$ 과 점 $(y_1, y_2, \dots, y_n)$ 의 $L _{\infty }$ 노름 거리는 다음과 같이 정의된다. 

    $$ \lim_{p \to \infty}  \Bigg ( \sqrt[]{\sum_{i=1}^{n}|x_i - y_i| ^{p}} \Bigg ) ^{1/p} $$

    또는

    $$ = \max (|x_1 -y_1|, |x_2 - y_2|, \dots, |x_n - y_n|) $$

- 보통 $L_1$ 노름거리과 $L_2$ 노름거리, 무한 노름거리 외에는 잘 사용되지 않는다. 

## 폐구간

!!! note ""

    구간(interval) : 두 실수 $a, b(a<b)$ 에 대하여 실수의 집합 

    $$\{x \in \mathbb{R} |a \leq x \leq b\}, \{x \in \mathbb{R} |a < x < b\}, \{x \in \mathbb{R}  | a \leq x < b\}, \{x \in \mathbb{R} |a<x \leq b\}$$

    를 구간이라 한다. 

기호로 각각 $[a,b], (a,b), [a,b), (a,b]$ 라 한다.

구간은 수로 그 특성 혹은 존재자체를 수로 추상화할 수 있는 자연의 모든 대상의 집합을 마찬가지로 수로 격하될 수 있는 자연의 어떤 대상을 기준으로 하여 나눈 것에 대응된다.

!!! note ""

    폐구간(닫힌구간, closed interval) : $[a,b]$ 를 닫힌구간이라 한다. 

즉, $[a,b] = \{x \in \mathbb{R} | a \leq x \leq b\}$ 이다. 

!!! note ""

    개구간(열린구간, open interval) : $(a,b)$ 를 열린구간이라 한다. 

즉, $(a,b) = \{x \in \mathbb{R} | a < x < b\}$ 이다. 

특히 실수 전체의 집합도 하나의 구간으로 보고 개구간 $(-\infty, \infty)$ 로 나타낸다. 

!!! tip

    $\infty$ 는 특정한 값이 아니고 "한없이 커지고 있는 상태" 를 나타내기 때문에 $[-\infty, \infty]$ 나 $(a, \infty]$ 와 같이 $\infty$ 를 폐구간과 엮지 않는다. 실수 $x$ 의 값이 한없이 커질 수는 있어도 $x = \infty$ 라는 값을 가질 수는 없기 때문이다. 

*참고 및 출처*: 

:   [저의 블로그 ㅎㅎ - 벡터](https://ccss17.github.io/vector.html)

:   [저의 블로그 ㅎㅎ - 해석](https://ccss17.github.io/anal.html)

---

# 《FaceNet: A Unified Embedding for Face Recognition and Clustering》 

## Abstract

우리는 이 논문에서 얼굴 유사도가 거리인 유클리드 공간으로 얼굴 사진을 사상(mapping)시키는 것을 학습하는 **FaceNet** 이라는 시스템을 소개한다. 얼굴 유사도가 거리인 유클리드 공간이 생성되면 얼굴 검증(*같은 사람인가?*), 얼굴 확인(*누구인가?*), 얼굴 군집화(*비슷한 얼굴을 모으는 것*)가 매우 쉬워진다.

얼굴 유사도가 거리인 유클리드 공간을 만들기 위하여 우리는 deep convolutional network 를 사용하여 중간층을 최적화(학습)하는 것이 아닌 embedding(얼굴에서 추출한 벡터) 자체를 직접적으로 최적화(학습)시켰다. 학습을 위하여 triplets 을 사용하였다. 이로써 우리는 얼굴 하나당 단지 `128` 바이트를 사용하여 현존하는 얼굴 인식 시스템 중 최고의 성능을 이끌어낼 수 있었다.

우리는 또한 harmonic embeddings 과 harmonic triplet loss 라는 또 다른 얼굴 embedding 방법을 소개한다. 이 두 embedding 방식을 서로 비교할 수 있을 것이다.

## 1. Introduction

우리는 deep convolutional network 를 사용하여 이미지의 유클리드 embedding 을 학습한다. 이 network 는 얼굴 유사도가 곧 $L2$ 거리인 embedding 공간을 학습하게 된다. 

![image](https://user-images.githubusercontent.com/16812446/89868084-2f913900-dbed-11ea-87f1-1d5a9e2db615.png)

:   *Figure 1. Illumination and Pose invariance ([FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/abs/1503.03832))*

위 그림을 보자. 수평으로는 같은 인물의 사진이고 수직으로는 다른 인물의 사진이다. 또한 수평으로는 다른 포즈를 취하고 있다. 이때 두 사진간의 유사도, 즉 거리가 $1.04, 1.22, 1.33, \dots$ 등으로 계산된 것이다. 이 값은 폐구간 $[0, 4]$ 에 존재한다. 값이 $0.0$ 이면 얼굴이 똑같음을 의미하고 값이 $4.0$ 이면 얼굴이 다르다는 것을 의미한다.

이 공간이 생성되면 얼굴 인식 시스템의 고전적인 문제들의 해결이 매우 쉬워진다. 얼굴 검증은 단지 두 embedding 간의 thresholding 을 정하는 것으로 귀결되고, 얼굴 확인은 k-NN 분류기의 문제가 되며, 얼굴 군집화는 k-mean 나 agglomerative clustering 같은 off-the-shelf 기술로 해결할 수 있다. 

!!! example

    *Figure 1.* 에서 thresholding 을 $1.1$ 로 두면 모든 얼굴 사진을 잘 분류할 수 있다는 것을 알 수 있다.

### FaceNet 과 지금까지의 얼굴 인식 접근법과의 차이

지금까지의 얼굴 인식 접근법은 신경망의 중간층을 학습시키는 것이었다. 이 방식의 단점은 간접적이고, 비효율적이라는 것이다. 이 방식에서는 중간층이 새로운 얼굴도 잘 인식하길 바라는 것이었다. 그리고 얼굴을 나타내는 사이즈가 거의 `1000` 차원 정도로 매우 컸다. 

반면 **FaceNet** 은 [LMNN](http://john.blitzer.com/papers/nips05.pdf) 을 기반으로 한 triplet-based 손실함수를 통하여 얼굴을 `128` 차원으로 embedding 시킨다. triplet 은 매칭되는 얼굴 썸네일과 매칭되지 않는 얼굴 썸네일, 그리고 positive pair 를 distance margin 으로 negative 로부터 분리시키기 위한 손실값으로 구성된다. 썸네일이란 얼굴 영역만 잘려진 사진을 뜻한다. 이 썸네일은 스케일 조정과 이미지 변환이 이루어질 수도 있다.

### triplets 선정

어떤 triplets 을 사용할지 선정하는 것은 좋은 성능을 위하여 매우 중요하다.

1. [Curriculum learning [1]](https://www.icml.cc/Conferences/2009/papers/119.pdf) 에서 착안하여 우리는 triplets 의 어려움을 지속적으로 증가시키는 online negative exemplar mining 전략을 소개한다. 

2. 또한 군집화의 정확도를 향상시키기 위하여 한 사람의 embeddings 을 위한 구형 군집화를 이루는 hard-positive mining 기술을 소개한다.

이로써 *Figure 1.* 같은 사진들도 잘 분류할 수 있다. 솔직히 이걸 분류하는 건 겁나 어려운 문제인데 우리는 해냈다.

### 논문 구조 설명

먼저 **2.** 에서 이 연구분야와 관련된 논문들을 리뷰해본다. **3.1** 에서는 triplet loss 를 정의해본다. **3.2** 에서는 우리의 triplet 선정 방식과 모델 학습 절차를 설명한다. **3.3** 에서 모델 구조 사용에 대하여 설명한다. **4.** 과 **5.** 에서 우리의 방식으로 embedding 을 한 것을 정량적 방식으로 결과를 내보고, 정성적 방식으로 군집화 결과를 확인해본다. 

## 2. Related Work

[Deeply  learned  facerepresentations  are  sparse,  selective,  and  robust [15]](https://arxiv.org/pdf/1412.1265) 와 [Deepface:Closing the gap to human-level performance in face verifica-tion [17]](https://www.cs.toronto.edu/~ranzato/publications/taigman_cvpr14.pdf) 와 비슷하게 우리도 순수하게 data driven method 를 사용하여 얼굴 사진의 픽셀로부터 그것을 특정할 수 있는 특징을 학습했다. 우리는 라벨링 된 얼굴 데이터셋에서 가변하는 포즈, 명도, 다양한 조건에서 불변하는 특성을 얻었다.

본 논문에서는 컴퓨터 비전에서 좋은 성과를 내고 있는 두 가지 신경망 구조를 설명한다. 두 개 다 deep convolutional network 이다. 하나는 [Backpropagation Applied to Handwritten Zip Code Recognition [8]](http://yann.lecun.com/exdb/publis/pdf/lecun-89e.pdf) 이고 하나는 [Learningrepresentations by back-propagating errors [11]](https://www.iro.umontreal.ca/~vincentp/ift3395/lectures/backprop_old.pdf) 이다.

첫번째 모델은 여러개의 interleaved convolutional layers 와 non-linear activations 과 local response normalizations 와 max pooling layers 로 구성된 [Visualizing and understandingconvolutional networks [22]](https://cs.nyu.edu/~fergus/papers/zeilerECCV2014.pdf) 의 모델을 기반으로 한다. 우리는 [Network in network [9]](https://arxiv.org/abs/1312.4400) 에서 착안하여 몇몇의 $1 \times 1 \times d$ convolutional layers 를 추가했다.

두번째 모델은 ImageNet 2014 에서 사용된 Szegedy 의 Inception model [Going deeper with convolutions [16]](https://arxiv.org/pdf/1409.4842) 을 기반으로 한다. 이 모델은 병행해서 실행되는 몇 개의 다른 convolutional 과 pooling layers 가 섞인 layers 를 사용하고 그것들의 출력을 합친다. 

## 3. Method

![image](https://user-images.githubusercontent.com/16812446/89889612-e224c400-dc0c-11ea-8770-bb603c6a7436.png)

:   *Figure 2. 모델 구조. FaceNet 은 배치 입력층, deep CNN 층, embedding 을 출력하는 $L_2$ normalization 층, triplet loss 층으로 구성된다. ([FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/abs/1503.03832))*

![image](https://user-images.githubusercontent.com/16812446/89889512-af7acb80-dc0c-11ea-8604-6b274ebe621e.png)

:   *Figure 3. Triplet Loss 는 같은 신원을 가진 anchor 와 positive 의 거리를 최소화 시키고 다른 신원을 가진 anchor 와 negative 의 거리를 최대화 시킨다. ([FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/abs/1503.03832))*

**FaceNet** 은 deep convolutional network 를 사용한다. 우리는 두 가지 핵심 구조를 논의할 것이다. 첫째는 [Visualizing and understandingconvolutional networks [22]](https://cs.nyu.edu/~fergus/papers/zeilerECCV2014.pdf) 스타일의 networks 이고 둘째는 [Going deeper with convolutions [16]](https://arxiv.org/pdf/1409.4842) 의 Inception 타입의 networks 이다. 이 networks 의 자세한 설명은 **3.3** 에서 한다. 이 모델을 *Figure 2.* 에서 회색박스로 표현했다. 

*Figure 2.* 에서 볼 수 있듯 가장 중요한 것은 어떻게 얼굴 사진을 그 특징을 대표할 수 있는 벡터로 변환하느냐이다. 즉, 우리는 얼굴 사진 $x$ 을 ^^조건(포즈, 명도 등)에 관계없이 모든 얼굴 사진에 대하여 같은 신원의 $L_2$ 거리는 작고 다른 신원의 $L_2$ 거리는 먼 feature space $\mathbb{R}^{d}$ 에 사상시키는 함수 $f(x)$^^ 을 찾아볼 것이다.

여기에서 다른 손실 함수와 triplet 을 비교해보지는 않겠지만, 그래도 triplet 이 얼굴 검증에는 가장 좋을 것이다.

### 3.1. Triplet Loss

### 3.2. Triplet Selection

### 3.3. Deep Convolutional Networks

## 4. Datasets and Evaluation

### 4.1. Hold-out Test Set

### 4.2. Personal Photos

### 4.3. Academic Datasets

## 5. Experiments

### 5.1. Computation Accuracy Trade-off

### 5.2. Effect of CNN Model

### 5.3. Sensitivity to Image Quality

### 5.4. Embedding Dimensionality

### 5.5. Amount of Training Data

### 5.6. Performance on LFW

### 5.7. Performance on Youtube Faces DB

### 5.8. Face Clustering

## 6. Summary

## 7. Harmonic Embedding

### 7.1. Harmonic Triplet Loss

### 7.2. Summary

*참고 및 출처*: 

:   [FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/abs/1503.03832)