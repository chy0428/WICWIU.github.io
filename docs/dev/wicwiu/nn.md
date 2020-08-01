
이곳에서는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 가 어떻게 인공신경망을 구성하는지 설명합니다.

# 인공신경망 구성하기

## 데이터 구조

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89108189-6474f180-d471-11ea-94cb-17d40a924109.png" width="70%" />
  <figcaption><i>Tensor, Shape, LongArray 데이터 형식 요약</i></figcaption>
</figure>

### Class `Tensor`

: Class `Tensor` : [**WICWIU**](https://github.com/WICWIU/WICWIU) 에서 인공 신경망 모델의 학습에 이용되는 ^^데이터의 기본 형식^^ 입니다.

`Tensor` 클래스는 최대 5의 계수(Rank)를 갖는 텐서를 지원합니다. 텐서의 각 축은 인공 신경망 학습에서 ^^Time, Batch, Row, Column 축에 해당^^ 합니다.

`Tensor` 클래스는 ^^텐서의 차원에 관한 정보를 담고 있는 `Shape` 클래스와 각 차원의 개별 데이터를 담고 있는 `LongArray` 클래스^^ 를 멤버 변수로 갖습니다. `Tensor` 클래스는 `Shape` 클래스의 차원 정보 데이터를 활용해 각 차원의 개별 데이터를 담고 있는 메모리에 접근합니다. 

!!! info 

    [Tensor](https://ko.wikipedia.org/wiki/%ED%85%90%EC%84%9C) 는 물리학의 개념을 차용, 다차원의 정보를 갖는 데이터를 의미합니다. 

### Class `Shape`

: Class `Shape` : `Tensor` 데이터의 차원에 관한 정보를 담고 있는 클래스입니다. 
    
`Shape` 클래스는 ^^텐서의 계수(Rank)를 담고 있는 변수와 계수 각 축의 차원 정보를 담고 있는 변수^^ 를 멤버 변수로 갖고 있습니다.

계수 변수의 최댓값은 `5` 이고, 각 축은 인공 신경망 학습에서 Time, Batch, Channel, Row, Column 축으로 활용됩니다. 각 ^^축의 차원 정보에 해당하는 변수는 포인터로 선언^^ 되어 있으며, 축의 개수만큼 배열로서 동적으로 할당되어 축의 차원 정보를 나타냅니다. 

### Class `LongArray`

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89108533-3513b400-d474-11ea-881b-3ceb8dd2772e.png" width="70%" />
  <figcaption><i>LongArray 클래스의 위계적 데이터 구조</i></figcaption>
</figure>

: Class `LongArray` : High-dimensional Array 의 약어로, 실제 각 차원의 개별 데이터를 담고 있는 클래스입니다.
    
`LongArray` 클래스의 데이터들은 ^^동적으로 한 번에 할당했을 때 메모리가 부족해 할당이 불가하는 경우를 막기 위해 위계적 구조를 가지고 이중 포인터를 이용하여 선언^^ 되어 있습니다.

논리적으로는 하나의 연속적인 배열이나 물리적으로는 블록으로 나누어져 메모리에 할당됩니다. 각 블록은 Time 축을 기준으로 그 외 나머지 4개의 차원(Batch, Channel, Row, Column)을 갖는 데이터로 분리됩니다.

## 인공신경망 구성 클래스

### Class `Operator`

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89108602-d8fd5f80-d474-11ea-83c7-a2d05cead642.png" width="70%" />
  <figcaption><i> Operator 클래스의 기본 구조
  </i></figcaption>
</figure>

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89108636-ee728980-d474-11ea-90e0-b547c5eb8d40.png" width="90%" />
  <figcaption><i> Operator 클래스 간 네트워크 연결 </i></figcaption>
</figure>

: Class `Operator` : 인공신경망 안에서 저수준의 기본 연산을 수행하기 위한 클래스입니다. 
    
`Operator` 클래스는 ^^인공신경망의 노드를 구성하는 가장 작은 단위^^ 입니다. 

`Operator` 클래스는 네트워크 구성을 위해 각각 ^^연산의 입력 방향과 출력 방향에 대해서 `Operator` 클래스에 대한 포인터를 저장하는 Container 를 멤버 변수^^ 로 갖습니다.

!!! note

    Container 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 에서 정의한 큐와 비슷한 자료 구조입니다. 

또한 인공 신경망의 순전파와 역전파를 수행하기 위해 연산의 결과 값과 기울기 벡터를 저장하기 위한 `Tensor` 클래스에 대한 포인터를 저장하는 Container 를 멤버 변수로 갖습니다. 순전파와 역전파에서 사용되는 Weight 파라미터들은 후에 기술할 `NeuralNetwork` 클래스가 포인터들의 Container 로 가지고 있으며, `Operator` 클래스에게 전달합니다. 파생 클래스들은 해당 클래스를 상속하여 각 연산의 기능을 수행합니다.

### Class `Module` 

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89108752-fed73400-d475-11ea-9b1d-905d7f1a4e05.png" width="100%" />
  <figcaption><i>Module 클래스의 기본 구조 예시</i></figcaption>
</figure>

: Class `Module` : 단일 `Operator` 클래스로는 수행할 수 없는 고수준의 복합 연산을 수행하기 위한 클래스입니다. 

`Module` 클래스는 ^^`Operator` 클래스를 상속^^ 받으며, 복수의 `Operator` 들을 조합하여 서브 그래프를 구성하고 연산을 수행합니다. 

`Module` 클래스는 **너비 우선 탐색(Breadth-First Search)** 방식을 이용해 서브 그래프를 구성하고 연산합니다. `Module` 클래스는 다른 `Module` 클래스를 포함하는 재귀적 구조를 형성할 수 있다. `Module` 클래스는 ^^하나의 단일 `Operator` 클래스와 같이 기능 및 동작^^ 한다. 파생 클래스들은 해당 클래스를 상속하여 각 연산의 기능을 수행한다.

## 신경망 학습 클래스

### Class `LossFunction`

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89108807-7f963000-d476-11ea-8c14-7db61d009a1f.png" width="90%" />
  <figcaption><i> LossFunction 클래스의 기본 구조 </i></figcaption>
</figure>

: Class `LossFunction` : `NeuralNetwork` 의 순전파를 통해 얻어진 최종 출력 `Tensor` 와 `NeuralNetwork` 로부터 전달 받은 입력 데이터에 대한 레이블 값을 비교하여 손실 함수 값을 계산하는 클래스입니다. 

`Operator` 클래스와는 구분된 독립적인 클래스이며, ^^기울기 벡터를 계산하여 `NeuralNetwork` 의 역전파의 시작 부분을 담당^^ 합니다. 파생 클래스들은 해당 클래스를 상속하여 각 손실 함수의 기능을 수행한다.

### Class `Optimizer`

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89108835-c7b55280-d476-11ea-9b4a-e053e52935a1.png" width="90%" />
  <figcaption><i> NeuralNetwork 클래스 내 학습 파라미터의 기본 구조 </i></figcaption>
</figure>

: `Optimizer` 클래스 : ^^최적화 알고리즘을 활용해 Weight 파라미터를 업데이트^^ 하는 클래스입니다.

인공신경망 모델의 역전파 시, 손실 함수에서 계산된 값에 대해서 각 학습 파라미터의 기울기 벡터가 `Tensor` 형태로 계산된다. `Optimizer` 클래스는 이 기울기 벡터에 대한 `Tensor` 들의 포인터를 Container 로 가지고 있습니다. 파생 클래스들은 해당 클래스를 상속하여 각 Optimizer의 기능을 수행한다. 

## 신경망 구성

### Class `NeuralNetwork`

<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89109037-963d8680-d478-11ea-8d89-248ce99b8a01.png" width="70%" />
  <figcaption><i>NeuralNetwork 클래스 그래프 예시</i></figcaption>
</figure>

: `NeuralNetwork` 클래스 : 앞에서 설명했던 요소들을 조합하여, 학습 가능한 신경망 모델을 구성하는 클래스입니다. 

`NeuralNetwork` 클래스는 하나의 그래프를 구성하는 `Operator(Module)` 클래스 포인터에 대한 Container 를 가지고 있습니다. `Operator(Module)` 클래스들이 구성하는 그래프는 인공신경망 모델에 대응됩니다.

`NeuralNetwork` 클래스는 너비 우선 탐색(Breadth-first Search) 방식으로 각 `Operator` 클래스들에 접근합니다. `NeuralNetwork` 클래스는 `LossFunction` 클래스를 이용해 손실 함수의 값을 계산하고, `Optimizer` 클래스의 최적화 알고리즘을 이용해 인공 신경망을 최적화한다. `NeuralNetwork` 클래스는 Weight 파라미터에 대한 포인터의 Container 를 가지고 있으며, 역전파 및 최적화 시 활용한다. `NeuralNetwork` 클래스를 이용한 학습 진행 방식의 자세한 내용은 후술하였다. 