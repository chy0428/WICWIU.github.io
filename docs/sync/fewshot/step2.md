# FaceNet 튜토리얼

!!! info

    이 글은 [**Keras** 로 **FaceNet** 을 구현하여 얼굴 인식 시스템을 개발하는 블로그 글](https://machinelearningmastery.com/how-to-develop-a-face-recognition-system-using-facenet-in-keras-and-an-svm-classifier/)을 기반으로 작성되었습니다.

**FaceNet** 은 2015년 구글에서 개발한 얼굴 인식 시스템이다. **FaceNet** 은 얼굴 인식 시스템의 학습에 사용되는 얼굴에서 특징을 고퀼리티로 추출(face enbedding) 할 수 있다.

이 튜토리얼에서는 **FaceNet** 과 SVM 분류기로 사진으로부터 사람의 얼굴을 인식하는 얼굴 인식 시스템을 어떻게 만들 수 있는지 배운다. 이 튜토리얼이 끝나면 다음을 알 수 있다.

- 구글이 어떻게 **FaceNet** 을 개발했고 어떻게 구현할 수 있는지

- 얼굴 인식 데이터셋을 어떻게 준비하는지

- 얼굴 인식 시스템으로 어떻게 얼굴 특징(face feature) 를 추출(face embedding) 하는지

- SVM 으로 face embedding 으로부터 어떻게 얼굴을 예측하는지

이 튜토리얼은 다음 단계로 이루어진다. 

1. 얼굴 인식 

2. **FaceNet** 모델

3. **FaceNet** 을 어떻게 **Keras** 로 로딩하는지

4. 어떻게 얼굴을 인식하는지

5. 어떻게 얼굴 분류 시스템을 개발하는지

## 1. 얼굴 인식

얼굴 인식의 일반적인 기능은 사진 또는 영상으로부터 자동으로 얼굴을 확인(인식)하는 것과 얼굴을 검증하는 것이다.

- 얼굴 검증 : 알려진 신원에 얼굴을 one-to-one 매핑하는 것 (이 사람이 이 사람인가?)

- 얼굴 확인(인식) : 알려진 얼굴들로부터 얼굴을 one-to-many 매핑하는 것 (이 사람이 누구인가?)

## 2. **FaceNet** 모델

**FaceNet** 은 2015년 구글의 연구원 [Florian Schroff](http://www.florian-schroff.de/) 의 논문 [FaceNet: A Unified Embedding for Face Recognition and Clustering](https://arxiv.org/abs/1503.03832) 에서 발표된 얼굴 인식 시스템이다.

**FaceNet** 은 얼굴 사진이 주어지면 얼굴로부터 고퀼리티의 특징들(features)을 추출하여 이 특징을 표현하는 128 개 원소를 갖는 벡터(face embedding )를 예측한다. **FaceNet** 은 얼굴 사진을 거리가 얼굴 유사도를 뜻하는 유클리드 공간에 매핑시킨다.

**FaceNet** 은 triplet loss 를 통한 deep CNN 이다. 이 모델로 비슷한 신원의 벡터(얼굴)는 가깝게, 다른 신원의 벡터(얼굴)는 멀게 만든다.

이 모델의 학습은 모델의 중간층으로부터 그것을 추출하는 것이 아니라 embedding 을 직접적을 만드는 것에 초점을 두었는데 이것은 중요한 혁명이다. **FaceNet** 은 이전의 접근에서 했던 것과 달리 중간의 좁은 층이 아니라 embedding 그 자체를 최적화시키는 것을 직접적으로 학습한다.

이 얼굴 embedding 은 표준 얼굴 인식 벤치마킹에서 최고의 성과를 내게 하는 분류 시스템을 학습시키는 기반이 된다.

**FaceNet** 의 논문에서는 얼굴에서 추출한 같은 얼굴의 특징을 군집화하는 등 embedding 을 다른 용도로 사용하는 방식도 보여주었다.

## 3. **Keras** 로 **FaceNet** 로딩하기

**FaceNet** 모델을 제공하는 프로젝트는 많이 있다. 가장 유명한 프로젝트는 [OpenFace](https://cmusatyalab.github.io/openface/) 인데 이 프로젝트는 **PyTorch** 를 사용하여 **FaceNet** 모델을 제공한다. 

또 유명한 프로젝트는 [FaceNet by David Sandberg](https://github.com/davidsandberg/facenet) 인데 David 는 **TensorFlow** 를 사용하여 **FaceNet** 모델을 제공한다.

주목할만한 **Keras** **FaceNet** 예제는 [FaceNet by Hiroki Taniai](https://github.com/nyoki-mtl/keras-facenet) 이다. 그는 Inception ResNet v1 을 **TensorFlow** 에서 **Keras** 로 변환해주는 스크립트를 제공했다. 또 이미 학습된 **Keras** 모델을 제공했다.

우리는 [Hiroki Taniai](https://github.com/nyoki-mtl) 가 제공한 **Keras** **FaceNet** 의 사전학습 모델을 사용해볼 것이다. 이 모델은 [MS-Celeb-1M 데이터셋](https://www.microsoft.com/en-us/research/project/ms-celeb-1m-challenge-recognizing-one-million-celebrities-real-world/) 에서 사전학습되었다. 그리고 입력된 이미지를 컬러가 되게 하고 3개의 채널에 대한 표준화된 화이트닝 된 픽셀 값을 갖게 하고 $160 \times 160$ 형상을 갖게 한다.

[여기](https://drive.google.com/drive/folders/1pwQ3H4aJ8a6yyJHZkTwtjcL4wYWQb7bn) 에서 미리 학습된 **Keras** **FaceNet** 모델을 다운로드할 수 있다. 이 `facenet_keras.h5` 을 현재 디렉토리에 위치시키자. 그리고 다음 코드를 실행하자.

## 4. 얼굴 인식하기

*참고 및 출처*: 

:   https://machinelearningmastery.com/how-to-develop-a-face-recognition-system-using-facenet-in-keras-and-an-svm-classifier/