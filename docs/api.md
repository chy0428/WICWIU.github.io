# Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`class `[`AdagradOptimizer`](#classAdagradOptimizer) | 
`class `[`Adam`](#classAdam) | 
`class `[`AdamOptimizer`](#classAdamOptimizer) | 
`class `[`Addall`](#classAddall) | 값들을 서로 더하는 class
`class `[`AddChannelWise`](#classAddChannelWise) | 서로 더하는 class
`class `[`AddColWise`](#classAddColWise) | 중 Colunm에만 값을 더하는 class
`class `[`AvaragePooling2D`](#classAvaragePooling2D) | 
`class `[`BatchNormalize`](#classBatchNormalize) | 
`class `[`BatchNormalizeLayer`](#classBatchNormalizeLayer) | 구성해 Batch Normalization Layer의 기능을 수행하는 모듈을 생성하는 클래스
`class `[`BEGAN`](#classBEGAN) | 
`class `[`BEGANDiscriminatorLoss`](#classBEGANDiscriminatorLoss) | 
`class `[`BEGANGeneratorLoss`](#classBEGANGeneratorLoss) | 
`class `[`ConcatenateChannelWise`](#classConcatenateChannelWise) | 
`class `[`Container`](#classContainer) | 저장하기 위한 Queue에 해당하는 클래스
`class `[`Convolution2D`](#classConvolution2D) | 
`class `[`ConvolutionLayer2D`](#classConvolutionLayer2D) | 구성해 2-Dimensional Convolution Layer의 기능을 수행하는 모듈을 생성하는 클래스
`class `[`CrossEntropy`](#classCrossEntropy) | Metric를 이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스
`class `[`DataLoader`](#classDataLoader) | 
`class `[`Dataset`](#classDataset) | 
`class `[`Dropout`](#classDropout) | 
`class `[`FewShotClassifier`](#classFewShotClassifier) | 
`class `[`GAN`](#classGAN) | 
`class `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator) | 
`class `[`GlobalAvaragePooling2D`](#classGlobalAvaragePooling2D) | Row * Colunm 공간을 GlobalAvaragePooling하는 클래스.
`class `[`GradientDescentOptimizer`](#classGradientDescentOptimizer) | 
`class `[`HingeLoss`](#classHingeLoss) | Metric를 이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스
`class `[`KNearestNeighbor`](#classKNearestNeighbor) | 
`class `[`Linear`](#classLinear) | 구성해 fully connected layer의 기능을 수행하는 모듈을 생성하는 클래스
`class `[`LongArray`](#classLongArray) | 데이터를 저장하고 관리하는 클래스.
`class `[`LossFunction`](#classLossFunction) | 손실 함수를 계산하는 클래스
`class `[`LRelu`](#classLRelu) | 
`class `[`MatMul`](#classMatMul) | 
`class `[`Maxpooling2D`](#classMaxpooling2D) | 
`class `[`Module`](#classModule) | 구성해 모듈화하는 클래스
`class `[`MSE`](#classMSE) | Squared Error) Metric를 이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스
`class `[`NagOptimizer`](#classNagOptimizer) | 
`class `[`NeuralNetwork`](#classNeuralNetwork) | 모델 생성, 학습 및 평가를 총괄하는 클래스
`class `[`NoiseGenerator`](#classNoiseGenerator) | [Tensor](#classTensor) 클래스의 Random_normal 함수를 사용하여 범위 내의 임의의 값을 갖는 [Tensor](#classTensor) 생성
`class `[`Operator`](#classOperator) | 본 프래임워크의 가장 작은 연산 단위.
`class `[`Optimizer`](#classOptimizer) | 
`class `[`PRelu`](#classPRelu) | 
`class `[`ReconstructionError`](#classReconstructionError) | 
`class `[`Recurrent`](#classRecurrent) | 
`class `[`Relu`](#classRelu) | 
`class `[`ReShape`](#classReShape) | 
`class `[`RMSPropOptimizer`](#classRMSPropOptimizer) | 
`class `[`Sequential`](#classSequential) | 
`class `[`Shape`](#classShape) | 정보를 담고 있는 Shape을 저장하고 관리하는 클래스
`class `[`Sigmoid`](#classSigmoid) | 
`class `[`Softmax`](#classSoftmax) | 
`class `[`SoftmaxCrossEntropy`](#classSoftmaxCrossEntropy) | 이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스
`class `[`Switch`](#classSwitch) | 
`class `[`Tanh`](#classTanh) | 
`class `[`Tensor`](#classTensor) | 저장하고 관리하는 클래스
`class `[`Tensorholder`](#classTensorholder) | Result만 사용하기 위한 클래스.
`class `[`TransposedConvolution2D`](#classTransposedConvolution2D) | 
`class `[`TransposedConvolutionLayer2D`](#classTransposedConvolutionLayer2D) | 구성해 2-Dimensional TransposedConvolution Layer의 기능을 수행하는 모듈을 생성하는 클래스
`class `[`TripletLoss`](#classTripletLoss) | 
`class `[`UniformNoiseGenerator`](#classUniformNoiseGenerator) | 
`class `[`VanillaGANDiscriminatorLoss`](#classVanillaGANDiscriminatorLoss) | 
`class `[`VanillaGANGeneratorLoss`](#classVanillaGANGeneratorLoss) | 
`class `[`WData`](#classWData) | 
`class `[`WGANDiscriminatorLoss`](#classWGANDiscriminatorLoss) | 
`class `[`WGANGeneratorLoss`](#classWGANGeneratorLoss) | 

# class `AdagradOptimizer` {#classAdagradOptimizer}

```
class AdagradOptimizer
  : public Optimizer< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`AdagradOptimizer`](#classAdagradOptimizer_1a57ec3fb8b88c955719598afba8dc7a85)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,OptimizeDirection pOptimizeDirection)` | [AdagradOptimizer](#classAdagradOptimizer) 생성자.
`public inline  `[`AdagradOptimizer`](#classAdagradOptimizer_1a43f6c5b1975640a30a562ad377cdf877)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float epsilon,OptimizeDirection pOptimizeDirection)` | [AdagradOptimizer](#classAdagradOptimizer) 생성자.
`public inline  `[`~AdagradOptimizer`](#classAdagradOptimizer_1a9b28f6ca7f58bd151f44e5043d2735b2)`()` | [AdagradOptimizer](#classAdagradOptimizer) 소멸자
`public inline void `[`Delete`](#classAdagradOptimizer_1aa4c51cf728ca90d2aa6bc71d1c4f22d6)`()` | Optimizer의 Delete 매소드
`public inline int `[`Alloc`](#classAdagradOptimizer_1a15d0e89567fdbffd4fd2076dbee6f286)`()` | 
`public inline int `[`Alloc`](#classAdagradOptimizer_1ae8b0d226a29ac5716fbffe0add5000ed)`(float epsilon)` | Optimizer의 Alloc 매소드
`public inline void `[`InitializeAttributeForGPU`](#classAdagradOptimizer_1addf7ab70645c4d0e5966b8fb72f31b93)`(unsigned int idOfDevice)` | 
`public inline virtual int `[`UpdateParameter`](#classAdagradOptimizer_1a770179d3d869898282bb7397e93003fb)`()` | 파라미터 값들을 업데이트 하는 메소드
`public inline virtual int `[`UpdateParameter`](#classAdagradOptimizer_1a60131cf4400fbc376bb584a6652f1723)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` | UpdateParameter default 함수
`public inline int `[`UpdateParameter`](#classAdagradOptimizer_1af728a868bb4faf9885d9b2707ebd04ef)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * m_pGradientSquared)` | 파라미터 값들을 업데이트 하는 메소드

## Members

#### `public inline  `[`AdagradOptimizer`](#classAdagradOptimizer_1a57ec3fb8b88c955719598afba8dc7a85)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,OptimizeDirection pOptimizeDirection)` {#classAdagradOptimizer_1a57ec3fb8b88c955719598afba8dc7a85}

[AdagradOptimizer](#classAdagradOptimizer) 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pLearningRate` Optimizer의 learning rate 

* `epsilon` 분모 값이 0이 되는 것을 방지 하는 값 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(epsilon)

#### `public inline  `[`AdagradOptimizer`](#classAdagradOptimizer_1a43f6c5b1975640a30a562ad377cdf877)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float epsilon,OptimizeDirection pOptimizeDirection)` {#classAdagradOptimizer_1a43f6c5b1975640a30a562ad377cdf877}

[AdagradOptimizer](#classAdagradOptimizer) 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pLearningRate` Optimizer의 learning rate 

* `epsilon` 분모 값이 0이 되는 것을 방지 하는 값 

* `weightDecayRate` 가중치 매개변수가 클 때 패널티를 부과하는 값 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(epsilon)

#### `public inline  `[`~AdagradOptimizer`](#classAdagradOptimizer_1a9b28f6ca7f58bd151f44e5043d2735b2)`()` {#classAdagradOptimizer_1a9b28f6ca7f58bd151f44e5043d2735b2}

[AdagradOptimizer](#classAdagradOptimizer) 소멸자

#### Returns
없음

#### `public inline void `[`Delete`](#classAdagradOptimizer_1aa4c51cf728ca90d2aa6bc71d1c4f22d6)`()` {#classAdagradOptimizer_1aa4c51cf728ca90d2aa6bc71d1c4f22d6}

Optimizer의 Delete 매소드

맴버 변수 m_aaGradientSquared 메모리 할당을 해제한다. 
#### Returns
없음

#### `public inline int `[`Alloc`](#classAdagradOptimizer_1a15d0e89567fdbffd4fd2076dbee6f286)`()` {#classAdagradOptimizer_1a15d0e89567fdbffd4fd2076dbee6f286}

#### `public inline int `[`Alloc`](#classAdagradOptimizer_1ae8b0d226a29ac5716fbffe0add5000ed)`(float epsilon)` {#classAdagradOptimizer_1ae8b0d226a29ac5716fbffe0add5000ed}

Optimizer의 Alloc 매소드

맴버 변수 m_ppParameter, m_numOfParameter, m_ppParameter, m_aaGradientSquared 초기화한다.

m_aaGradientSquared m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다. 
#### Parameters
* `epsilon` 분모 값이 0이 되는 것을 방지 하는 값 

#### Returns
성공 시 TRUE 

**See also**: [Container](#classContainer)<[Operator<DTYPE>](#classOperator) *>* GetTrainableTensor() 

**See also**: int GetTrainableTensorDegree()

#### `public inline void `[`InitializeAttributeForGPU`](#classAdagradOptimizer_1addf7ab70645c4d0e5966b8fb72f31b93)`(unsigned int idOfDevice)` {#classAdagradOptimizer_1addf7ab70645c4d0e5966b8fb72f31b93}

#### `public inline virtual int `[`UpdateParameter`](#classAdagradOptimizer_1a770179d3d869898282bb7397e93003fb)`()` {#classAdagradOptimizer_1a770179d3d869898282bb7397e93003fb}

파라미터 값들을 업데이트 하는 메소드

m_epsilon 유무에 따라 UpdateParameter 호출과 에러 메세지 호출 
#### Returns
성공 시 TRUE 

**See also**: int [UpdateParameter(Operator<DTYPE> *pParameter, Tensor<DTYPE> *m_pGradientSquared)](#classAdagradOptimizer_1af728a868bb4faf9885d9b2707ebd04ef)

#### `public inline virtual int `[`UpdateParameter`](#classAdagradOptimizer_1a60131cf4400fbc376bb584a6652f1723)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` {#classAdagradOptimizer_1a60131cf4400fbc376bb584a6652f1723}

UpdateParameter default 함수

#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

#### Returns
성공 시 TRUE

#### `public inline int `[`UpdateParameter`](#classAdagradOptimizer_1af728a868bb4faf9885d9b2707ebd04ef)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * m_pGradientSquared)` {#classAdagradOptimizer_1af728a868bb4faf9885d9b2707ebd04ef}

파라미터 값들을 업데이트 하는 메소드

gradient 제곱 값으로 pGradientSquared 업데이트

signed_learning_rate와 gradient의 곱을 업데이트 된 pGradientSquared값에 root를 적용 한 값으로 나누어 파라미터를 업데이트 한다. 
#### Parameters
* `pGradientSquared` 업데이트 할 pGradientSquared 

#### Returns
성공 시 TURE

# class `Adam` {#classAdam}

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------

## Members

# class `AdamOptimizer` {#classAdamOptimizer}

```
class AdamOptimizer
  : public Optimizer< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`AdamOptimizer`](#classAdamOptimizer_1af21a930d69dbc8ac3a539019c2e0cb34)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float Beta1,float Beta2,float epsilon,OptimizeDirection pOptimizeDirection)` | AdamOptimizer의 생성자.
`public inline  `[`AdamOptimizer`](#classAdamOptimizer_1ac06df8f4edbbf0d567e496f09dccfce6)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float Beta1,float Beta2,float epsilon,float weightDecayRate,OptimizeDirection pOptimizeDirection)` | AdamOptimizer의 생성자.
`public inline  `[`~AdamOptimizer`](#classAdamOptimizer_1add0faced6d3126163acfc4e0c36fa294)`()` | [AdamOptimizer](#classAdamOptimizer) 소멸자
`public inline virtual void `[`Delete`](#classAdamOptimizer_1a826c98d4c1b0182ad571e3d4ebcdd9a4)`()` | Optimizer의 Delete 매소드
`public inline int `[`Alloc`](#classAdamOptimizer_1acef5cf04a176f41e9ce0db58bcdc4119)`(float Beta1,float Beta2,float epsilon)` | Optimizer의 Alloc 매소드
`public inline virtual int `[`UpdateParameter`](#classAdamOptimizer_1a8587c95667564353e1649bfe4c2c34e2)`()` | 파라미터 값들을 업데이트 하는 메소드
`public inline virtual int `[`UpdateParameter`](#classAdamOptimizer_1a92911ca3e755b8028a02ee21a57b8c2d)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` | UpdateParameter default 함수
`public inline int `[`UpdateParameter`](#classAdamOptimizer_1a6ee9461e547e56ee60153a53b4ecf246)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * pFirstMomentum,`[`Tensor`](#classTensor)`< DTYPE > * pFirstVelocity,`[`Tensor`](#classTensor)`< DTYPE > * pUnbiasedMomentum,`[`Tensor`](#classTensor)`< DTYPE > * pUnbiasedVelocity)` | 파라미터 값들을 업데이트 하는 메소드

## Members

#### `public inline  `[`AdamOptimizer`](#classAdamOptimizer_1af21a930d69dbc8ac3a539019c2e0cb34)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float Beta1,float Beta2,float epsilon,OptimizeDirection pOptimizeDirection)` {#classAdamOptimizer_1af21a930d69dbc8ac3a539019c2e0cb34}

AdamOptimizer의 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 

* `pLearningRate` Optimizer의 learning rate 

* `Beta1` FirstMomentum 조정 가중치 값 

* `Beta2` FirstVelocity 조정 가중치 값 

* `epsilon` 분모 값이 0이 되는 것을 방지 하는 값 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(Beta1, Beta2, epsilon)

#### `public inline  `[`AdamOptimizer`](#classAdamOptimizer_1ac06df8f4edbbf0d567e496f09dccfce6)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float Beta1,float Beta2,float epsilon,float weightDecayRate,OptimizeDirection pOptimizeDirection)` {#classAdamOptimizer_1ac06df8f4edbbf0d567e496f09dccfce6}

AdamOptimizer의 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 

* `pLearningRate` Optimizer의 learning rate 

* `Beta1` FirstMomentum 조정 가중치 값 

* `Beta2` FirstVelocity 조정 가중치 값 

* `epsilon` 분모 값이 0이 되는 것을 방지 하는 값 

* `weightDecayRate` 가중치 매개변수가 클 때 패널티를 부과하는 값 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(Beta1, Beta2, epsilon)

#### `public inline  `[`~AdamOptimizer`](#classAdamOptimizer_1add0faced6d3126163acfc4e0c36fa294)`()` {#classAdamOptimizer_1add0faced6d3126163acfc4e0c36fa294}

[AdamOptimizer](#classAdamOptimizer) 소멸자

#### Returns
없음

#### `public inline virtual void `[`Delete`](#classAdamOptimizer_1a826c98d4c1b0182ad571e3d4ebcdd9a4)`()` {#classAdamOptimizer_1a826c98d4c1b0182ad571e3d4ebcdd9a4}

Optimizer의 Delete 매소드

맴버 변수 m_aaFirstVelocity, m_aaFirstMomentum m_aaUnbiasedVelocity, m_aaUnbiasedMomentum 메모리 할당을 해제한다. 
#### Returns
없음

#### `public inline int `[`Alloc`](#classAdamOptimizer_1acef5cf04a176f41e9ce0db58bcdc4119)`(float Beta1,float Beta2,float epsilon)` {#classAdamOptimizer_1acef5cf04a176f41e9ce0db58bcdc4119}

Optimizer의 Alloc 매소드

맴버 변수 m_ppParameter, m_numOfParameter, m_aaFirstVelocity, m_aaUnbiasedVelocity, m_aaFirstMomentum m_aaUnbiasedMomentum를 초기화한다.

m_aaFirstVelocity를 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다.

m_aaUnbiasedVelocity를 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다.

m_aaFirstMomentum를 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다.

m_aaUnbiasedMomentum를 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다. 
#### Parameters
* `Beta1` FirstMomentum 조정 가중치 값 

* `Beta2` FirstVelocity 조정 가중치 값 

* `epsilon` Root Sqaure 값이 0이 되는 것을 방지 하는 값 

#### Returns
성공 시 TRUE 

**See also**: [Container](#classContainer)<[Operator<DTYPE>](#classOperator) *>* GetTrainableTensor() 

**See also**: int GetTrainableTensorDegree()

#### `public inline virtual int `[`UpdateParameter`](#classAdamOptimizer_1a8587c95667564353e1649bfe4c2c34e2)`()` {#classAdamOptimizer_1a8587c95667564353e1649bfe4c2c34e2}

파라미터 값들을 업데이트 하는 메소드

m_Beta1 유무에 따라 UpdateParameter 호출과 에러 메세지 호출 
#### Returns
성공 시 TRUE 

**See also**: int [UpdateParameter(Operator<DTYPE> *pParameter, Tensor<DTYPE> *pFirstMomentum, Tensor<DTYPE> *pFirstVelocity, Tensor<DTYPE> *pUnbiasedMomentum, Tensor<DTYPE> *pUnbiasedVelocity)](#classAdamOptimizer_1a6ee9461e547e56ee60153a53b4ecf246)

#### `public inline virtual int `[`UpdateParameter`](#classAdamOptimizer_1a92911ca3e755b8028a02ee21a57b8c2d)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` {#classAdamOptimizer_1a92911ca3e755b8028a02ee21a57b8c2d}

UpdateParameter default 함수

#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

#### Returns
성공 시 TRUE

#### `public inline int `[`UpdateParameter`](#classAdamOptimizer_1a6ee9461e547e56ee60153a53b4ecf246)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * pFirstMomentum,`[`Tensor`](#classTensor)`< DTYPE > * pFirstVelocity,`[`Tensor`](#classTensor)`< DTYPE > * pUnbiasedMomentum,`[`Tensor`](#classTensor)`< DTYPE > * pUnbiasedVelocity)` {#classAdamOptimizer_1a6ee9461e547e56ee60153a53b4ecf246}

파라미터 값들을 업데이트 하는 메소드

m_Beta1값으로 가중치가 조정된 pFirstMomentum와 gradinet로 pFirstMomentum를 업데이트 한다.

m_Beta2값으로 가중치가 조정된 pFirstVelocity와 elementwise 연산이 된 gradient로 pFirstVelocity를 업데이트 한다.

학습 초반 부, pFirstMomentum, pFirstVelocity는 0으로 biased 상태이므로 이를 unbiased 해주는 연산하여 업데이트 한다.

signed_learning_rate와 pUnbiasedMomentum곱을 root가 적용된 pUnbiasedVelocity와 m_epsilon으로 나눈 값으로 weight(trainable_data)를 업데이트 한다. 
#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pFirstMomentum` 업데이트 할 pFirstMomentum 

* `pFirstVelocity` 업데이트 할 pFirstVelocity 

* `pUnbiasedMomentum` 업데이트 할 pUnbiasedMomentum 

* `pUnbiasedVelocity` 업데이트 할 pUnbiasedVelocity 

#### Returns
성공 시 TURE

# class `Addall` {#classAddall}

```
class Addall
  : public Operator< DTYPE >
```  

값들을 서로 더하는 class

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Addall`](#classAddall_1a99310814f54bce052866e8694b4fe6ac)`(`[`Operator`](#classOperator)`< DTYPE > * pLeftInput,`[`Operator`](#classOperator)`< DTYPE > * pRightInput,std::string pName,int pLoadflag)` | Addall의 생성자
`public inline  `[`~Addall`](#classAddall_1a690307eba0d553a908b21a1d6f9110a0)`()` | Addall의 소멸자.
`public inline int `[`Alloc`](#classAddall_1ab8295fc0432e2ba0844df46254b2e5c0)`(`[`Operator`](#classOperator)`< DTYPE > * pLeftInput,`[`Operator`](#classOperator)`< DTYPE > * pRightInput)` | 파라미터로 들어온 pLeftInput을 이용해 맴버 변수들을 초기화한다.
`public inline void `[`Delete`](#classAddall_1acf09771a4170ac38c563890e391cf7b3)`()` | 메모리를 헤제하는 Delete 메소드.
`public inline virtual int `[`ForwardPropagate`](#classAddall_1a25b0cdf81f3021bf0aca0c9d65977810)`(int pTime)` | Addall의 forwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classAddall_1a1fc80ca8d9908d2d126fa1ba6a9264a3)`(int pTime)` | Addall의 BackPropagate 매소드.

## Members

#### `public inline  `[`Addall`](#classAddall_1a99310814f54bce052866e8694b4fe6ac)`(`[`Operator`](#classOperator)`< DTYPE > * pLeftInput,`[`Operator`](#classOperator)`< DTYPE > * pRightInput,std::string pName,int pLoadflag)` {#classAddall_1a99310814f54bce052866e8694b4fe6ac}

Addall의 생성자

pLeftInput, pRightInput을 Alloc시킨다. 
#### Parameters
* `pLeftInput` Alloc할 대상 [Operator](#classOperator). 

* `pRightInput` Alloc할 대상 [Operator](#classOperator). 

* `pName` Operator에 사용자가 부여한 이름. int [Alloc(Operator<DTYPE> *pLeftInput, Operator<DTYPE> *pRightInput)](#classAddall_1ab8295fc0432e2ba0844df46254b2e5c0)

#### `public inline  `[`~Addall`](#classAddall_1a690307eba0d553a908b21a1d6f9110a0)`()` {#classAddall_1a690307eba0d553a908b21a1d6f9110a0}

Addall의 소멸자.

#### `public inline int `[`Alloc`](#classAddall_1ab8295fc0432e2ba0844df46254b2e5c0)`(`[`Operator`](#classOperator)`< DTYPE > * pLeftInput,`[`Operator`](#classOperator)`< DTYPE > * pRightInput)` {#classAddall_1ab8295fc0432e2ba0844df46254b2e5c0}

파라미터로 들어온 pLeftInput을 이용해 맴버 변수들을 초기화한다.

파라미터로 들어온 pLeftInput과 m_pRightInput의 Shape정보를 맴버변수에 저장하고 다른 맴버 변수들은 pLeftInput의 Shape값으로 초기화한다.

Result값과 gradient값을 저장 할 Tensor를 새로 만든다. 
#### Parameters
* `생성` 할 Tensor의 Shape정보를 가진 [Operator](#classOperator)

* `pRightInput` 연산에 사용 할 inputTensor. 

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classAddall_1acf09771a4170ac38c563890e391cf7b3)`()` {#classAddall_1acf09771a4170ac38c563890e391cf7b3}

메모리를 헤제하는 Delete 메소드.

cudnnDescriptor들을 GPU메모리에서 해제하고 포인터를 null로 초기화한다.

#### `public inline virtual int `[`ForwardPropagate`](#classAddall_1a25b0cdf81f3021bf0aca0c9d65977810)`(int pTime)` {#classAddall_1a25b0cdf81f3021bf0aca0c9d65977810}

Addall의 forwardPropagate 매소드.

Container에 저장한 left, right의 Result값을 서로 더해 result에 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0으로 사용한다. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classAddall_1a1fc80ca8d9908d2d126fa1ba6a9264a3)`(int pTime)` {#classAddall_1a1fc80ca8d9908d2d126fa1ba6a9264a3}

Addall의 BackPropagate 매소드.

Container에 저장한 pLeftInput, pRightInput의 Gradient값에 계산한 Gradient값을 각각 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0으로 사용한다. 

#### Returns
성공 시 TRUE.

# class `AddChannelWise` {#classAddChannelWise}

```
class AddChannelWise
  : public Operator< DTYPE >
```  

서로 더하는 class

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`AddChannelWise`](#classAddChannelWise_1a7128fd2ac40a5e04fb3744e0fa5b020f)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias,std::string pName,int pLoadflag)` | AddChannelWise의 생성자
`public inline  `[`~AddChannelWise`](#classAddChannelWise_1a872112c4eb7b4533024d1625ba8db35e)`()` | AddChannelWise의 소멸자.
`public inline int `[`Alloc`](#classAddChannelWise_1a0e8731f2863b1bd143d9684a3ba52f76)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias)` | 파라미터로 들어온 pInput, pBias를 이용해 맴버 변수들을 초기화 한다
`public inline void `[`Delete`](#classAddChannelWise_1a273d5b9ebf0c74de8cdd0228fc72c9c7)`()` | 메모리를 헤제하는 Delete 메소드.
`public inline virtual int `[`ForwardPropagate`](#classAddChannelWise_1a0f81d16022df4519a555fe4b1367b902)`(int pTime)` | AddChannelWise의 forwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classAddChannelWise_1ac03a3c81061ad24b3b693b2b9fd9d96a)`(int pTime)` | AddColWise의 BackPropagate 매소드.

## Members

#### `public inline  `[`AddChannelWise`](#classAddChannelWise_1a7128fd2ac40a5e04fb3744e0fa5b020f)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias,std::string pName,int pLoadflag)` {#classAddChannelWise_1a7128fd2ac40a5e04fb3744e0fa5b020f}

AddChannelWise의 생성자

pInput, pBias을 Alloc시킨다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator). 

* `pBias` Alloc할 대상 [Operator](#classOperator). 

* `pName` Operator에 사용자가 부여한 이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pBias)](#classAddChannelWise_1a0e8731f2863b1bd143d9684a3ba52f76)

#### `public inline  `[`~AddChannelWise`](#classAddChannelWise_1a872112c4eb7b4533024d1625ba8db35e)`()` {#classAddChannelWise_1a872112c4eb7b4533024d1625ba8db35e}

AddChannelWise의 소멸자.

#### `public inline int `[`Alloc`](#classAddChannelWise_1a0e8731f2863b1bd143d9684a3ba52f76)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias)` {#classAddChannelWise_1a0e8731f2863b1bd143d9684a3ba52f76}

파라미터로 들어온 pInput, pBias를 이용해 맴버 변수들을 초기화 한다

파라미터로 들어온 pInput, pBias의 Shape정보를 맴버 변수에 저장하고 다른 맴버 변수들은 pInput의 Shape값으로 초기화 한다.

Result값과 gradient값을 저장 할 Tensor를 새로 만든다. 
#### Parameters
* `생성` 할 Tensor의 Shape정보를 가진 [Operator](#classOperator). 

* `pBias` 더할 [Operator](#classOperator). 

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classAddChannelWise_1a273d5b9ebf0c74de8cdd0228fc72c9c7)`()` {#classAddChannelWise_1a273d5b9ebf0c74de8cdd0228fc72c9c7}

메모리를 헤제하는 Delete 메소드.

cudnnDescriptor들을 GPU메모리에서 해제하고 포인터를 null로 초기화한다.

#### `public inline virtual int `[`ForwardPropagate`](#classAddChannelWise_1a0f81d16022df4519a555fe4b1367b902)`(int pTime)` {#classAddChannelWise_1a0f81d16022df4519a555fe4b1367b902}

AddChannelWise의 forwardPropagate 매소드.

Container에 저장한 Input, bias의 Channel값을 Result에 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0으로 사용한다. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classAddChannelWise_1ac03a3c81061ad24b3b693b2b9fd9d96a)`(int pTime)` {#classAddChannelWise_1ac03a3c81061ad24b3b693b2b9fd9d96a}

AddColWise의 BackPropagate 매소드.

Container에 저장한 pInput, pBias의 Gradient값애 계산을 통해 구한 gradient값을 각각 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0으로 사용한다. 

#### Returns
성공 시 TRUE.

# class `AddColWise` {#classAddColWise}

```
class AddColWise
  : public Operator< DTYPE >
```  

중 Colunm에만 값을 더하는 class

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`AddColWise`](#classAddColWise_1a4da3a66eef3f65f59b668ff69b48e218)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias,std::string pName,int pLoadflag)` | AddColWise의 생성자
`public inline  `[`~AddColWise`](#classAddColWise_1a6eb85611bc474cb5ba59d01219eabc93)`()` | AddColWise의 소멸자
`public inline int `[`Alloc`](#classAddColWise_1ac3f9ec702b314d273f50a6849cb9be6b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias)` | 파라미터로 들어온 pInput, pBias를 이용해 맴버 변수들을 초기화 한다
`public inline void `[`Delete`](#classAddColWise_1a02cc4ac173c8750ffe1212a19dee1652)`()` | 메모리를 헤제하는 Delete 메소드.
`public inline virtual int `[`ForwardPropagate`](#classAddColWise_1a4b89ea2fdc1baa3622a2fe68db8436a8)`(int pTime)` | AddColWise의 forwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classAddColWise_1ab6c9363fae11d7aaad2293bc69f8c57d)`(int pTime)` | AddColWise의 BackPropagate 매소드.

## Members

#### `public inline  `[`AddColWise`](#classAddColWise_1a4da3a66eef3f65f59b668ff69b48e218)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias,std::string pName,int pLoadflag)` {#classAddColWise_1a4da3a66eef3f65f59b668ff69b48e218}

AddColWise의 생성자

pInput, pBias을 Alloc시킨다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator). 

* `pBais` Alloc할 대상 [Operator](#classOperator). 

* `pName` Operator에 사용자가 부여한 이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pBias)](#classAddColWise_1ac3f9ec702b314d273f50a6849cb9be6b)

#### `public inline  `[`~AddColWise`](#classAddColWise_1a6eb85611bc474cb5ba59d01219eabc93)`()` {#classAddColWise_1a6eb85611bc474cb5ba59d01219eabc93}

AddColWise의 소멸자

#### `public inline int `[`Alloc`](#classAddColWise_1ac3f9ec702b314d273f50a6849cb9be6b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pBias)` {#classAddColWise_1ac3f9ec702b314d273f50a6849cb9be6b}

파라미터로 들어온 pInput, pBias를 이용해 맴버 변수들을 초기화 한다

파라미터로 들어온 pInput, pBias의 Shape정보를 맴버 변수에 저장하고 다른 맴버 변수들은 pInput의 Shape값으로 초기화 한다.

Result값과 gradient값을 저장 할 Tensor를 새로 만든다. 
#### Parameters
* `생성` 할 Tensor의 Shape정보를 가진 [Operator](#classOperator). 

* `pBias` 더할 [Operator](#classOperator). 

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classAddColWise_1a02cc4ac173c8750ffe1212a19dee1652)`()` {#classAddColWise_1a02cc4ac173c8750ffe1212a19dee1652}

메모리를 헤제하는 Delete 메소드.

cudnnDescriptor들을 GPU메모리에서 해제하고 포인터를 null로 초기화한다.

#### `public inline virtual int `[`ForwardPropagate`](#classAddColWise_1a4b89ea2fdc1baa3622a2fe68db8436a8)`(int pTime)` {#classAddColWise_1a4b89ea2fdc1baa3622a2fe68db8436a8}

AddColWise의 forwardPropagate 매소드.

Container에 저장한 Input과 bias의 Colunm값을 서로 더해 result에 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0으로 사용한다. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classAddColWise_1ab6c9363fae11d7aaad2293bc69f8c57d)`(int pTime)` {#classAddColWise_1ab6c9363fae11d7aaad2293bc69f8c57d}

AddColWise의 BackPropagate 매소드.

Container에 저장한 pInput, pBias의 Gradient값에 계산을 통해 구한 gradient값을 각각 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0으로 사용한다. 

#### Returns
성공 시 TRUE.

# class `AvaragePooling2D` {#classAvaragePooling2D}

```
class AvaragePooling2D
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`AvaragePooling2D`](#classAvaragePooling2D_1a5562be05630dade6f325154bab08cf78)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,std::string pName,int pLoadflag)` | 
`public inline  `[`AvaragePooling2D`](#classAvaragePooling2D_1a8c55c1dd95cda860ac2b1f2a78bab8a8)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,int padding,std::string pName,int pLoadflag)` | 
`public inline  `[`~AvaragePooling2D`](#classAvaragePooling2D_1a5307b5225eb6eed73c0c3a90d7baf4e9)`()` | 
`public inline int `[`Alloc`](#classAvaragePooling2D_1a94be8a4f17e668f11a9453f974318ad3)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int strideRow,int strideCol,int maskRow,int maskCol,int padding1,int padding2)` | 
`public inline void `[`Delete`](#classAvaragePooling2D_1a13fdef673da9370396f639d611c7cf19)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classAvaragePooling2D_1a9f1c1689f694564e669877834a661ec6)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classAvaragePooling2D_1a7ac66b567e2ed27c16e9a501d7cbcf5a)`(int pTime)` | 

## Members

#### `public inline  `[`AvaragePooling2D`](#classAvaragePooling2D_1a5562be05630dade6f325154bab08cf78)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,std::string pName,int pLoadflag)` {#classAvaragePooling2D_1a5562be05630dade6f325154bab08cf78}

#### `public inline  `[`AvaragePooling2D`](#classAvaragePooling2D_1a8c55c1dd95cda860ac2b1f2a78bab8a8)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,int padding,std::string pName,int pLoadflag)` {#classAvaragePooling2D_1a8c55c1dd95cda860ac2b1f2a78bab8a8}

#### `public inline  `[`~AvaragePooling2D`](#classAvaragePooling2D_1a5307b5225eb6eed73c0c3a90d7baf4e9)`()` {#classAvaragePooling2D_1a5307b5225eb6eed73c0c3a90d7baf4e9}

#### `public inline int `[`Alloc`](#classAvaragePooling2D_1a94be8a4f17e668f11a9453f974318ad3)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int strideRow,int strideCol,int maskRow,int maskCol,int padding1,int padding2)` {#classAvaragePooling2D_1a94be8a4f17e668f11a9453f974318ad3}

#### `public inline void `[`Delete`](#classAvaragePooling2D_1a13fdef673da9370396f639d611c7cf19)`()` {#classAvaragePooling2D_1a13fdef673da9370396f639d611c7cf19}

#### `public inline virtual int `[`ForwardPropagate`](#classAvaragePooling2D_1a9f1c1689f694564e669877834a661ec6)`(int pTime)` {#classAvaragePooling2D_1a9f1c1689f694564e669877834a661ec6}

#### `public inline virtual int `[`BackPropagate`](#classAvaragePooling2D_1a7ac66b567e2ed27c16e9a501d7cbcf5a)`(int pTime)` {#classAvaragePooling2D_1a7ac66b567e2ed27c16e9a501d7cbcf5a}

# class `BatchNormalize` {#classBatchNormalize}

```
class BatchNormalize
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`BatchNormalize`](#classBatchNormalize_1a4605ef6bc6c23d61101f1eebc013d5bf)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,std::string pName)` | 
`public inline  `[`BatchNormalize`](#classBatchNormalize_1aca6d3c52ef215361278126874af0ea15)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,float pEpsilon,std::string pName)` | 
`public inline virtual int `[`ForwardPropagate`](#classBatchNormalize_1a76815c0f13105d944722e17476513838)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classBatchNormalize_1a3b0cce7d21f6b99f5d70aacb35b08200)`(int pTime)` | 
`public inline virtual void `[`SetModeTrain`](#classBatchNormalize_1af44186c9a81c0473bc1101bcc308233e)`()` | 
`public inline virtual void `[`SetModeAccumulate`](#classBatchNormalize_1acb076b958c2d46e45538b0c04e05bdb1)`()` | 
`public inline virtual void `[`SetModeInference`](#classBatchNormalize_1a1d241bfdb2cb113b604aa88765e87c06)`()` | 
`public inline  `[`BatchNormalize`](#classBatchNormalize_1aabded28cf8fb2059330a4766f1d273e1)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,std::string pName,int pLoadflag)` | 
`public inline  `[`BatchNormalize`](#classBatchNormalize_1a371b4a12a3411b4aa0f0026e256bb063)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,float pMomentum,std::string pName,int pLoadflag)` | 
`public inline  `[`~BatchNormalize`](#classBatchNormalize_1aa2ca8ff9c4ea80162f304ab3bf1e57e2)`()` | 
`public inline int `[`Alloc`](#classBatchNormalize_1a69a2918f7563e8a754c6f92e8d983292)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,float pMomentum,double pEpsilon)` | 
`public inline virtual int `[`SetModeTrain`](#classBatchNormalize_1ac9945da88b6fdbe32f3e1aa4fda7e631)`()` | 
`public inline virtual int `[`SetModeAccumulate`](#classBatchNormalize_1a01bfe41e2200672f179704ba71c044a0)`()` | 
`public inline virtual int `[`SetModeInference`](#classBatchNormalize_1a0ecddabe78a70f92f150f83428eecabc)`()` | 

## Members

#### `public inline  `[`BatchNormalize`](#classBatchNormalize_1a4605ef6bc6c23d61101f1eebc013d5bf)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,std::string pName)` {#classBatchNormalize_1a4605ef6bc6c23d61101f1eebc013d5bf}

#### `public inline  `[`BatchNormalize`](#classBatchNormalize_1aca6d3c52ef215361278126874af0ea15)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,float pEpsilon,std::string pName)` {#classBatchNormalize_1aca6d3c52ef215361278126874af0ea15}

#### `public inline virtual int `[`ForwardPropagate`](#classBatchNormalize_1a76815c0f13105d944722e17476513838)`(int pTime)` {#classBatchNormalize_1a76815c0f13105d944722e17476513838}

#### `public inline virtual int `[`BackPropagate`](#classBatchNormalize_1a3b0cce7d21f6b99f5d70aacb35b08200)`(int pTime)` {#classBatchNormalize_1a3b0cce7d21f6b99f5d70aacb35b08200}

#### `public inline virtual void `[`SetModeTrain`](#classBatchNormalize_1af44186c9a81c0473bc1101bcc308233e)`()` {#classBatchNormalize_1af44186c9a81c0473bc1101bcc308233e}

#### `public inline virtual void `[`SetModeAccumulate`](#classBatchNormalize_1acb076b958c2d46e45538b0c04e05bdb1)`()` {#classBatchNormalize_1acb076b958c2d46e45538b0c04e05bdb1}

#### `public inline virtual void `[`SetModeInference`](#classBatchNormalize_1a1d241bfdb2cb113b604aa88765e87c06)`()` {#classBatchNormalize_1a1d241bfdb2cb113b604aa88765e87c06}

#### `public inline  `[`BatchNormalize`](#classBatchNormalize_1aabded28cf8fb2059330a4766f1d273e1)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,std::string pName,int pLoadflag)` {#classBatchNormalize_1aabded28cf8fb2059330a4766f1d273e1}

#### `public inline  `[`BatchNormalize`](#classBatchNormalize_1a371b4a12a3411b4aa0f0026e256bb063)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,float pMomentum,std::string pName,int pLoadflag)` {#classBatchNormalize_1a371b4a12a3411b4aa0f0026e256bb063}

#### `public inline  `[`~BatchNormalize`](#classBatchNormalize_1aa2ca8ff9c4ea80162f304ab3bf1e57e2)`()` {#classBatchNormalize_1aa2ca8ff9c4ea80162f304ab3bf1e57e2}

#### `public inline int `[`Alloc`](#classBatchNormalize_1a69a2918f7563e8a754c6f92e8d983292)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pScale,`[`Operator`](#classOperator)`< DTYPE > * pBias,int pIsChannelwise,float pMomentum,double pEpsilon)` {#classBatchNormalize_1a69a2918f7563e8a754c6f92e8d983292}

#### `public inline virtual int `[`SetModeTrain`](#classBatchNormalize_1ac9945da88b6fdbe32f3e1aa4fda7e631)`()` {#classBatchNormalize_1ac9945da88b6fdbe32f3e1aa4fda7e631}

#### `public inline virtual int `[`SetModeAccumulate`](#classBatchNormalize_1a01bfe41e2200672f179704ba71c044a0)`()` {#classBatchNormalize_1a01bfe41e2200672f179704ba71c044a0}

#### `public inline virtual int `[`SetModeInference`](#classBatchNormalize_1a0ecddabe78a70f92f150f83428eecabc)`()` {#classBatchNormalize_1a0ecddabe78a70f92f150f83428eecabc}

# class `BatchNormalizeLayer` {#classBatchNormalizeLayer}

```
class BatchNormalizeLayer
  : public Module< DTYPE >
```  

구성해 Batch Normalization Layer의 기능을 수행하는 모듈을 생성하는 클래스

Operator들을 뉴럴 네트워크의 서브 그래프로 구성해 Batch Normalization Layer의 기능을 수행한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`BatchNormalizeLayer`](#classBatchNormalizeLayer_1ab72f27059f143d70809c44186c3aec2a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pIsChannelwise,std::string pName)` | [BatchNormalizeLayer](#classBatchNormalizeLayer) 클래스 생성자
`public inline virtual  `[`~BatchNormalizeLayer`](#classBatchNormalizeLayer_1a53b3cc13dbea61c9845277bfbc88c935)`()` | [BatchNormalizeLayer](#classBatchNormalizeLayer) 클래스 소멸자
`public inline int `[`Alloc`](#classBatchNormalizeLayer_1ad61e05b3ff8a276a1021671d1e2af814)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pIsChannelwise,std::string pName)` | Batch Normalize Layer 그래프를 동적으로 할당 및 구성하는 메소드

## Members

#### `public inline  `[`BatchNormalizeLayer`](#classBatchNormalizeLayer_1ab72f27059f143d70809c44186c3aec2a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pIsChannelwise,std::string pName)` {#classBatchNormalizeLayer_1ab72f27059f143d70809c44186c3aec2a}

[BatchNormalizeLayer](#classBatchNormalizeLayer) 클래스 생성자

[BatchNormalizeLayer](#classBatchNormalizeLayer) 클래스의 Alloc 메소드를 호출한다. 
**See also**: [BatchNormalizeLayer<DTYPE>::Alloc(Operator<DTYPE> *pInput, int pIsChannelwise, std::string pName)](#classBatchNormalizeLayer_1ad61e05b3ff8a276a1021671d1e2af814)

#### `public inline virtual  `[`~BatchNormalizeLayer`](#classBatchNormalizeLayer_1a53b3cc13dbea61c9845277bfbc88c935)`()` {#classBatchNormalizeLayer_1a53b3cc13dbea61c9845277bfbc88c935}

[BatchNormalizeLayer](#classBatchNormalizeLayer) 클래스 소멸자

단, 동적 할당 받은 Operator들은 NeuralNetwork에서 할당 해제한다.

#### `public inline int `[`Alloc`](#classBatchNormalizeLayer_1ad61e05b3ff8a276a1021671d1e2af814)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pIsChannelwise,std::string pName)` {#classBatchNormalizeLayer_1ad61e05b3ff8a276a1021671d1e2af814}

Batch Normalize Layer 그래프를 동적으로 할당 및 구성하는 메소드

Input Operator의 Element에 대해 배치 정규화(Batch Normailzation)을 수행한다. 
#### Parameters
* `pInput` 해당 Layer의 Input에 해당하는 [Operator](#classOperator)

* `pIsChannelWise` Column-Wise Normalization 유무, 0일 시 Column-Wise롤 연산, 0이 아닐 시 Channel-Wise로 연산 

* `pName` Module의 이름 

#### Returns
TRUE 

**See also**: BatchNormalize<DTYPE>::BatchNormalize([Operator<DTYPE>](#classOperator) *pInput, [Operator<DTYPE>](#classOperator) *pScale, [Operator<DTYPE>](#classOperator) *pBias, int pIsChannelwise = TRUE, std::string pName = NULL) [Module<DTYPE>::AnalyzeGraph(Operator<DTYPE> *pResultOperator)](#classModule_1a7a8ca0c6ddde4bffde9d806ff64ba614)

# class `BEGAN` {#classBEGAN}

```
class BEGAN
  : public GAN< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`BEGAN`](#classBEGAN_1a691d96dc6bc0f76f7a45f92b32ec1f0f)`()` | 
`public virtual  `[`~BEGAN`](#classBEGAN_1a41c615f2d72167b0d308760de9409c6f)`()` | 
`public int `[`SetBEGANParameter`](#classBEGAN_1aa4fff3a445d061d3d5011267b1586db6)`(float pK,float pLamda,float pGamma)` | 
`public virtual int `[`TrainGeneratorOnCPU`](#classBEGAN_1a3fe4d0faae4798618228b458a21a96d5)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnCPU`](#classBEGAN_1a17c4c345f733cf7eb626bfd893485cac)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnCPU`](#classBEGAN_1a8a924de74987dd2d612912fa5dcdb9fc)`()` | 
`public virtual int `[`TrainGeneratorOnGPU`](#classBEGAN_1acbbbd6c8d4ba0ebefa5c5ad71347a851)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnGPU`](#classBEGAN_1abbb29ae231c784b87d3272cbe9a38cb1)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnGPU`](#classBEGAN_1a5933ab766907aaf7facf189af99ed7f2)`()` | 
`public float `[`SaveLossX`](#classBEGAN_1a12c9a7c35f4b54fe3c5b03191f5ba806)`()` | 
`public float `[`SaveLossG`](#classBEGAN_1a8b25215b2c15691974500d0bf4a1db63)`()` | 
`public int `[`MultiplyKOnOutput`](#classBEGAN_1a914e5d0a2d6f26e891d0ef03998902f8)`()` | 
`public int `[`MultiplyKOnGradient`](#classBEGAN_1a715adb9b5a846c4d3f4f7fbac1f8e59e)`()` | 
`public float `[`UpdateK`](#classBEGAN_1a152d0737c8d9fb04f94526cfaaebf95b)`()` | 
`public float `[`GetK`](#classBEGAN_1af8769254fa4066ddf34ef9bd89548a8e)`()` | 
`public float `[`ComputeConvergenceMeasure`](#classBEGAN_1ade9b978d04828413c248e6418d23b67c)`()` | 
`public float `[`GetConvergenceMeasure`](#classBEGAN_1a06ba784c4b1956fd1de5d11ba766fdde)`()` | 

## Members

#### `public  `[`BEGAN`](#classBEGAN_1a691d96dc6bc0f76f7a45f92b32ec1f0f)`()` {#classBEGAN_1a691d96dc6bc0f76f7a45f92b32ec1f0f}

#### `public virtual  `[`~BEGAN`](#classBEGAN_1a41c615f2d72167b0d308760de9409c6f)`()` {#classBEGAN_1a41c615f2d72167b0d308760de9409c6f}

#### `public int `[`SetBEGANParameter`](#classBEGAN_1aa4fff3a445d061d3d5011267b1586db6)`(float pK,float pLamda,float pGamma)` {#classBEGAN_1aa4fff3a445d061d3d5011267b1586db6}

#### `public virtual int `[`TrainGeneratorOnCPU`](#classBEGAN_1a3fe4d0faae4798618228b458a21a96d5)`()` {#classBEGAN_1a3fe4d0faae4798618228b458a21a96d5}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnCPU`](#classBEGAN_1a17c4c345f733cf7eb626bfd893485cac)`()` {#classBEGAN_1a17c4c345f733cf7eb626bfd893485cac}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnCPU`](#classBEGAN_1a8a924de74987dd2d612912fa5dcdb9fc)`()` {#classBEGAN_1a8a924de74987dd2d612912fa5dcdb9fc}

#### `public virtual int `[`TrainGeneratorOnGPU`](#classBEGAN_1acbbbd6c8d4ba0ebefa5c5ad71347a851)`()` {#classBEGAN_1acbbbd6c8d4ba0ebefa5c5ad71347a851}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnGPU`](#classBEGAN_1abbb29ae231c784b87d3272cbe9a38cb1)`()` {#classBEGAN_1abbb29ae231c784b87d3272cbe9a38cb1}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnGPU`](#classBEGAN_1a5933ab766907aaf7facf189af99ed7f2)`()` {#classBEGAN_1a5933ab766907aaf7facf189af99ed7f2}

#### `public float `[`SaveLossX`](#classBEGAN_1a12c9a7c35f4b54fe3c5b03191f5ba806)`()` {#classBEGAN_1a12c9a7c35f4b54fe3c5b03191f5ba806}

#### `public float `[`SaveLossG`](#classBEGAN_1a8b25215b2c15691974500d0bf4a1db63)`()` {#classBEGAN_1a8b25215b2c15691974500d0bf4a1db63}

#### `public int `[`MultiplyKOnOutput`](#classBEGAN_1a914e5d0a2d6f26e891d0ef03998902f8)`()` {#classBEGAN_1a914e5d0a2d6f26e891d0ef03998902f8}

#### `public int `[`MultiplyKOnGradient`](#classBEGAN_1a715adb9b5a846c4d3f4f7fbac1f8e59e)`()` {#classBEGAN_1a715adb9b5a846c4d3f4f7fbac1f8e59e}

#### `public float `[`UpdateK`](#classBEGAN_1a152d0737c8d9fb04f94526cfaaebf95b)`()` {#classBEGAN_1a152d0737c8d9fb04f94526cfaaebf95b}

#### `public float `[`GetK`](#classBEGAN_1af8769254fa4066ddf34ef9bd89548a8e)`()` {#classBEGAN_1af8769254fa4066ddf34ef9bd89548a8e}

#### `public float `[`ComputeConvergenceMeasure`](#classBEGAN_1ade9b978d04828413c248e6418d23b67c)`()` {#classBEGAN_1ade9b978d04828413c248e6418d23b67c}

#### `public float `[`GetConvergenceMeasure`](#classBEGAN_1a06ba784c4b1956fd1de5d11ba766fdde)`()` {#classBEGAN_1a06ba784c4b1956fd1de5d11ba766fdde}

# class `BEGANDiscriminatorLoss` {#classBEGANDiscriminatorLoss}

```
class BEGANDiscriminatorLoss
  : public LossFunction< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`BEGANDiscriminatorLoss`](#classBEGANDiscriminatorLoss_1a010715fe26fff2e5e007ed15ea9c5655)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | 
`public inline virtual  `[`~BEGANDiscriminatorLoss`](#classBEGANDiscriminatorLoss_1a26e2bed92059fa4e06bac852d58cd223)`()` | 
`public inline virtual int `[`Alloc`](#classBEGANDiscriminatorLoss_1a6b019fee5c76d833b057538852d003a1)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` | 
`public inline virtual void `[`Delete`](#classBEGANDiscriminatorLoss_1ab3a4d840369f2f372ac7985f3c05c024)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classBEGANDiscriminatorLoss_1ae4ea63a8093be7984d96c1d7c31663bf)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classBEGANDiscriminatorLoss_1af0637d48c60d55b356aaed92c8b24401)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`BEGANDiscriminatorLoss`](#classBEGANDiscriminatorLoss_1a010715fe26fff2e5e007ed15ea9c5655)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classBEGANDiscriminatorLoss_1a010715fe26fff2e5e007ed15ea9c5655}

#### `public inline virtual  `[`~BEGANDiscriminatorLoss`](#classBEGANDiscriminatorLoss_1a26e2bed92059fa4e06bac852d58cd223)`()` {#classBEGANDiscriminatorLoss_1a26e2bed92059fa4e06bac852d58cd223}

#### `public inline virtual int `[`Alloc`](#classBEGANDiscriminatorLoss_1a6b019fee5c76d833b057538852d003a1)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` {#classBEGANDiscriminatorLoss_1a6b019fee5c76d833b057538852d003a1}

#### `public inline virtual void `[`Delete`](#classBEGANDiscriminatorLoss_1ab3a4d840369f2f372ac7985f3c05c024)`()` {#classBEGANDiscriminatorLoss_1ab3a4d840369f2f372ac7985f3c05c024}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classBEGANDiscriminatorLoss_1ae4ea63a8093be7984d96c1d7c31663bf)`(int pTime)` {#classBEGANDiscriminatorLoss_1ae4ea63a8093be7984d96c1d7c31663bf}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classBEGANDiscriminatorLoss_1af0637d48c60d55b356aaed92c8b24401)`(int pTime)` {#classBEGANDiscriminatorLoss_1af0637d48c60d55b356aaed92c8b24401}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

# class `BEGANGeneratorLoss` {#classBEGANGeneratorLoss}

```
class BEGANGeneratorLoss
  : public LossFunction< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`BEGANGeneratorLoss`](#classBEGANGeneratorLoss_1a08d4ff8cf1d6c1928f6d505593b09044)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | 
`public inline virtual  `[`~BEGANGeneratorLoss`](#classBEGANGeneratorLoss_1aa0f955a8e83ec6ad45bd05723b11f949)`()` | 
`public inline virtual int `[`Alloc`](#classBEGANGeneratorLoss_1a30b7cddd07e653b0e32db6d995344018)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` | 
`public inline virtual void `[`Delete`](#classBEGANGeneratorLoss_1a0166fb27d354569a87b16c9625a31611)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classBEGANGeneratorLoss_1a49c3bcc602a251960dbf5f150a8cd4c3)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classBEGANGeneratorLoss_1a1e6802c0db50cc63f1e1537f818d89ad)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`BEGANGeneratorLoss`](#classBEGANGeneratorLoss_1a08d4ff8cf1d6c1928f6d505593b09044)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classBEGANGeneratorLoss_1a08d4ff8cf1d6c1928f6d505593b09044}

#### `public inline virtual  `[`~BEGANGeneratorLoss`](#classBEGANGeneratorLoss_1aa0f955a8e83ec6ad45bd05723b11f949)`()` {#classBEGANGeneratorLoss_1aa0f955a8e83ec6ad45bd05723b11f949}

#### `public inline virtual int `[`Alloc`](#classBEGANGeneratorLoss_1a30b7cddd07e653b0e32db6d995344018)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` {#classBEGANGeneratorLoss_1a30b7cddd07e653b0e32db6d995344018}

#### `public inline virtual void `[`Delete`](#classBEGANGeneratorLoss_1a0166fb27d354569a87b16c9625a31611)`()` {#classBEGANGeneratorLoss_1a0166fb27d354569a87b16c9625a31611}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classBEGANGeneratorLoss_1a49c3bcc602a251960dbf5f150a8cd4c3)`(int pTime)` {#classBEGANGeneratorLoss_1a49c3bcc602a251960dbf5f150a8cd4c3}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classBEGANGeneratorLoss_1a1e6802c0db50cc63f1e1537f818d89ad)`(int pTime)` {#classBEGANGeneratorLoss_1a1e6802c0db50cc63f1e1537f818d89ad}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

# class `ConcatenateChannelWise` {#classConcatenateChannelWise}

```
class ConcatenateChannelWise
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`ConcatenateChannelWise`](#classConcatenateChannelWise_1a6b96ab6f8de1e8827f37299eef63d293)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,std::string pName,int pLoadflag)` | 
`public inline  `[`~ConcatenateChannelWise`](#classConcatenateChannelWise_1a06b00347d6de66d5eae8a4ed178d4909)`()` | 
`public inline int `[`Alloc`](#classConcatenateChannelWise_1ae5ac08e3680e10d46d95647eaa1de3fe)`(int noOperator,...)` | 
`public inline virtual int `[`ForwardPropagate`](#classConcatenateChannelWise_1ae37a10c31cf4635de1fae1245b872193)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classConcatenateChannelWise_1a2d4fe7b4d6901c4a2330d5c533c974b2)`(int pTime)` | 

## Members

#### `public inline  `[`ConcatenateChannelWise`](#classConcatenateChannelWise_1a6b96ab6f8de1e8827f37299eef63d293)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,std::string pName,int pLoadflag)` {#classConcatenateChannelWise_1a6b96ab6f8de1e8827f37299eef63d293}

#### `public inline  `[`~ConcatenateChannelWise`](#classConcatenateChannelWise_1a06b00347d6de66d5eae8a4ed178d4909)`()` {#classConcatenateChannelWise_1a06b00347d6de66d5eae8a4ed178d4909}

#### `public inline int `[`Alloc`](#classConcatenateChannelWise_1ae5ac08e3680e10d46d95647eaa1de3fe)`(int noOperator,...)` {#classConcatenateChannelWise_1ae5ac08e3680e10d46d95647eaa1de3fe}

#### `public inline virtual int `[`ForwardPropagate`](#classConcatenateChannelWise_1ae37a10c31cf4635de1fae1245b872193)`(int pTime)` {#classConcatenateChannelWise_1ae37a10c31cf4635de1fae1245b872193}

#### `public inline virtual int `[`BackPropagate`](#classConcatenateChannelWise_1a2d4fe7b4d6901c4a2330d5c533c974b2)`(int pTime)` {#classConcatenateChannelWise_1a2d4fe7b4d6901c4a2330d5c533c974b2}

# class `Container` {#classContainer}

저장하기 위한 Queue에 해당하는 클래스

[Tensor](#classTensor), [Operator](#classOperator), [Tensorholder](#classTensorholder) 세 가지 클래스에 대한 Queue를 동적으로 할당한다.

기본 queue 구조에 인덱스를 이용한 접근 및 역순으로 접근 등 추가적인 메소드가 구현되어 있다.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Container`](#classContainer_1ab2bf85021abd93687431712eec397bd6)`()` | [Container](#classContainer) 생성자
`public inline virtual  `[`~Container`](#classContainer_1aa842cc3579205a9431569dea02b0976e)`()` | [Container](#classContainer) 클래스 소멸자
`public inline int `[`Push`](#classContainer_1ac875fe061a6d4c1137def5251eaef95a)`(DTYPE pElement)` | Queue의 push 메소드
`public inline DTYPE `[`Pop`](#classContainer_1ad7b9f7d5eb283748a0d31389b487e396)`()` | Queue의 pop 메소드
`public inline DTYPE `[`Pop`](#classContainer_1a15c8f4962022d9ad82ffb6c721b672f9)`(DTYPE pElement)` | Queue에서 Element를 찾아 반환하는 pop 메소드
`public inline int `[`Reverse`](#classContainer_1ab86a61645d5fff30cff8062e7988b770)`()` | Queue를 역순으로 재할당해주는 메소드
`public inline int `[`SetElement`](#classContainer_1a4f113e1ecebcf3a21273aefd26d7bbb5)`(DTYPE pElement,unsigned int index)` | 
`public inline int `[`GetSize`](#classContainer_1ac0cc8e4e6056e832c4874635ac871c40)`()` | 
`public inline DTYPE `[`GetLast`](#classContainer_1ac4fb1b6458674b9876afb4b1fa18c4a9)`()` | 
`public inline DTYPE * `[`GetRawData`](#classContainer_1adbb3e154598ae672e37283a1fb292ba2)`() const` | 
`public inline DTYPE `[`GetElement`](#classContainer_1a127e7b9fa3de03c7f7f866190fd1c585)`(unsigned int index)` | 
`public inline DTYPE & `[`operator[]`](#classContainer_1a884d3c64b1d6556018585569d8f00994)`(unsigned int index)` | []연산자 오버로딩

## Members

#### `public inline  `[`Container`](#classContainer_1ab2bf85021abd93687431712eec397bd6)`()` {#classContainer_1ab2bf85021abd93687431712eec397bd6}

[Container](#classContainer) 생성자

각 멤버 변수를 초기화하여 [Container](#classContainer) 클래스를 생성한다. 
#### Returns
없음

#### `public inline virtual  `[`~Container`](#classContainer_1aa842cc3579205a9431569dea02b0976e)`()` {#classContainer_1aa842cc3579205a9431569dea02b0976e}

[Container](#classContainer) 클래스 소멸자

해당 [Container](#classContainer) 클래스를 위해 동적으로 할당된 메모리 공간을 반환하고 클래스를 소멸한다. 
#### Returns
없음

#### `public inline int `[`Push`](#classContainer_1ac875fe061a6d4c1137def5251eaef95a)`(DTYPE pElement)` {#classContainer_1ac875fe061a6d4c1137def5251eaef95a}

Queue의 push 메소드

기존의 queue를 할당 해제하고 매개변수로 받은 Element를 마지막에 추가하여 새로운 Queue를 동적으로 할당한다. 
#### Parameters
* `pElement` Queue에 추가하고자 하는 변수 

#### Returns
성공 시 TRUE, 실패 시 FALSE

#### `public inline DTYPE `[`Pop`](#classContainer_1ad7b9f7d5eb283748a0d31389b487e396)`()` {#classContainer_1ad7b9f7d5eb283748a0d31389b487e396}

Queue의 pop 메소드

기존의 queue를 할당 해제하고 Queue의 첫번째 Element를 반환한 후 새로운 Queue를 동적으로 할당한다. 
#### Returns
Queue의 첫번째 Element

#### `public inline DTYPE `[`Pop`](#classContainer_1a15c8f4962022d9ad82ffb6c721b672f9)`(DTYPE pElement)` {#classContainer_1a15c8f4962022d9ad82ffb6c721b672f9}

Queue에서 Element를 찾아 반환하는 pop 메소드

매개변수로 받은 Element가 Queue에 존재할 경우, 해당 Element를 반환하고 Queue를 새로 동적으로 할당한다. 
#### Parameters
* `pElement` Queue에서 찾고자 하는 Element 

#### Returns
실패 시 NULL, 성공 시 매개변수로 전달받은 Element와 동일한 Queue의 Element

#### `public inline int `[`Reverse`](#classContainer_1ab86a61645d5fff30cff8062e7988b770)`()` {#classContainer_1ab86a61645d5fff30cff8062e7988b770}

Queue를 역순으로 재할당해주는 메소드

Queue의 Element를 반대 순서로 저장하는 새로운 Queue를 할당하고, 기존의 Queue를 할당 해제한다. 
#### Returns
TRUE

#### `public inline int `[`SetElement`](#classContainer_1a4f113e1ecebcf3a21273aefd26d7bbb5)`(DTYPE pElement,unsigned int index)` {#classContainer_1a4f113e1ecebcf3a21273aefd26d7bbb5}

#### `public inline int `[`GetSize`](#classContainer_1ac0cc8e4e6056e832c4874635ac871c40)`()` {#classContainer_1ac0cc8e4e6056e832c4874635ac871c40}

#### `public inline DTYPE `[`GetLast`](#classContainer_1ac4fb1b6458674b9876afb4b1fa18c4a9)`()` {#classContainer_1ac4fb1b6458674b9876afb4b1fa18c4a9}

#### `public inline DTYPE * `[`GetRawData`](#classContainer_1adbb3e154598ae672e37283a1fb292ba2)`() const` {#classContainer_1adbb3e154598ae672e37283a1fb292ba2}

#### `public inline DTYPE `[`GetElement`](#classContainer_1a127e7b9fa3de03c7f7f866190fd1c585)`(unsigned int index)` {#classContainer_1a127e7b9fa3de03c7f7f866190fd1c585}

#### `public inline DTYPE & `[`operator[]`](#classContainer_1a884d3c64b1d6556018585569d8f00994)`(unsigned int index)` {#classContainer_1a884d3c64b1d6556018585569d8f00994}

[]연산자 오버로딩

Queue에서 파라미터로 받은 인덱스에 해당하는 ELement를 반환한다. 
#### Parameters
* `index` 찾고자 하는 Queue의 Element의 인덱스 

#### Returns
m_aElement[index]

# class `Convolution2D` {#classConvolution2D}

```
class Convolution2D
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Convolution2D`](#classConvolution2D_1a5beb3b40bafb285ae8e3263090750629)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,std::string pName,int pLoadflag)` | Convolution2D의 생성자.
`public inline  `[`Convolution2D`](#classConvolution2D_1abe5ba6af6d5f937406afdcaa38f8f523)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding,std::string pName,int pLoadflag)` | Convolution2D의 생성자.
`public inline  `[`Convolution2D`](#classConvolution2D_1ade843fe630f0761b08c2f9c8cd6700c3)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2,std::string pName,int pLoadflag)` | Convolution2D의 생성자.
`public inline virtual  `[`~Convolution2D`](#classConvolution2D_1a594f73f7e54af4986fb38f65f0b47d86)`()` | Convolution2D의 소멸자.
`public inline int `[`Alloc`](#classConvolution2D_1a50def34cf16da197fbbff0f5d51df8af)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2)` | 파라미터로 받은 pInput, pWeight, stride1, stride2, padding1, padding2으로 맴버 변수들을 초기화 한다.
`public inline void `[`Delete`](#classConvolution2D_1a138e61e8ddf41736599591d1fcbef660)`()` | GPU에 할당했던 메모리를 해제하고 각 포인터들을 NULL로 초기화한다.
`public inline virtual int `[`ForwardPropagate`](#classConvolution2D_1af6fb380cb816f05f6be1d373a5a38646)`(int pTime)` | Convolution2D의 ForwardPropagate 메소드.
`public inline virtual int `[`BackPropagate`](#classConvolution2D_1ad191ef030ffcbc1c49fc19701bc76ac4)`(int pTime)` | CONVOLUTION_2D의 BackPropagate 메소드.
`public inline int * `[`GetStrideList`](#classConvolution2D_1a16d798fd391ebf68199013aa1c95d02c)`()` | 
`public inline int * `[`GetPaddingList`](#classConvolution2D_1a8f2665a6a9a2ad89ecd60d0119188968)`()` | 

## Members

#### `public inline  `[`Convolution2D`](#classConvolution2D_1a5beb3b40bafb285ae8e3263090750629)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,std::string pName,int pLoadflag)` {#classConvolution2D_1a5beb3b40bafb285ae8e3263090750629}

Convolution2D의 생성자.

파라미터로 받은 pInput, pWeight, stride1, stride2로 Alloc한다. 
#### Parameters
* `pInput` Convolution할 [Operator](#classOperator)

* `pWeight` Convolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight, int stride1, int stride2, int padding1, int padding2)](#classConvolution2D_1a50def34cf16da197fbbff0f5d51df8af)

#### `public inline  `[`Convolution2D`](#classConvolution2D_1abe5ba6af6d5f937406afdcaa38f8f523)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding,std::string pName,int pLoadflag)` {#classConvolution2D_1abe5ba6af6d5f937406afdcaa38f8f523}

Convolution2D의 생성자.

파라미터로 받은 pInput, pWeight, stride1, stride2, padding로 Alloc한다. 
#### Parameters
* `pInput` Convolution할 [Operator](#classOperator)

* `pWeight` Convolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `padding` padding 할 값. height, width 모두 이 값으로 한다. 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight, int stride1, int stride2, int padding1, int padding2)](#classConvolution2D_1a50def34cf16da197fbbff0f5d51df8af)

#### `public inline  `[`Convolution2D`](#classConvolution2D_1ade843fe630f0761b08c2f9c8cd6700c3)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2,std::string pName,int pLoadflag)` {#classConvolution2D_1ade843fe630f0761b08c2f9c8cd6700c3}

Convolution2D의 생성자.

파라미터로 받은 pInput, pWeight, stride1, stride2, padding1, padding2로 Alloc한다. 
#### Parameters
* `pInput` Convolution할 [Operator](#classOperator)

* `pWeight` Convolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `padding1` height padding값 

* `padding2` width padding값 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight, int stride1, int stride2, int padding1, int padding2)](#classConvolution2D_1a50def34cf16da197fbbff0f5d51df8af)

#### `public inline virtual  `[`~Convolution2D`](#classConvolution2D_1a594f73f7e54af4986fb38f65f0b47d86)`()` {#classConvolution2D_1a594f73f7e54af4986fb38f65f0b47d86}

Convolution2D의 소멸자.

Delete매소드를 사용해 GPU에 할당했던 값들을 해제한다. void [Delete()](#classConvolution2D_1a138e61e8ddf41736599591d1fcbef660)

#### `public inline int `[`Alloc`](#classConvolution2D_1a50def34cf16da197fbbff0f5d51df8af)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2)` {#classConvolution2D_1a50def34cf16da197fbbff0f5d51df8af}

파라미터로 받은 pInput, pWeight, stride1, stride2, padding1, padding2으로 맴버 변수들을 초기화 한다.

pInput과 pWeight의 Shape과 stride, padding값으로 output으로 Result와 Delta로 사용 할 Tensor의 Shape을 정의한다. 
#### Parameters
* `pInput` Convolution할 [Operator](#classOperator)

* `pWeight` Convolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `padding1` height padding값 

* `padding2` width padding값

#### `public inline void `[`Delete`](#classConvolution2D_1a138e61e8ddf41736599591d1fcbef660)`()` {#classConvolution2D_1a138e61e8ddf41736599591d1fcbef660}

GPU에 할당했던 메모리를 해제하고 각 포인터들을 NULL로 초기화한다.

inputTensorDesc, outputTensorDesc,deltaDesc, inputDeltaDesc, convDesc, filterDesc,filterDeltaDesc들을 삭제하고 NULL로 초기화한다.

cudnn연산을 위해 할당 했던 메모리들을 해제시킨다.

#### `public inline virtual int `[`ForwardPropagate`](#classConvolution2D_1af6fb380cb816f05f6be1d373a5a38646)`(int pTime)` {#classConvolution2D_1af6fb380cb816f05f6be1d373a5a38646}

Convolution2D의 ForwardPropagate 메소드.

weight(filter size = rowsizeOfWeight * colsizeOfWeight)와 input의 곱한 값을 result에 더해 넣는다.

이때 m_stride값들 만큼 이동하며 result를 계산한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classConvolution2D_1ad191ef030ffcbc1c49fc19701bc76ac4)`(int pTime)` {#classConvolution2D_1ad191ef030ffcbc1c49fc19701bc76ac4}

CONVOLUTION_2D의 BackPropagate 메소드.

Convolution의 미분 값(weight * this_delta, input * this_delta)을 계산하여 input_delta와 weight_gradient에 각각 더해 넣는다.

이때 m_stride값들 만큼 이동하며 미분 값을 넣을 위치를 계산한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline int * `[`GetStrideList`](#classConvolution2D_1a16d798fd391ebf68199013aa1c95d02c)`()` {#classConvolution2D_1a16d798fd391ebf68199013aa1c95d02c}

#### `public inline int * `[`GetPaddingList`](#classConvolution2D_1a8f2665a6a9a2ad89ecd60d0119188968)`()` {#classConvolution2D_1a8f2665a6a9a2ad89ecd60d0119188968}

# class `ConvolutionLayer2D` {#classConvolutionLayer2D}

```
class ConvolutionLayer2D
  : public Module< DTYPE >
```  

구성해 2-Dimensional Convolution Layer의 기능을 수행하는 모듈을 생성하는 클래스

Operator들을 뉴럴 네트워크의 서브 그래프로 구성해 2-Dimensional convolution Layer의 기능을 수행한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`ConvolutionLayer2D`](#classConvolutionLayer2D_1a0a51514f4250ab566ff1a29ede2846c0)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPadding,int use_bias,std::string pName)` | [ConvolutionLayer2D](#classConvolutionLayer2D) 클래스 생성자
`public inline virtual  `[`~ConvolutionLayer2D`](#classConvolutionLayer2D_1a12099a1799e812c7de9341844518e105)`()` | [ConvolutionLayer2D](#classConvolutionLayer2D) 클래스 소멸자
`public inline int `[`Alloc`](#classConvolutionLayer2D_1a6d951dcc0de4424e417ea0eba30d48ba)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPaddingRow,int pPaddingCol,int use_bias,std::string pName)` | 2D convolution Layer 그래프를 동적으로 할당 및 구성하는 메소드

## Members

#### `public inline  `[`ConvolutionLayer2D`](#classConvolutionLayer2D_1a0a51514f4250ab566ff1a29ede2846c0)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPadding,int use_bias,std::string pName)` {#classConvolutionLayer2D_1a0a51514f4250ab566ff1a29ede2846c0}

[ConvolutionLayer2D](#classConvolutionLayer2D) 클래스 생성자

ConvouutionLayer2D 클래스의 Alloc 함수를 호출한다. 
**See also**: Convolution2D<DTYPE>::Alloc(Operator<DTYPE> *pInput, int pNumInputChannel, int pNumOutputChannel, int pNumKernelRow, int pNumKernelCol, int pStrideRow, int pStrideCol, int pPaddingRow, int pPaddingCol, int use_bias, std::string pName)

#### `public inline virtual  `[`~ConvolutionLayer2D`](#classConvolutionLayer2D_1a12099a1799e812c7de9341844518e105)`()` {#classConvolutionLayer2D_1a12099a1799e812c7de9341844518e105}

[ConvolutionLayer2D](#classConvolutionLayer2D) 클래스 소멸자

단, 동적 할당 받은 Operator들은 NeuralNetwork에서 할당 해제한다.

#### `public inline int `[`Alloc`](#classConvolutionLayer2D_1a6d951dcc0de4424e417ea0eba30d48ba)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPaddingRow,int pPaddingCol,int use_bias,std::string pName)` {#classConvolutionLayer2D_1a6d951dcc0de4424e417ea0eba30d48ba}

2D convolution Layer 그래프를 동적으로 할당 및 구성하는 메소드

Input Operator의 Element에 대해 2D Convolution을 수행한다.

Input Operator의 Element에 대해 Weight를 이용해 2차원 합성 곱(2D Convolution)을 수행하고 Bias가 존재할 시 Bias를 합(Column Wise Addition)해 Output Operator로 내보내는 layer를 구성한다. 
#### Parameters
* `pInput` 해당 Layer의 Input에 해당하는 [Operator](#classOperator)

* `pNumInputChannel` 해당 Layer의 Input Operator의 Channel의 갯수, Input Channel에 대한 Dimension 

* `pNumOutputChannel` 해당 Layer의 Output Operator의 Channel의 갯수, Output Channel에 대한 Dimension 

* `pNumKernelRow` 2D Convolution Layer 커널의 Row Size 

* `pNumKernelCol` 2D Convolution Layer 커널의 Column Size 

* `pStrideRow` 2D Convolution Layer의 Row Stride Size 

* `pStrideCol` 2D Convolution Layer의 Column Stride Size 

* `pPaddingRow` 2D Convolution Layer의 Row Padding 값 

* `pPaddingCol` 2D Convolution Layer의 Column Padding 값 

* `use_bias` Bias 사용 유무, 0일 시 사용 안 함, 0이 아닐 시 사용 

* `pName` Module의 이름 

#### Returns
TRUE 

**See also**: [Convolution2D<DTYPE>::Convolution2D](#classConvolution2D_1a5beb3b40bafb285ae8e3263090750629)([Operator<DTYPE>](#classOperator) *pInput, [Operator<DTYPE>](#classOperator) *pWeight, int stride1, int stride2, std::string pName = "NO NAME") AddColWise<DTYPE>::AddColWise(Operator<DTYPE> *pInput, Operator<DTYPE> *pBias, std::string pName) [Module<DTYPE>::AnalyzeGraph(Operator<DTYPE> *pResultOperator)](#classModule_1a7a8ca0c6ddde4bffde9d806ff64ba614)

# class `CrossEntropy` {#classCrossEntropy}

```
class CrossEntropy
  : public LossFunction< DTYPE >
```  

Metric를 이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스

Cross Entropy 계산식을 이용해 뉴럴 네트워크의 순전파를 통해 계산된 출력 Tensor와 레이블 값의 손실 함수를 계산한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`CrossEntropy`](#classCrossEntropy_1a9a33d1185ee453c393860c3a1552f628)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,int epsilon)` | [CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자
`public inline  `[`CrossEntropy`](#classCrossEntropy_1af539d0934955e572dfa338c911ca213f)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | [CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자
`public inline  `[`CrossEntropy`](#classCrossEntropy_1a23d0632092775d81e85add781638f148)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,int epsilon,std::string pName)` | [CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자
`public inline  `[`~CrossEntropy`](#classCrossEntropy_1a20e18d255067837dda38df8ff884df27)`()` | [CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 소멸자
`public inline virtual int `[`Alloc`](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,int epsilon)` | [CrossEntropy](#classCrossEntropy) Lossfunction의 멤버 변수들을 동적 할당하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classCrossEntropy_1a4d4f5ad7e88301644ab173ef75b5eee9)`(int pTime)` | [CrossEntropy](#classCrossEntropy) LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classCrossEntropy_1addeb5ba89138297799b21d118ede3602)`(int pTime)` | [CrossEntropy](#classCrossEntropy) LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`CrossEntropy`](#classCrossEntropy_1a9a33d1185ee453c393860c3a1552f628)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,int epsilon)` {#classCrossEntropy_1a9a33d1185ee453c393860c3a1552f628}

[CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 epsilon을 매개변수로 전달하여 [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5) 메소드를 호출한다. 
#### Parameters
* `pOperator` [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `epsilon` 더미 변수, 값을 미 지정시 1e-6f로 초기화 

#### Returns
없음 

**See also**: [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5)

#### `public inline  `[`CrossEntropy`](#classCrossEntropy_1af539d0934955e572dfa338c911ca213f)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classCrossEntropy_1af539d0934955e572dfa338c911ca213f}

[CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 1e-6f에 해당하는 epsilon 값을 매개변수로 전달하여 [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5) 메소드를 호출한다. 
#### Parameters
* `pOperator` [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `pName` LossFunction의 이름 

#### Returns
없음 

**See also**: [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5)

#### `public inline  `[`CrossEntropy`](#classCrossEntropy_1a23d0632092775d81e85add781638f148)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,int epsilon,std::string pName)` {#classCrossEntropy_1a23d0632092775d81e85add781638f148}

[CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 epsilon을 매개변수로 전달하여 [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5) 메소드를 호출한다. 
#### Parameters
* `pOperator` [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `epsilon` 더미 변수 

* `pName` LossFunction의 이름 

#### Returns
없음 

**See also**: [CrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, int epsilon)](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5)

#### `public inline  `[`~CrossEntropy`](#classCrossEntropy_1a20e18d255067837dda38df8ff884df27)`()` {#classCrossEntropy_1a20e18d255067837dda38df8ff884df27}

[CrossEntropy](#classCrossEntropy)[LossFunction](#classLossFunction) 클래스 소멸자

#### Returns
없음

#### `public inline virtual int `[`Alloc`](#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,int epsilon)` {#classCrossEntropy_1a54c779f83f3af7e1f74528289a7614a5}

[CrossEntropy](#classCrossEntropy) Lossfunction의 멤버 변수들을 동적 할당하는 메소드

매개변수로 전달받은 Operator를 Input Operator에 할당하고 초기화 된 Result 텐서를 동적으로 할당 및 생성한다. 
#### Parameters
* `pOperator` [CrossEntropy](#classCrossEntropy) LossFunction의 입력에 해당하는 [Operator](#classOperator)

* `epsilon` 더미 변수 

#### Returns
TRUE

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classCrossEntropy_1a4d4f5ad7e88301644ab173ef75b5eee9)`(int pTime)` {#classCrossEntropy_1a4d4f5ad7e88301644ab173ef75b5eee9}

[CrossEntropy](#classCrossEntropy) LossFunction의 순전파를 수행하는 메소드

구성한 뉴럴 네트워크에서 얻어진 결과 값을 레이블 값과 비교해 Cross Entropy를 구한다 
#### Parameters
* `pTime` 입력 Tensor의 Time 축의 Dimension 

#### Returns
뉴럴 네트워크의 결과 값에 대한 Cross Entropy

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classCrossEntropy_1addeb5ba89138297799b21d118ede3602)`(int pTime)` {#classCrossEntropy_1addeb5ba89138297799b21d118ede3602}

[CrossEntropy](#classCrossEntropy) LossFunction의 역전파를 수행하는 메소드

구성한 뉴럴 네트워크에서 얻어진 [CrossEntropy](#classCrossEntropy) LossFunction에 대한 입력 Tensor의 Gradient를 계산한다 
#### Parameters
* `pTime` 입력 Tensor의 Time 축의 Dimension 

#### Returns
NULL

# class `DataLoader` {#classDataLoader}

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`DataLoader`](#classDataLoader_1ab068b9fb61b022430a5fd4e357c48b00)`(`[`Dataset`](#classDataset)`< DTYPE > * dataset,int batchSize,int useShuffle,int numOfWorker,int dropLast)` | 
`public virtual  `[`~DataLoader`](#classDataLoader_1a75bed33b2668a7262ed3d6576a6dd9e8)`()` | 
`public void `[`StartProcess`](#classDataLoader_1ab56c7b34da2522ee04b0880d092193e4)`()` | 
`public void `[`StopProcess`](#classDataLoader_1a2353547121b6b941c92464c1a42c6a3c)`()` | 
`public void `[`DistributeIdxOfData2Thread`](#classDataLoader_1ab5eacdd0affb0529681673d816b94fea)`()` | 
`public virtual void `[`MakeAllOfIndex`](#classDataLoader_1a2dff81a1f0ebe728999458424d15f315)`(std::vector< int > * pAllOfIndex)` | 
`public virtual void `[`DataPreprocess`](#classDataLoader_1a046f99f587d7046763b1df5c30f075e8)`()` | 
`public void `[`Push2IdxBuffer`](#classDataLoader_1a1e59af7e80cd086051f503088952d87d)`(std::vector< int > * setOfIdx)` | 
`public std::vector< int > * `[`GetIdxSetFromIdxBuffer`](#classDataLoader_1aab365477975ac3753f058fb936bf2e65)`()` | 
`public `[`Tensor`](#classTensor)`< DTYPE > * `[`Concatenate`](#classDataLoader_1a66ab19bddbe95dd2ccc2b6b610267c83)`(std::queue< `[`Tensor`](#classTensor)`< DTYPE > * > & setOfData)` | 
`public void `[`Push2GlobalBuffer`](#classDataLoader_1a79ec4b21d32eb4a0753ac3ecc1f5b4a2)`(std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * preprocessedData)` | 
`public std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetDataFromGlobalBuffer`](#classDataLoader_1a283d78594c4007d4ee4dfce688e94ccf)`()` | 
`public inline int `[`GetBatchSize`](#classDataLoader_1ac1127611ca1991c89448b107ac1db10a)`()` | 
`public inline int `[`GetWorkingSignal`](#classDataLoader_1a00f4ea62ec8d47d157ff7f0728cf7e80)`()` | 
`public inline int `[`GetNumOfEachDatasetMember`](#classDataLoader_1a89fffabc92f8592855ab4d32fc6f3b30)`()` | 
`public inline `[`Dataset`](#classDataset)`< DTYPE > * `[`GetDataset`](#classDataLoader_1a0880559eeabd33ada6e4ca43af4b0a0f)`()` | 

## Members

#### `public  `[`DataLoader`](#classDataLoader_1ab068b9fb61b022430a5fd4e357c48b00)`(`[`Dataset`](#classDataset)`< DTYPE > * dataset,int batchSize,int useShuffle,int numOfWorker,int dropLast)` {#classDataLoader_1ab068b9fb61b022430a5fd4e357c48b00}

#### `public virtual  `[`~DataLoader`](#classDataLoader_1a75bed33b2668a7262ed3d6576a6dd9e8)`()` {#classDataLoader_1a75bed33b2668a7262ed3d6576a6dd9e8}

#### `public void `[`StartProcess`](#classDataLoader_1ab56c7b34da2522ee04b0880d092193e4)`()` {#classDataLoader_1ab56c7b34da2522ee04b0880d092193e4}

#### `public void `[`StopProcess`](#classDataLoader_1a2353547121b6b941c92464c1a42c6a3c)`()` {#classDataLoader_1a2353547121b6b941c92464c1a42c6a3c}

#### `public void `[`DistributeIdxOfData2Thread`](#classDataLoader_1ab5eacdd0affb0529681673d816b94fea)`()` {#classDataLoader_1ab5eacdd0affb0529681673d816b94fea}

#### `public virtual void `[`MakeAllOfIndex`](#classDataLoader_1a2dff81a1f0ebe728999458424d15f315)`(std::vector< int > * pAllOfIndex)` {#classDataLoader_1a2dff81a1f0ebe728999458424d15f315}

#### `public virtual void `[`DataPreprocess`](#classDataLoader_1a046f99f587d7046763b1df5c30f075e8)`()` {#classDataLoader_1a046f99f587d7046763b1df5c30f075e8}

#### `public void `[`Push2IdxBuffer`](#classDataLoader_1a1e59af7e80cd086051f503088952d87d)`(std::vector< int > * setOfIdx)` {#classDataLoader_1a1e59af7e80cd086051f503088952d87d}

#### `public std::vector< int > * `[`GetIdxSetFromIdxBuffer`](#classDataLoader_1aab365477975ac3753f058fb936bf2e65)`()` {#classDataLoader_1aab365477975ac3753f058fb936bf2e65}

#### `public `[`Tensor`](#classTensor)`< DTYPE > * `[`Concatenate`](#classDataLoader_1a66ab19bddbe95dd2ccc2b6b610267c83)`(std::queue< `[`Tensor`](#classTensor)`< DTYPE > * > & setOfData)` {#classDataLoader_1a66ab19bddbe95dd2ccc2b6b610267c83}

#### `public void `[`Push2GlobalBuffer`](#classDataLoader_1a79ec4b21d32eb4a0753ac3ecc1f5b4a2)`(std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * preprocessedData)` {#classDataLoader_1a79ec4b21d32eb4a0753ac3ecc1f5b4a2}

#### `public std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetDataFromGlobalBuffer`](#classDataLoader_1a283d78594c4007d4ee4dfce688e94ccf)`()` {#classDataLoader_1a283d78594c4007d4ee4dfce688e94ccf}

#### `public inline int `[`GetBatchSize`](#classDataLoader_1ac1127611ca1991c89448b107ac1db10a)`()` {#classDataLoader_1ac1127611ca1991c89448b107ac1db10a}

#### `public inline int `[`GetWorkingSignal`](#classDataLoader_1a00f4ea62ec8d47d157ff7f0728cf7e80)`()` {#classDataLoader_1a00f4ea62ec8d47d157ff7f0728cf7e80}

#### `public inline int `[`GetNumOfEachDatasetMember`](#classDataLoader_1a89fffabc92f8592855ab4d32fc6f3b30)`()` {#classDataLoader_1a89fffabc92f8592855ab4d32fc6f3b30}

#### `public inline `[`Dataset`](#classDataset)`< DTYPE > * `[`GetDataset`](#classDataLoader_1a0880559eeabd33ada6e4ca43af4b0a0f)`()` {#classDataLoader_1a0880559eeabd33ada6e4ca43af4b0a0f}

# class `Dataset` {#classDataset}

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`Dataset`](#classDataset_1a117a5cf499442026ec65539e86d323b8)`()` | 
`public virtual  `[`~Dataset`](#classDataset_1ab4ca1cb7864616d827a224972852dc02)`()` | 
`public virtual void `[`Alloc`](#classDataset_1ad83a7518034d146d0ffffcdff5456fb8)`()` | 
`public virtual void `[`Dealloc`](#classDataset_1a94111198dbd5b5ba10c4aea5669b98a4)`()` | 
`public virtual std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetData`](#classDataset_1add9bbd1292520996a0d53661e9fe2274)`(int idx)` | 
`public virtual std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetDataOfPositiveLabel`](#classDataset_1af63feeb777bbfd323364d8728eb5bd94)`(int anchorIdx,int * pPosIdx)` | 
`public virtual std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetDataOfNegativeLabel`](#classDataset_1afd3328c1f081932195e8470ec3942b72)`(int anchorIdx,int * pNegIdx)` | 
`public void `[`SetLabel`](#classDataset_1a00dda88a3e668d0c09047053e9521e6c)`(const int * pLabel,int noLabel)` | 
`public void `[`SetLabel`](#classDataset_1a75923ba054ba36b97c91aaed509b3be9)`(const unsigned char * pLabel,int noLabel)` | 
`public inline virtual int `[`GetLabel`](#classDataset_1a7a80be63f47b9e7f6251f07b2e06b842)`(int idx)` | 
`public inline virtual int `[`GetLength`](#classDataset_1afde2f4837773a5cf14a2088a7337d1d5)`()` | 
`public int `[`GetNumOfDatasetMember`](#classDataset_1a0ed8c212dde5a144aa47d1fe15efa9e0)`()` | 
`public inline virtual void `[`CopyData`](#classDataset_1adf6ba25290bc6e809c41c6f01292ce44)`(int idx,DTYPE * pDest)` | 
`public inline virtual void `[`SetPosNegIndices`](#classDataset_1a0a23ae14b56a165779ef50163ed55387)`(std::vector< int > * pvPosIndex,std::vector< int > * pvNegIndex)` | 
`public inline std::vector< int > & `[`GetPositiveIndices`](#classDataset_1a5b4fee175817ab07ac6fbe9c3b41d079)`()` | 
`public inline std::vector< int > & `[`GetNegativeIndices`](#classDataset_1a41c487f8ec2b455e389f99f25d78ea9c)`()` | 
`public inline virtual int `[`GetPositiveIndex`](#classDataset_1ac15d95710ec3ad2fcb29137d53041da4)`(int idx)` | 
`public inline virtual int `[`GetNegativeIndex`](#classDataset_1a2163594d7e797e4188e251157e6f01c5)`(int idx)` | 

## Members

#### `public  `[`Dataset`](#classDataset_1a117a5cf499442026ec65539e86d323b8)`()` {#classDataset_1a117a5cf499442026ec65539e86d323b8}

#### `public virtual  `[`~Dataset`](#classDataset_1ab4ca1cb7864616d827a224972852dc02)`()` {#classDataset_1ab4ca1cb7864616d827a224972852dc02}

#### `public virtual void `[`Alloc`](#classDataset_1ad83a7518034d146d0ffffcdff5456fb8)`()` {#classDataset_1ad83a7518034d146d0ffffcdff5456fb8}

#### `public virtual void `[`Dealloc`](#classDataset_1a94111198dbd5b5ba10c4aea5669b98a4)`()` {#classDataset_1a94111198dbd5b5ba10c4aea5669b98a4}

#### `public virtual std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetData`](#classDataset_1add9bbd1292520996a0d53661e9fe2274)`(int idx)` {#classDataset_1add9bbd1292520996a0d53661e9fe2274}

#### `public virtual std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetDataOfPositiveLabel`](#classDataset_1af63feeb777bbfd323364d8728eb5bd94)`(int anchorIdx,int * pPosIdx)` {#classDataset_1af63feeb777bbfd323364d8728eb5bd94}

#### `public virtual std::vector< `[`Tensor`](#classTensor)`< DTYPE > * > * `[`GetDataOfNegativeLabel`](#classDataset_1afd3328c1f081932195e8470ec3942b72)`(int anchorIdx,int * pNegIdx)` {#classDataset_1afd3328c1f081932195e8470ec3942b72}

#### `public void `[`SetLabel`](#classDataset_1a00dda88a3e668d0c09047053e9521e6c)`(const int * pLabel,int noLabel)` {#classDataset_1a00dda88a3e668d0c09047053e9521e6c}

#### `public void `[`SetLabel`](#classDataset_1a75923ba054ba36b97c91aaed509b3be9)`(const unsigned char * pLabel,int noLabel)` {#classDataset_1a75923ba054ba36b97c91aaed509b3be9}

#### `public inline virtual int `[`GetLabel`](#classDataset_1a7a80be63f47b9e7f6251f07b2e06b842)`(int idx)` {#classDataset_1a7a80be63f47b9e7f6251f07b2e06b842}

#### `public inline virtual int `[`GetLength`](#classDataset_1afde2f4837773a5cf14a2088a7337d1d5)`()` {#classDataset_1afde2f4837773a5cf14a2088a7337d1d5}

#### `public int `[`GetNumOfDatasetMember`](#classDataset_1a0ed8c212dde5a144aa47d1fe15efa9e0)`()` {#classDataset_1a0ed8c212dde5a144aa47d1fe15efa9e0}

#### `public inline virtual void `[`CopyData`](#classDataset_1adf6ba25290bc6e809c41c6f01292ce44)`(int idx,DTYPE * pDest)` {#classDataset_1adf6ba25290bc6e809c41c6f01292ce44}

#### `public inline virtual void `[`SetPosNegIndices`](#classDataset_1a0a23ae14b56a165779ef50163ed55387)`(std::vector< int > * pvPosIndex,std::vector< int > * pvNegIndex)` {#classDataset_1a0a23ae14b56a165779ef50163ed55387}

#### `public inline std::vector< int > & `[`GetPositiveIndices`](#classDataset_1a5b4fee175817ab07ac6fbe9c3b41d079)`()` {#classDataset_1a5b4fee175817ab07ac6fbe9c3b41d079}

#### `public inline std::vector< int > & `[`GetNegativeIndices`](#classDataset_1a41c487f8ec2b455e389f99f25d78ea9c)`()` {#classDataset_1a41c487f8ec2b455e389f99f25d78ea9c}

#### `public inline virtual int `[`GetPositiveIndex`](#classDataset_1ac15d95710ec3ad2fcb29137d53041da4)`(int idx)` {#classDataset_1ac15d95710ec3ad2fcb29137d53041da4}

#### `public inline virtual int `[`GetNegativeIndex`](#classDataset_1a2163594d7e797e4188e251157e6f01c5)`(int idx)` {#classDataset_1a2163594d7e797e4188e251157e6f01c5}

# class `Dropout` {#classDropout}

```
class Dropout
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Dropout`](#classDropout_1acb7090ba8045011c8c5175e83fcdeb30)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 
`public inline  `[`Dropout`](#classDropout_1abd51138fedaeb265c1584d0ea14a7cba)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float pDroprate,std::string pName,int pLoadflag)` | 
`public inline  `[`~Dropout`](#classDropout_1afad2e18e52d939e6763e020b6d07ead2)`()` | 
`public inline int `[`Alloc`](#classDropout_1a5c30a5d6b102a293aca2085dce7cc55b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float pDroprate,int pLoadflag)` | 
`public inline void `[`Delete`](#classDropout_1adc02e8a3518aa6950eb6d9b86499ce5b)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classDropout_1ad9a0170b88f230007ecc496a12de3f84)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classDropout_1ad501c062c1975206e8854f22881ddf14)`(int pTime)` | 

## Members

#### `public inline  `[`Dropout`](#classDropout_1acb7090ba8045011c8c5175e83fcdeb30)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classDropout_1acb7090ba8045011c8c5175e83fcdeb30}

#### `public inline  `[`Dropout`](#classDropout_1abd51138fedaeb265c1584d0ea14a7cba)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float pDroprate,std::string pName,int pLoadflag)` {#classDropout_1abd51138fedaeb265c1584d0ea14a7cba}

#### `public inline  `[`~Dropout`](#classDropout_1afad2e18e52d939e6763e020b6d07ead2)`()` {#classDropout_1afad2e18e52d939e6763e020b6d07ead2}

#### `public inline int `[`Alloc`](#classDropout_1a5c30a5d6b102a293aca2085dce7cc55b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float pDroprate,int pLoadflag)` {#classDropout_1a5c30a5d6b102a293aca2085dce7cc55b}

#### `public inline void `[`Delete`](#classDropout_1adc02e8a3518aa6950eb6d9b86499ce5b)`()` {#classDropout_1adc02e8a3518aa6950eb6d9b86499ce5b}

#### `public inline virtual int `[`ForwardPropagate`](#classDropout_1ad9a0170b88f230007ecc496a12de3f84)`(int pTime)` {#classDropout_1ad9a0170b88f230007ecc496a12de3f84}

#### `public inline virtual int `[`BackPropagate`](#classDropout_1ad501c062c1975206e8854f22881ddf14)`(int pTime)` {#classDropout_1ad501c062c1975206e8854f22881ddf14}

# class `FewShotClassifier` {#classFewShotClassifier}

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`FewShotClassifier`](#classFewShotClassifier_1afd4cd751b6242a6c83315d1213d04831)`(int inputDim,int featureDim,const std::vector< std::string > vClassName,`[`NeuralNetwork`](#classNeuralNetwork)`< float > * pNN,int noRef,int * pRefLabel,float * pRefSample,int batchSize)` | 
`public  `[`FewShotClassifier`](#classFewShotClassifier_1a5e1cf99445c4675a49a7e4fa53d7d699)`(int inputDim,int featureDim,const std::vector< std::string > vClassName,`[`NeuralNetwork`](#classNeuralNetwork)`< float > * pNN,`[`KNearestNeighbor`](#classKNearestNeighbor)` * kNN)` | 
`public std::string `[`Recognize`](#classFewShotClassifier_1a27fd015fe4d3231caaf67e26c774423a)`(float * pInputSample,int k)` | 
`public float `[`GetAccuracy`](#classFewShotClassifier_1aeff452a2a72d74fb557a41f7e1f8ed28)`(int noTestSample,float * pTestSample,int * pLabel)` | 
`public void `[`AddReference`](#classFewShotClassifier_1ad7cbd965fb4147a540b5bb18febba51f)`(const char * className,float * pRefSample)` | 
`public int `[`FindClass`](#classFewShotClassifier_1acfd408b46029fa1a3815ed7d49e40e6d)`(const char * className)` | 

## Members

#### `public  `[`FewShotClassifier`](#classFewShotClassifier_1afd4cd751b6242a6c83315d1213d04831)`(int inputDim,int featureDim,const std::vector< std::string > vClassName,`[`NeuralNetwork`](#classNeuralNetwork)`< float > * pNN,int noRef,int * pRefLabel,float * pRefSample,int batchSize)` {#classFewShotClassifier_1afd4cd751b6242a6c83315d1213d04831}

#### `public  `[`FewShotClassifier`](#classFewShotClassifier_1a5e1cf99445c4675a49a7e4fa53d7d699)`(int inputDim,int featureDim,const std::vector< std::string > vClassName,`[`NeuralNetwork`](#classNeuralNetwork)`< float > * pNN,`[`KNearestNeighbor`](#classKNearestNeighbor)` * kNN)` {#classFewShotClassifier_1a5e1cf99445c4675a49a7e4fa53d7d699}

#### `public std::string `[`Recognize`](#classFewShotClassifier_1a27fd015fe4d3231caaf67e26c774423a)`(float * pInputSample,int k)` {#classFewShotClassifier_1a27fd015fe4d3231caaf67e26c774423a}

#### `public float `[`GetAccuracy`](#classFewShotClassifier_1aeff452a2a72d74fb557a41f7e1f8ed28)`(int noTestSample,float * pTestSample,int * pLabel)` {#classFewShotClassifier_1aeff452a2a72d74fb557a41f7e1f8ed28}

#### `public void `[`AddReference`](#classFewShotClassifier_1ad7cbd965fb4147a540b5bb18febba51f)`(const char * className,float * pRefSample)` {#classFewShotClassifier_1ad7cbd965fb4147a540b5bb18febba51f}

#### `public int `[`FindClass`](#classFewShotClassifier_1acfd408b46029fa1a3815ed7d49e40e6d)`(const char * className)` {#classFewShotClassifier_1acfd408b46029fa1a3815ed7d49e40e6d}

# class `GAN` {#classGAN}

```
class GAN
  : public NeuralNetwork< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`GAN`](#classGAN_1a485a7890354d931d2f727384ee8060b5)`()` | 
`public virtual  `[`~GAN`](#classGAN_1aa674ca6ad1fe8645591604d00e58f5b4)`()` | 
`public int `[`AllocLabel`](#classGAN_1a5ced95eb64ce34d1e99b5cd2e184cf65)`(float plabelValue)` | 
`public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`SetGenerator`](#classGAN_1a5590e634d5d8d33283e85b413624b098)`(`[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * pGen)` | 
`public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`SetDiscriminator`](#classGAN_1a198740b018110795a33f089709314375)`(`[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * pDiscLoss)` | 
`public `[`Tensorholder`](#classTensorholder)`< DTYPE > * `[`SetLabel`](#classGAN_1a8fcc2c8654b1498fc48b6089ad0a5696)`(`[`Tensorholder`](#classTensorholder)`< DTYPE > * pLabel)` | 
`public `[`Switch`](#classSwitch)`< DTYPE > * `[`SetSwitch`](#classGAN_1aff8a0cd54c63493358af350961463508)`(`[`Switch`](#classSwitch)`< DTYPE > * pSwitch)` | 
`public void `[`SetGANLossFunctions`](#classGAN_1a6eaf5392784f585c644d5d575fa17a88)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pGenLoss,`[`LossFunction`](#classLossFunction)`< DTYPE > * pDiscLoss)` | 
`public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`SetGeneratorLossFunction`](#classGAN_1ace1f80bbd25e498ad1911ecc671575ca)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pGenLoss)` | 
`public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`SetDiscriminatorLossFunction`](#classGAN_1ac20136c40e6ca3d8ce640f180a2441f4)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pDiscLoss)` | 
`public void `[`SetGANOptimizers`](#classGAN_1ae7f2b5c594fc3007a33b1d7147e52dd1)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pGenOpt,`[`Optimizer`](#classOptimizer)`< DTYPE > * pDiscOpt)` | 
`public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`SetGeneratorOptimizer`](#classGAN_1a8dafa4e173ed888890075b78dac86e17)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pGenOpt)` | 
`public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`SetDiscriminatorOptimizer`](#classGAN_1a73ba54c2e5013968c7bd0ac371c4e811)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pDiscOpt)` | 
`public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`GetGenerator`](#classGAN_1a6148b66565f745bbcbc338d09d6a388a)`()` | 
`public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`GetDiscriminator`](#classGAN_1a44a2ead7ceb083fe3d5d53e6636d0c05)`()` | 
`public `[`Tensorholder`](#classTensorholder)`< DTYPE > * `[`GetLabel`](#classGAN_1a26458184b7d1b3689c4e17340f3e07f9)`()` | 
`public `[`Switch`](#classSwitch)`< DTYPE > * `[`GetSwitch`](#classGAN_1af70967bb4f3c2b44b55792989207e45b)`()` | 
`public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`GetGeneratorLossFunction`](#classGAN_1a3e47203aa534111947de22551b273594)`()` | 
`public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`GetDiscriminatorLossFunction`](#classGAN_1a055ebf9b70adc7c523e8bb2cae1b9eb7)`()` | 
`public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`GetGeneratorOptimizer`](#classGAN_1a7cff900e1cd5c3e71a5ba4334a18c339)`()` | 
`public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`GetDiscriminatorOptimizer`](#classGAN_1a6c9800fcc6750f705cba67d9f231725c)`()` | 
`public int `[`TrainGenerator`](#classGAN_1a28df20395095ad5004b6c22ec68c54d1)`()` | 
`public int `[`TrainDiscriminator`](#classGAN_1a632348aaf9b03bed27eb83d754910a67)`()` | 
`public int `[`Generate`](#classGAN_1aab6f7efa0aad6be17bbe1e2f4aba3c8b)`()` | 
`public virtual int `[`TrainGeneratorOnCPU`](#classGAN_1a5ad0a83d17e35d5b76b9b7bf360338db)`()` | 
`public virtual int `[`TrainDiscriminatorOnCPU`](#classGAN_1a1f1f8f8070e7b50534fb77f0802829dc)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnCPU`](#classGAN_1af04453ffb96138c654d6cf408e389061)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnCPU`](#classGAN_1a5c99dea104a9a1287267d6292b09b293)`()` | 
`public int `[`GenerateOnCPU`](#classGAN_1a928c6f99e06d061e29a2640f6fd9829b)`()` | 
`public virtual int `[`TrainGeneratorOnGPU`](#classGAN_1a9ddd1d82f0466c2cd523585d12848721)`()` | 
`public virtual int `[`TrainDiscriminatorOnGPU`](#classGAN_1aa7cb8914285ebe663d48a7b3be1acefc)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnGPU`](#classGAN_1acf9d6cbad00941f035f97860664359d7)`()` | 
`public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnGPU`](#classGAN_1a12205964f1bcf665fcdcc3ce325829f2)`()` | 
`public int `[`GenerateOnGPU`](#classGAN_1ab4c605b6b642843d63c3a754a99d5456)`()` | 
`public int `[`ResetParameterGradient`](#classGAN_1a6fbb3bef953a3ed847093e96ca73a1b8)`()` | 
`public int `[`ResetGeneratorLossFunctionResult`](#classGAN_1ae88e2a427b7bc8c29318545e73749c93)`()` | 
`public int `[`ResetGeneratorLossFunctionGradient`](#classGAN_1a0de84743bff6ee5885e9d73a7fde5890)`()` | 
`public int `[`ResetDiscriminatorLossFunctionResult`](#classGAN_1a86bce2e2539bed246eab6f96a6d3d940)`()` | 
`public int `[`ResetDiscriminatorLossFunctionGradient`](#classGAN_1a803492a2eec163d90a55cb98d5daaccb)`()` | 
`public void `[`Clip`](#classGAN_1a2991d95a56c002de500944a8a52f57c0)`(float min,float max)` | 

## Members

#### `public  `[`GAN`](#classGAN_1a485a7890354d931d2f727384ee8060b5)`()` {#classGAN_1a485a7890354d931d2f727384ee8060b5}

#### `public virtual  `[`~GAN`](#classGAN_1aa674ca6ad1fe8645591604d00e58f5b4)`()` {#classGAN_1aa674ca6ad1fe8645591604d00e58f5b4}

#### `public int `[`AllocLabel`](#classGAN_1a5ced95eb64ce34d1e99b5cd2e184cf65)`(float plabelValue)` {#classGAN_1a5ced95eb64ce34d1e99b5cd2e184cf65}

#### `public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`SetGenerator`](#classGAN_1a5590e634d5d8d33283e85b413624b098)`(`[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * pGen)` {#classGAN_1a5590e634d5d8d33283e85b413624b098}

#### `public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`SetDiscriminator`](#classGAN_1a198740b018110795a33f089709314375)`(`[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * pDiscLoss)` {#classGAN_1a198740b018110795a33f089709314375}

#### `public `[`Tensorholder`](#classTensorholder)`< DTYPE > * `[`SetLabel`](#classGAN_1a8fcc2c8654b1498fc48b6089ad0a5696)`(`[`Tensorholder`](#classTensorholder)`< DTYPE > * pLabel)` {#classGAN_1a8fcc2c8654b1498fc48b6089ad0a5696}

#### `public `[`Switch`](#classSwitch)`< DTYPE > * `[`SetSwitch`](#classGAN_1aff8a0cd54c63493358af350961463508)`(`[`Switch`](#classSwitch)`< DTYPE > * pSwitch)` {#classGAN_1aff8a0cd54c63493358af350961463508}

#### `public void `[`SetGANLossFunctions`](#classGAN_1a6eaf5392784f585c644d5d575fa17a88)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pGenLoss,`[`LossFunction`](#classLossFunction)`< DTYPE > * pDiscLoss)` {#classGAN_1a6eaf5392784f585c644d5d575fa17a88}

#### `public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`SetGeneratorLossFunction`](#classGAN_1ace1f80bbd25e498ad1911ecc671575ca)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pGenLoss)` {#classGAN_1ace1f80bbd25e498ad1911ecc671575ca}

#### `public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`SetDiscriminatorLossFunction`](#classGAN_1ac20136c40e6ca3d8ce640f180a2441f4)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pDiscLoss)` {#classGAN_1ac20136c40e6ca3d8ce640f180a2441f4}

#### `public void `[`SetGANOptimizers`](#classGAN_1ae7f2b5c594fc3007a33b1d7147e52dd1)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pGenOpt,`[`Optimizer`](#classOptimizer)`< DTYPE > * pDiscOpt)` {#classGAN_1ae7f2b5c594fc3007a33b1d7147e52dd1}

#### `public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`SetGeneratorOptimizer`](#classGAN_1a8dafa4e173ed888890075b78dac86e17)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pGenOpt)` {#classGAN_1a8dafa4e173ed888890075b78dac86e17}

#### `public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`SetDiscriminatorOptimizer`](#classGAN_1a73ba54c2e5013968c7bd0ac371c4e811)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pDiscOpt)` {#classGAN_1a73ba54c2e5013968c7bd0ac371c4e811}

#### `public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`GetGenerator`](#classGAN_1a6148b66565f745bbcbc338d09d6a388a)`()` {#classGAN_1a6148b66565f745bbcbc338d09d6a388a}

#### `public `[`NeuralNetwork`](#classNeuralNetwork)`< DTYPE > * `[`GetDiscriminator`](#classGAN_1a44a2ead7ceb083fe3d5d53e6636d0c05)`()` {#classGAN_1a44a2ead7ceb083fe3d5d53e6636d0c05}

#### `public `[`Tensorholder`](#classTensorholder)`< DTYPE > * `[`GetLabel`](#classGAN_1a26458184b7d1b3689c4e17340f3e07f9)`()` {#classGAN_1a26458184b7d1b3689c4e17340f3e07f9}

#### `public `[`Switch`](#classSwitch)`< DTYPE > * `[`GetSwitch`](#classGAN_1af70967bb4f3c2b44b55792989207e45b)`()` {#classGAN_1af70967bb4f3c2b44b55792989207e45b}

#### `public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`GetGeneratorLossFunction`](#classGAN_1a3e47203aa534111947de22551b273594)`()` {#classGAN_1a3e47203aa534111947de22551b273594}

#### `public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`GetDiscriminatorLossFunction`](#classGAN_1a055ebf9b70adc7c523e8bb2cae1b9eb7)`()` {#classGAN_1a055ebf9b70adc7c523e8bb2cae1b9eb7}

#### `public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`GetGeneratorOptimizer`](#classGAN_1a7cff900e1cd5c3e71a5ba4334a18c339)`()` {#classGAN_1a7cff900e1cd5c3e71a5ba4334a18c339}

#### `public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`GetDiscriminatorOptimizer`](#classGAN_1a6c9800fcc6750f705cba67d9f231725c)`()` {#classGAN_1a6c9800fcc6750f705cba67d9f231725c}

#### `public int `[`TrainGenerator`](#classGAN_1a28df20395095ad5004b6c22ec68c54d1)`()` {#classGAN_1a28df20395095ad5004b6c22ec68c54d1}

#### `public int `[`TrainDiscriminator`](#classGAN_1a632348aaf9b03bed27eb83d754910a67)`()` {#classGAN_1a632348aaf9b03bed27eb83d754910a67}

#### `public int `[`Generate`](#classGAN_1aab6f7efa0aad6be17bbe1e2f4aba3c8b)`()` {#classGAN_1aab6f7efa0aad6be17bbe1e2f4aba3c8b}

#### `public virtual int `[`TrainGeneratorOnCPU`](#classGAN_1a5ad0a83d17e35d5b76b9b7bf360338db)`()` {#classGAN_1a5ad0a83d17e35d5b76b9b7bf360338db}

#### `public virtual int `[`TrainDiscriminatorOnCPU`](#classGAN_1a1f1f8f8070e7b50534fb77f0802829dc)`()` {#classGAN_1a1f1f8f8070e7b50534fb77f0802829dc}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnCPU`](#classGAN_1af04453ffb96138c654d6cf408e389061)`()` {#classGAN_1af04453ffb96138c654d6cf408e389061}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnCPU`](#classGAN_1a5c99dea104a9a1287267d6292b09b293)`()` {#classGAN_1a5c99dea104a9a1287267d6292b09b293}

#### `public int `[`GenerateOnCPU`](#classGAN_1a928c6f99e06d061e29a2640f6fd9829b)`()` {#classGAN_1a928c6f99e06d061e29a2640f6fd9829b}

#### `public virtual int `[`TrainGeneratorOnGPU`](#classGAN_1a9ddd1d82f0466c2cd523585d12848721)`()` {#classGAN_1a9ddd1d82f0466c2cd523585d12848721}

#### `public virtual int `[`TrainDiscriminatorOnGPU`](#classGAN_1aa7cb8914285ebe663d48a7b3be1acefc)`()` {#classGAN_1aa7cb8914285ebe663d48a7b3be1acefc}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutRealOnGPU`](#classGAN_1acf9d6cbad00941f035f97860664359d7)`()` {#classGAN_1acf9d6cbad00941f035f97860664359d7}

#### `public virtual int `[`ComputeGradientOfDiscriminatorAboutFakeOnGPU`](#classGAN_1a12205964f1bcf665fcdcc3ce325829f2)`()` {#classGAN_1a12205964f1bcf665fcdcc3ce325829f2}

#### `public int `[`GenerateOnGPU`](#classGAN_1ab4c605b6b642843d63c3a754a99d5456)`()` {#classGAN_1ab4c605b6b642843d63c3a754a99d5456}

#### `public int `[`ResetParameterGradient`](#classGAN_1a6fbb3bef953a3ed847093e96ca73a1b8)`()` {#classGAN_1a6fbb3bef953a3ed847093e96ca73a1b8}

#### `public int `[`ResetGeneratorLossFunctionResult`](#classGAN_1ae88e2a427b7bc8c29318545e73749c93)`()` {#classGAN_1ae88e2a427b7bc8c29318545e73749c93}

#### `public int `[`ResetGeneratorLossFunctionGradient`](#classGAN_1a0de84743bff6ee5885e9d73a7fde5890)`()` {#classGAN_1a0de84743bff6ee5885e9d73a7fde5890}

#### `public int `[`ResetDiscriminatorLossFunctionResult`](#classGAN_1a86bce2e2539bed246eab6f96a6d3d940)`()` {#classGAN_1a86bce2e2539bed246eab6f96a6d3d940}

#### `public int `[`ResetDiscriminatorLossFunctionGradient`](#classGAN_1a803492a2eec163d90a55cb98d5daaccb)`()` {#classGAN_1a803492a2eec163d90a55cb98d5daaccb}

#### `public void `[`Clip`](#classGAN_1a2991d95a56c002de500944a8a52f57c0)`(float min,float max)` {#classGAN_1a2991d95a56c002de500944a8a52f57c0}

# class `GaussianNoiseGenerator` {#classGaussianNoiseGenerator}

```
class GaussianNoiseGenerator
  : public NoiseGenerator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1ac5b197b17864d63111ede68afc20bfca)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,float mean,float stddev,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` | 
`public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1ac526f687dfa847d0c9b8ac17a457f3b7)`(`[`Shape`](#classShape)` * pShape,float mean,float stddev,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` | 
`public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1ac7387087fc9be62988c7a3d972a62643)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,float mean,float stddev,float pTrunc,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` | 
`public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1a0d4f06510cdba07c74cd1cec48229c14)`(`[`Shape`](#classShape)` * pShape,float mean,float stddev,float pTrunc,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` | 
`public inline  `[`~GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1a8d8787c2fa17c5b4b5a495a9490cd2cf)`()` | 
`public inline void `[`StartProduce`](#classGaussianNoiseGenerator_1ab22477bf3d686066759dc98d0f449e34)`()` | 
`public inline void `[`StopProduce`](#classGaussianNoiseGenerator_1ad1419cb933b92e8ad1faca250c54284d)`()` | 
`public inline int `[`GenerateNoise`](#classGaussianNoiseGenerator_1a06b812ccb68081bb4d0c9e6912ebdc17)`()` | 
`public inline int `[`AddNoise2Buffer`](#classGaussianNoiseGenerator_1ac72a2a61640a48ae92d5828297d697d0)`(`[`Tensor`](#classTensor)`< DTYPE > * noise)` | 
`public inline `[`Tensor`](#classTensor)`< DTYPE > * `[`GetNoiseFromBuffer`](#classGaussianNoiseGenerator_1a774f3131654d374ce5dd158d6db468fa)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classGaussianNoiseGenerator_1a03d74cffd843533fbfc230e0d9d912fe)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classGaussianNoiseGenerator_1aeaddb74aeb0ccd9bbd24c0fd04570dab)`(int pTime)` | 

## Members

#### `public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1ac5b197b17864d63111ede68afc20bfca)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,float mean,float stddev,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` {#classGaussianNoiseGenerator_1ac5b197b17864d63111ede68afc20bfca}

#### `public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1ac526f687dfa847d0c9b8ac17a457f3b7)`(`[`Shape`](#classShape)` * pShape,float mean,float stddev,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` {#classGaussianNoiseGenerator_1ac526f687dfa847d0c9b8ac17a457f3b7}

#### `public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1ac7387087fc9be62988c7a3d972a62643)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,float mean,float stddev,float pTrunc,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` {#classGaussianNoiseGenerator_1ac7387087fc9be62988c7a3d972a62643}

#### `public inline  `[`GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1a0d4f06510cdba07c74cd1cec48229c14)`(`[`Shape`](#classShape)` * pShape,float mean,float stddev,float pTrunc,IsTruncated pTruncated,IsUseTime pAnswer,std::string pName)` {#classGaussianNoiseGenerator_1a0d4f06510cdba07c74cd1cec48229c14}

#### `public inline  `[`~GaussianNoiseGenerator`](#classGaussianNoiseGenerator_1a8d8787c2fa17c5b4b5a495a9490cd2cf)`()` {#classGaussianNoiseGenerator_1a8d8787c2fa17c5b4b5a495a9490cd2cf}

#### `public inline void `[`StartProduce`](#classGaussianNoiseGenerator_1ab22477bf3d686066759dc98d0f449e34)`()` {#classGaussianNoiseGenerator_1ab22477bf3d686066759dc98d0f449e34}

#### `public inline void `[`StopProduce`](#classGaussianNoiseGenerator_1ad1419cb933b92e8ad1faca250c54284d)`()` {#classGaussianNoiseGenerator_1ad1419cb933b92e8ad1faca250c54284d}

#### `public inline int `[`GenerateNoise`](#classGaussianNoiseGenerator_1a06b812ccb68081bb4d0c9e6912ebdc17)`()` {#classGaussianNoiseGenerator_1a06b812ccb68081bb4d0c9e6912ebdc17}

#### `public inline int `[`AddNoise2Buffer`](#classGaussianNoiseGenerator_1ac72a2a61640a48ae92d5828297d697d0)`(`[`Tensor`](#classTensor)`< DTYPE > * noise)` {#classGaussianNoiseGenerator_1ac72a2a61640a48ae92d5828297d697d0}

#### `public inline `[`Tensor`](#classTensor)`< DTYPE > * `[`GetNoiseFromBuffer`](#classGaussianNoiseGenerator_1a774f3131654d374ce5dd158d6db468fa)`()` {#classGaussianNoiseGenerator_1a774f3131654d374ce5dd158d6db468fa}

#### `public inline virtual int `[`ForwardPropagate`](#classGaussianNoiseGenerator_1a03d74cffd843533fbfc230e0d9d912fe)`(int pTime)` {#classGaussianNoiseGenerator_1a03d74cffd843533fbfc230e0d9d912fe}

#### `public inline virtual int `[`BackPropagate`](#classGaussianNoiseGenerator_1aeaddb74aeb0ccd9bbd24c0fd04570dab)`(int pTime)` {#classGaussianNoiseGenerator_1aeaddb74aeb0ccd9bbd24c0fd04570dab}

# class `GlobalAvaragePooling2D` {#classGlobalAvaragePooling2D}

```
class GlobalAvaragePooling2D
  : public Operator< DTYPE >
```  

Row * Colunm 공간을 GlobalAvaragePooling하는 클래스.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`GlobalAvaragePooling2D`](#classGlobalAvaragePooling2D_1a9e1592091dd62880912d9d258c7363ad)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` | GlobalAvaragePooling2D의 생성자.
`public inline virtual  `[`~GlobalAvaragePooling2D`](#classGlobalAvaragePooling2D_1aeec236ca89e621890df159b51b19e90b)`()` | GlobalAvaragePooling2D의 소멸자.
`public inline int `[`Alloc`](#classGlobalAvaragePooling2D_1a263d8a716c132862970c1b0b081139ae)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 파라미터로 받은 pInput으로부터 맴버 변수들을 초기화 한다.
`public inline virtual int `[`ForwardPropagate`](#classGlobalAvaragePooling2D_1ae506cb847b78140a1ee89812992aca97)`(int pTime)` | GlobalAvaragePooling2D의 ForwardPropagate 매소드
`public inline virtual int `[`BackPropagate`](#classGlobalAvaragePooling2D_1aa80e1155774c758544558dcc91a260a9)`(int pTime)` | GlobalAvaragePooling2D의 BackPropagate 매소드

## Members

#### `public inline  `[`GlobalAvaragePooling2D`](#classGlobalAvaragePooling2D_1a9e1592091dd62880912d9d258c7363ad)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` {#classGlobalAvaragePooling2D_1a9e1592091dd62880912d9d258c7363ad}

GlobalAvaragePooling2D의 생성자.

파라미터로 받은 pInput으로 Alloc한다. 
#### Parameters
* `pInput` GlobalAvaragePooling2D할 대상 [Operator](#classOperator). 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pInput)](#classGlobalAvaragePooling2D_1a263d8a716c132862970c1b0b081139ae).

#### `public inline virtual  `[`~GlobalAvaragePooling2D`](#classGlobalAvaragePooling2D_1aeec236ca89e621890df159b51b19e90b)`()` {#classGlobalAvaragePooling2D_1aeec236ca89e621890df159b51b19e90b}

GlobalAvaragePooling2D의 소멸자.

#### `public inline int `[`Alloc`](#classGlobalAvaragePooling2D_1a263d8a716c132862970c1b0b081139ae)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classGlobalAvaragePooling2D_1a263d8a716c132862970c1b0b081139ae}

파라미터로 받은 pInput으로부터 맴버 변수들을 초기화 한다.

Result와 Gradient를 저장하기 위해 pInput의 Shape과 같은 dim을 갖는 Tensor를 생성한다. 
#### Parameters
* `pInput` 생성 할 Tensor의 Shape정보를 가진 [Operator](#classOperator)

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`ForwardPropagate`](#classGlobalAvaragePooling2D_1ae506cb847b78140a1ee89812992aca97)`(int pTime)` {#classGlobalAvaragePooling2D_1ae506cb847b78140a1ee89812992aca97}

GlobalAvaragePooling2D의 ForwardPropagate 매소드

input의 row, col상의 값들들 모두 더하고 m_divisor로 나눈 값을 result Tensor에 저장한다. 
#### Parameters
* `pTime` pInput의 m_timesize값, default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classGlobalAvaragePooling2D_1aa80e1155774c758544558dcc91a260a9)`(int pTime)` {#classGlobalAvaragePooling2D_1aa80e1155774c758544558dcc91a260a9}

GlobalAvaragePooling2D의 BackPropagate 매소드

Input_grad에 계산한 Gradient / m_divisor 한 값을 더한다. 
#### Parameters
* `pTime` pInput의 m_timesize값, default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `GradientDescentOptimizer` {#classGradientDescentOptimizer}

```
class GradientDescentOptimizer
  : public Optimizer< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`GradientDescentOptimizer`](#classGradientDescentOptimizer_1a308ba6cac844c89e54471859d5da6285)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,OptimizeDirection pOptimizeDirection)` | GradientDescentOptimizer의 생성자.
`public inline  `[`GradientDescentOptimizer`](#classGradientDescentOptimizer_1a41d48f02cf8465c2ffde25f47198d930)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,OptimizeDirection pOptimizeDirection)` | GradientDescentOptimizer의 생성자.
`public inline  `[`GradientDescentOptimizer`](#classGradientDescentOptimizer_1a04ff84018ebe89fbb5fa8a1bdbfb428e)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,float weightDecayRate,OptimizeDirection pOptimizeDirection)` | GradientDescentOptimizer의 생성자.
`public inline  `[`~GradientDescentOptimizer`](#classGradientDescentOptimizer_1af4344616b07632306e678037ce6c89bb)`()` | GradientDescentOptimizer의 소멸자
`public inline int `[`Alloc`](#classGradientDescentOptimizer_1ab968000d204c52e6cb349204ddbc4cd1)`()` | Optimizer의 Alloc 매소드
`public inline int `[`Alloc`](#classGradientDescentOptimizer_1a252fb90356ce7f3bcdd7770d078f2501)`(float momentum)` | Optimizer의 Alloc 매소드
`public inline int `[`Delete`](#classGradientDescentOptimizer_1af4758fdc5cd03534a82846cea2969dd3)`()` | 
`public inline void `[`InitializeAttributeForGPU`](#classGradientDescentOptimizer_1a3f91a71f3153a5add223200092cced67)`(unsigned int idOfDevice)` | m_aaVelocity내부의 Tensor의 device를 idOfDevice번째 GPU로 바꾼다.
`public inline virtual int `[`UpdateParameter`](#classGradientDescentOptimizer_1ae6fde8288f07c36b625fb2772a4154d3)`()` | 파라미터 값들을 업데이트 하는 메소드
`public inline virtual int `[`UpdateParameter`](#classGradientDescentOptimizer_1ae9ee1f4f549d532d5011ce6ac6848976)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` | 파라미터 값들을 업데이트 하는 메소드
`public inline int `[`UpdateParameter`](#classGradientDescentOptimizer_1a5f8c15ae8c990f306f36c287f05d258e)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * pVelocity)` | 파라미터 값들을 업데이트 하는 메소드

## Members

#### `public inline  `[`GradientDescentOptimizer`](#classGradientDescentOptimizer_1a308ba6cac844c89e54471859d5da6285)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,OptimizeDirection pOptimizeDirection)` {#classGradientDescentOptimizer_1a308ba6cac844c89e54471859d5da6285}

GradientDescentOptimizer의 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 

* `pLearningRate` Optimizer의 learning rate 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int [Alloc()](#classGradientDescentOptimizer_1ab968000d204c52e6cb349204ddbc4cd1)

#### `public inline  `[`GradientDescentOptimizer`](#classGradientDescentOptimizer_1a41d48f02cf8465c2ffde25f47198d930)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,OptimizeDirection pOptimizeDirection)` {#classGradientDescentOptimizer_1a41d48f02cf8465c2ffde25f47198d930}

GradientDescentOptimizer의 생성자.

맴버변수들을 초기화하고 momentum값을 파라미터로 하는 Alloc 매소드를 호출한다. 
#### Parameters
* `pParameterContainer` 

* `pLearningRate` Optimizer의 learning rate 

* `momentum` Optimize의 momentum 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int [Alloc(float momentum)](#classGradientDescentOptimizer_1a252fb90356ce7f3bcdd7770d078f2501)

#### `public inline  `[`GradientDescentOptimizer`](#classGradientDescentOptimizer_1a04ff84018ebe89fbb5fa8a1bdbfb428e)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,float weightDecayRate,OptimizeDirection pOptimizeDirection)` {#classGradientDescentOptimizer_1a04ff84018ebe89fbb5fa8a1bdbfb428e}

GradientDescentOptimizer의 생성자.

맴버변수들을 초기화하고 momentum값을 파라미터로 하는 Alloc 매소드를 호출한다. 
#### Parameters
* `pParameterContainer` 

* `pLearningRate` Optimizer의 learning rate 

* `momentum` Optimize의 momentum 

* `weightDecayRate` @paramp OptimizeDirection Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int [Alloc(float momentum)](#classGradientDescentOptimizer_1a252fb90356ce7f3bcdd7770d078f2501)

#### `public inline  `[`~GradientDescentOptimizer`](#classGradientDescentOptimizer_1af4344616b07632306e678037ce6c89bb)`()` {#classGradientDescentOptimizer_1af4344616b07632306e678037ce6c89bb}

GradientDescentOptimizer의 소멸자

#### Returns
없음

#### `public inline int `[`Alloc`](#classGradientDescentOptimizer_1ab968000d204c52e6cb349204ddbc4cd1)`()` {#classGradientDescentOptimizer_1ab968000d204c52e6cb349204ddbc4cd1}

Optimizer의 Alloc 매소드

맴버 변수 m_ppParameter와 m_numOfParameter를 초기화한다. 
#### Returns
성공 시 TRUE 

**See also**: [Container](#classContainer)<[Operator<DTYPE>](#classOperator) *>* GetTrainableTensor() 

**See also**: int GetTrainableTensorDegree()

#### `public inline int `[`Alloc`](#classGradientDescentOptimizer_1a252fb90356ce7f3bcdd7770d078f2501)`(float momentum)` {#classGradientDescentOptimizer_1a252fb90356ce7f3bcdd7770d078f2501}

Optimizer의 Alloc 매소드

맴버 변수 m_aaVelocity, m_momentum를 초기화 한다.

m_aaVelocity에 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다. 
#### Parameters
* `momentum` Optimizer의 monentum값 

#### Returns
성공 시 TRUE 

**See also**: int [Alloc()](#classGradientDescentOptimizer_1ab968000d204c52e6cb349204ddbc4cd1)

#### `public inline int `[`Delete`](#classGradientDescentOptimizer_1af4758fdc5cd03534a82846cea2969dd3)`()` {#classGradientDescentOptimizer_1af4758fdc5cd03534a82846cea2969dd3}

#### `public inline void `[`InitializeAttributeForGPU`](#classGradientDescentOptimizer_1a3f91a71f3153a5add223200092cced67)`(unsigned int idOfDevice)` {#classGradientDescentOptimizer_1a3f91a71f3153a5add223200092cced67}

m_aaVelocity내부의 Tensor의 device를 idOfDevice번째 GPU로 바꾼다.

#### Parameters
* `idOfDevice` 사용 하는 GPU번호

#### `public inline virtual int `[`UpdateParameter`](#classGradientDescentOptimizer_1ae6fde8288f07c36b625fb2772a4154d3)`()` {#classGradientDescentOptimizer_1ae6fde8288f07c36b625fb2772a4154d3}

파라미터 값들을 업데이트 하는 메소드

m_momentum값에 따라 다른 UpdataParameter를 호출한다. 
#### Returns
성공 시 TRUE 

**See also**: int [UpdateParameter(Operator<DTYPE> *pParameter)](#classGradientDescentOptimizer_1ae9ee1f4f549d532d5011ce6ac6848976)

**See also**: int [UpdateParameter(Operator<DTYPE> *pParameter, Tensor<DTYPE> *pVelocity)](#classGradientDescentOptimizer_1a5f8c15ae8c990f306f36c287f05d258e)

#### `public inline virtual int `[`UpdateParameter`](#classGradientDescentOptimizer_1ae9ee1f4f549d532d5011ce6ac6848976)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` {#classGradientDescentOptimizer_1ae9ee1f4f549d532d5011ce6ac6848976}

파라미터 값들을 업데이트 하는 메소드

Parameter안에 있는 Tensor의 새로 계산된 gradinet값과 learning_rate의 곱, weightDecayRate와 기존 weight(trainable_date)의 곱으로 weight(trainable_date)값을 업데이트한다. 
#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

#### Returns
성공 시 TRUE

#### `public inline int `[`UpdateParameter`](#classGradientDescentOptimizer_1a5f8c15ae8c990f306f36c287f05d258e)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * pVelocity)` {#classGradientDescentOptimizer_1a5f8c15ae8c990f306f36c287f05d258e}

파라미터 값들을 업데이트 하는 메소드

Parameter안에 있는 Tensor의 새로 계산된 gradinet값과 learning_rate의 곱, weightDecayRate와 기존 weight(trainable_date)의 곱으로 weight(trainable_date)값을 업데이트한다.

momentum과 pVelocity의 곱과 learnung_rate와 gradient의 곱으로 pVelocity의 값을 업데이트 한다. 
#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pVelocity` 업데이트 할 pVelocity 

#### Returns
성공 시 TURE

# class `HingeLoss` {#classHingeLoss}

```
class HingeLoss
  : public LossFunction< DTYPE >
```  

Metric를 이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스

Hinge Loss 계산 식을 이용해 뉴럴 네트워크의 순전파를 통해 계산된 출력 Tensor와 레이블 값의 손실 함수를 계산한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`HingeLoss`](#classHingeLoss_1a1fd8f684e9fc55fa6f520cc6d9e95240)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,float theta)` | [HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 생성자
`public inline  `[`HingeLoss`](#classHingeLoss_1af5cf855a84b382ca3948dbd9218d1279)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | [HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 생성자
`public inline  `[`HingeLoss`](#classHingeLoss_1a332c2d14aa13dea8833d244f91bfa87c)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,float theta,std::string pName)` | [HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 생성자
`public inline  `[`~HingeLoss`](#classHingeLoss_1a27cb9c3fcce4bc2eee68cb5a921d1b87)`()` | [HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 소멸자
`public inline int `[`Alloc`](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,float theta)` | [HingeLoss](#classHingeLoss) Lossfunction의 멤버 변수들을 동적 할당하는 메소드
`public inline virtual void `[`Delete`](#classHingeLoss_1a38f635376808e0609ebb99daa09354f2)`()` | [LossFunction](#classLossFunction) 클래스의 메모리를 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classHingeLoss_1ad839f1997f80de41ca4da2282b85e0f9)`(int timeIdx)` | GPU 동작 모드에서의 [HingeLoss](#classHingeLoss) LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classHingeLoss_1abc6ab97e970a292e9611b9ec2739a9f3)`(int pTime)` | GPU 동작 모드에서의 [HingeLoss](#classHingeLoss) LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`HingeLoss`](#classHingeLoss_1a1fd8f684e9fc55fa6f520cc6d9e95240)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,float theta)` {#classHingeLoss_1a1fd8f684e9fc55fa6f520cc6d9e95240}

[HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 theta을 매개변수로 전달하여 [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936) 메소드를 호출한다. 
#### Parameters
* `pOperator` [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `theta` alloc 메소드의 theta 값으로 전달할 파라미터, 값을 지정하지 않을 시 1.f로 초기화 

#### Returns
없음 

**See also**: [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936)

#### `public inline  `[`HingeLoss`](#classHingeLoss_1af5cf855a84b382ca3948dbd9218d1279)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classHingeLoss_1af5cf855a84b382ca3948dbd9218d1279}

[HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 1.f에 해당하는 theta 값 매개변수로 전달하여 [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936) 메소드를 호출한다. 
#### Parameters
* `pOperator` [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `pName` LossFunction의 이름 

#### Returns
없음 

**See also**: [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936)

#### `public inline  `[`HingeLoss`](#classHingeLoss_1a332c2d14aa13dea8833d244f91bfa87c)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,float theta,std::string pName)` {#classHingeLoss_1a332c2d14aa13dea8833d244f91bfa87c}

[HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 theta을 매개변수로 전달하여 [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936) 메소드를 호출한다. 
#### Parameters
* `pOperator` [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `theta` alloc 메소드의 theta 값으로 전달할 파라미터 

**See also**: [HingeLoss<DTYPE>::Alloc(Operator<DTYPE> *pOperator, float theta)](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936)

#### `public inline  `[`~HingeLoss`](#classHingeLoss_1a27cb9c3fcce4bc2eee68cb5a921d1b87)`()` {#classHingeLoss_1a27cb9c3fcce4bc2eee68cb5a921d1b87}

[HingeLoss](#classHingeLoss)[LossFunction](#classLossFunction) 클래스 소멸자

#### Returns
없음

#### `public inline int `[`Alloc`](#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,float theta)` {#classHingeLoss_1ad279a4a7cf77d9d22029049f5227e936}

[HingeLoss](#classHingeLoss) Lossfunction의 멤버 변수들을 동적 할당하는 메소드

매개변수로 전달받은 Operator를 Input Operator에 할당하고 초기화 된 Result 텐서를 동적으로 할당 및 생성한다.

역전파를 위한 인덱스 더미 텐서를 동적으로 할당 및 생성하고 theta 값을 초기화한다. 
#### Parameters
* `pOperator` [CrossEntropy](#classCrossEntropy) LossFunction의 입력에 해당하는 [Operator](#classOperator)

* `theta` LossFunction의 멤버 변수 theta에 할당할 값 

#### Returns
TRUE

#### `public inline virtual void `[`Delete`](#classHingeLoss_1a38f635376808e0609ebb99daa09354f2)`()` {#classHingeLoss_1a38f635376808e0609ebb99daa09354f2}

[LossFunction](#classLossFunction) 클래스의 메모리를 할당 해제하는 메소드

Index for BackPropagation Tensor가 존재할 경우 Tensor의 메모리를 할당 해제하고 0으로 초기화한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classHingeLoss_1ad839f1997f80de41ca4da2282b85e0f9)`(int timeIdx)` {#classHingeLoss_1ad839f1997f80de41ca4da2282b85e0f9}

GPU 동작 모드에서의 [HingeLoss](#classHingeLoss) LossFunction의 순전파를 수행하는 메소드

구성한 뉴럴 네트워크에서 얻어진 결과 값을 레이블 값과 비교해 Hinge Loss 값을 구한다 
#### Parameters
* `timeIdx` Time 축의 인덱스, 미지정 시 0으로 초기화 

#### Returns
뉴럴 네트워크 결과 값에 대한 Hinge Loss

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classHingeLoss_1abc6ab97e970a292e9611b9ec2739a9f3)`(int pTime)` {#classHingeLoss_1abc6ab97e970a292e9611b9ec2739a9f3}

GPU 동작 모드에서의 [HingeLoss](#classHingeLoss) LossFunction의 역전파를 수행하는 메소드

구성한 뉴럴 네트워크에서 얻어진 [HingeLoss](#classHingeLoss) LossFunction에 대한 입력 Tensor의 Gradient를 계산한다 
#### Parameters
* `pTIme` Time 축의 인덱스, 미지정 시 0으로 초기화 

#### Returns
NULL

# class `KNearestNeighbor` {#classKNearestNeighbor}

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`KNearestNeighbor`](#classKNearestNeighbor_1addce391444a16e29943d4f366107ea21)`()` | 
`public  `[`KNearestNeighbor`](#classKNearestNeighbor_1ada5e2880030688a4b2bad199eb017f65)`(int dim,int noClass,int noRef,int * pRefLabel,float * pRefVector)` | 
`public virtual  `[`~KNearestNeighbor`](#classKNearestNeighbor_1ab54b4b3a500a79b9c4656f55ca1b43ba)`()` | 
`public void `[`AddReference`](#classKNearestNeighbor_1aec217b766f1a70bb1e5743a99a737b4a)`(int label,float * pRefVector)` | 
`public int `[`Recognize`](#classKNearestNeighbor_1a6f3d5f4a8ea89282e79d742950b842f0)`(float * pInput,int k)` | 
`public float `[`GetAccuracy`](#classKNearestNeighbor_1a032c332fb53270577542c5bc1eb2588d)`(int noTestSamples,int * pTestLabels,float * pTestVectors,int k)` | 

## Members

#### `public inline  `[`KNearestNeighbor`](#classKNearestNeighbor_1addce391444a16e29943d4f366107ea21)`()` {#classKNearestNeighbor_1addce391444a16e29943d4f366107ea21}

#### `public  `[`KNearestNeighbor`](#classKNearestNeighbor_1ada5e2880030688a4b2bad199eb017f65)`(int dim,int noClass,int noRef,int * pRefLabel,float * pRefVector)` {#classKNearestNeighbor_1ada5e2880030688a4b2bad199eb017f65}

#### `public virtual  `[`~KNearestNeighbor`](#classKNearestNeighbor_1ab54b4b3a500a79b9c4656f55ca1b43ba)`()` {#classKNearestNeighbor_1ab54b4b3a500a79b9c4656f55ca1b43ba}

#### `public void `[`AddReference`](#classKNearestNeighbor_1aec217b766f1a70bb1e5743a99a737b4a)`(int label,float * pRefVector)` {#classKNearestNeighbor_1aec217b766f1a70bb1e5743a99a737b4a}

#### `public int `[`Recognize`](#classKNearestNeighbor_1a6f3d5f4a8ea89282e79d742950b842f0)`(float * pInput,int k)` {#classKNearestNeighbor_1a6f3d5f4a8ea89282e79d742950b842f0}

#### `public float `[`GetAccuracy`](#classKNearestNeighbor_1a032c332fb53270577542c5bc1eb2588d)`(int noTestSamples,int * pTestLabels,float * pTestVectors,int k)` {#classKNearestNeighbor_1a032c332fb53270577542c5bc1eb2588d}

# class `Linear` {#classLinear}

```
class Linear
  : public Module< DTYPE >
```  

구성해 fully connected layer의 기능을 수행하는 모듈을 생성하는 클래스

Operator들을 뉴럴 네트워크의 서브 그래프로 구성해 fully connected layer의 기능을 수행한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Linear`](#classLinear_1aa748db4f994e9ced4e6727ed28859864)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputCol,int pNumOutputCol,int use_bias,std::string pName)` | [Linear](#classLinear) 클래스 생성자
`public inline virtual  `[`~Linear`](#classLinear_1a93788848749be1d68d444bd40d8d9bc1)`()` | [Linear](#classLinear) 클래스 소멸자
`public inline int `[`Alloc`](#classLinear_1a83d01a67c02c7d09c34129bd900366e0)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputCol,int pNumOutputCol,int use_bias,std::string pName)` | [Linear(Fully Connected)](#classLinear) Layer 그래프를 동적으로 할당 및 구성하는 메소드

## Members

#### `public inline  `[`Linear`](#classLinear_1aa748db4f994e9ced4e6727ed28859864)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputCol,int pNumOutputCol,int use_bias,std::string pName)` {#classLinear_1aa748db4f994e9ced4e6727ed28859864}

[Linear](#classLinear) 클래스 생성자

[Linear](#classLinear) 클래스의 Alloc 메소드를 호출한다. 
**See also**: linear<DTYPE>::Alloc(Operator<DTYPE> *pInput, int pNumInputCol, int pNumOutputCol, int use_bias, std::string pName)

#### `public inline virtual  `[`~Linear`](#classLinear_1a93788848749be1d68d444bd40d8d9bc1)`()` {#classLinear_1a93788848749be1d68d444bd40d8d9bc1}

[Linear](#classLinear) 클래스 소멸자

단, 동적 할당 받은 Operator들은 NeuralNetwork에서 할당 해제한다.

#### `public inline int `[`Alloc`](#classLinear_1a83d01a67c02c7d09c34129bd900366e0)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputCol,int pNumOutputCol,int use_bias,std::string pName)` {#classLinear_1a83d01a67c02c7d09c34129bd900366e0}

[Linear(Fully Connected)](#classLinear) Layer 그래프를 동적으로 할당 및 구성하는 메소드

Input Operator의 Element에 대해 Weight를 이용해 행렬 곱(Matrix Multiplication)을 수행하고 Bias가 존재할 시 Bias를 합(Column Wise Addition)해 Output Operator로 내보내는 layer를 구성한다. 
#### Parameters
* `pInput` 해당 Layer의 Input에 해당하는 [Operator](#classOperator)

* `pNumInputCol` 해당 Layer의 Input Operator의 Column의 갯수, Input Column에 대한 Dimension 

* `pNumOutputCol` 해당 Layer의 Output Operator의 Column의 갯수, Output Column에 대한 Dimension 

* `use_bias` Bias 사용 유무, 0일 시 사용 안 함, 0이 아닐 시 사용 

* `pName` Module의 이름 

#### Returns
TRUE 

**See also**: MatMul<DTYPE>::MatMul(Operator<DTYPE> *pWeight, Operator<DTYPE> *pInput, std::string pName) AddColWise<DTYPE>::AddColWise(Operator<DTYPE> *pInput, Operator<DTYPE> *pBias, std::string pName) [Module<DTYPE>::AnalyzeGraph(Operator<DTYPE> *pResultOperator)](#classModule_1a7a8ca0c6ddde4bffde9d806ff64ba614)

# class `LongArray` {#classLongArray}

데이터를 저장하고 관리하는 클래스.

학습에 사용 될 Tensor의 맴버변수 중 LongArray를 정의하기 위한 클래스.

실질적으로 Tensor클래스의 데이터를 저장하고 관리하기위한 클래스.

데이터를 초기화하고 CPU와 GPU간 데이터의 이동을 가능하게 한다.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`LongArray`](#classLongArray_1a0e448aa621a5a40584f4db3bee5f27b3)`(unsigned int pCapacity)` | 
`public  `[`LongArray`](#classLongArray_1a0ee04422fc600f9b2d577f6679e131f5)`(unsigned int pTimeSize,unsigned int pCapacityPerTime)` | 입력받은 TimeSize와 Capacity크기의 LongArray를 Alloc하는 생성자.
`public  `[`LongArray`](#classLongArray_1a8ba08c4e2db06cf8077b543f4133c341)`(`[`LongArray`](#classLongArray)` * pLongArray)` | LongArray를 deep copy하는 메소드.
`public virtual  `[`~LongArray`](#classLongArray_1a99b9382548ea2c7eb2864b8fc6834fbf)`()` | LongArray의 소멸자.
`public int `[`GetCapacity`](#classLongArray_1aac066a7a3124bd3faf5790cb1cd3a775)`()` | 
`public int `[`GetTimeSize`](#classLongArray_1a2fdf38f3b567651e109e237a32354479)`()` | 
`public int `[`GetCapacityPerTime`](#classLongArray_1a8a76e2170c3fd845c5d4a4264d818347)`()` | 
`public DTYPE `[`GetElement`](#classLongArray_1a891727ff9e896eece172ca0f5f91c682)`(unsigned int index)` | LongArray의 특정 원소의 값을 반환하는 메소드.
`public DTYPE & `[`operator[]`](#classLongArray_1ac589b2d62373ff5b107869f4d6438773)`(unsigned int index)` | []연산자 Overloading
`public Device `[`GetDevice`](#classLongArray_1a390aa49da495a88a8180bcc829790471)`()` | 
`public int `[`GetDeviceID`](#classLongArray_1a7ea4aa2f04851aa209017b6401f2b35f)`()` | 
`public DTYPE * `[`GetCPULongArray`](#classLongArray_1a488167dabfb50194e2af76e31745d73a)`(unsigned int pTime)` | m_aaHostLongArray중 pTime에 있는 LongArray를 반환하는 메소드.
`public int `[`SetDeviceCPU`](#classLongArray_1a7a6546122e528c6f8934f08eefd1d9bf)`()` | LongArray의 m_Device를 CPU로 바꾸는 메소드.
`public int `[`Save`](#classLongArray_1ac4039a1f176738fc44ef8f8c28aa0d50)`(FILE * fp)` | LongArray의 데이터를 파일에 저장하는 메소드.
`public int `[`Load`](#classLongArray_1a76e8e08d27340622fb9a82603da15bd4)`(FILE * fp)` | 

## Members

#### `public  `[`LongArray`](#classLongArray_1a0e448aa621a5a40584f4db3bee5f27b3)`(unsigned int pCapacity)` {#classLongArray_1a0e448aa621a5a40584f4db3bee5f27b3}

#### `public  `[`LongArray`](#classLongArray_1a0ee04422fc600f9b2d577f6679e131f5)`(unsigned int pTimeSize,unsigned int pCapacityPerTime)` {#classLongArray_1a0ee04422fc600f9b2d577f6679e131f5}

입력받은 TimeSize와 Capacity크기의 LongArray를 Alloc하는 생성자.

#### Parameters
* `pTimeSize` Alloc할 LongArray의 TimeSize 

* `pCapacity` Alloc할 LongArray의 Capacity 

#### Returns
없음. 

**See also**: LongArray<DTYPE>::Alloc(unsigned int pTimeSize, unsigned int pCapacityPerTime)

#### `public  `[`LongArray`](#classLongArray_1a8ba08c4e2db06cf8077b543f4133c341)`(`[`LongArray`](#classLongArray)` * pLongArray)` {#classLongArray_1a8ba08c4e2db06cf8077b543f4133c341}

LongArray를 deep copy하는 메소드.

#### Parameters
* `*pLongArray` deep copy할 대상 [LongArray](#classLongArray)

#### Returns
없음. 

**See also**: LongArray<DTYPE>::Alloc(LongArray *pLongArray)

#### `public virtual  `[`~LongArray`](#classLongArray_1a99b9382548ea2c7eb2864b8fc6834fbf)`()` {#classLongArray_1a99b9382548ea2c7eb2864b8fc6834fbf}

LongArray의 소멸자.

Delete를 사용하여 해당 LongArray를 메모리에서 삭제한다 
#### Returns
없음. 

**See also**: void LongArray<DTYPE>::Delete()

#### `public int `[`GetCapacity`](#classLongArray_1aac066a7a3124bd3faf5790cb1cd3a775)`()` {#classLongArray_1aac066a7a3124bd3faf5790cb1cd3a775}

#### `public int `[`GetTimeSize`](#classLongArray_1a2fdf38f3b567651e109e237a32354479)`()` {#classLongArray_1a2fdf38f3b567651e109e237a32354479}

#### `public int `[`GetCapacityPerTime`](#classLongArray_1a8a76e2170c3fd845c5d4a4264d818347)`()` {#classLongArray_1a8a76e2170c3fd845c5d4a4264d818347}

#### `public DTYPE `[`GetElement`](#classLongArray_1a891727ff9e896eece172ca0f5f91c682)`(unsigned int index)` {#classLongArray_1a891727ff9e896eece172ca0f5f91c682}

LongArray의 특정 원소의 값을 반환하는 메소드.

메모리에 있는 LongArray데이터 중 index번째 있는 원소의 값을 반환한다.

단, m_Device가 GPU이면 바로 값을 꺼내올 수 없기 때문에 CPU로 바꿔 준 후 값을 찾아 반환한다. 
#### Returns
m_aaHostLongArray[index / m_CapacityPerTime][index % m_CapacityPerTime] 

**See also**: [LongArray<DTYPE>::SetDeviceCPU()](#classLongArray_1a7a6546122e528c6f8934f08eefd1d9bf)

#### `public DTYPE & `[`operator[]`](#classLongArray_1ac589b2d62373ff5b107869f4d6438773)`(unsigned int index)` {#classLongArray_1ac589b2d62373ff5b107869f4d6438773}

[]연산자 Overloading

m_aLongArray의 특정 위치에 있는 값을 return할 수 있게 한다.

단, m_Device가 GPU일 시 CPU로 바꿔 준 후 값을 찾아 반환한다.

GetElement와 다르게 주소값을 반환하기 때문에 LongArray의 값을 변경 할 수 있다. 
**See also**: [LongArray<DTYPE>::SetDeviceCPU()](#classLongArray_1a7a6546122e528c6f8934f08eefd1d9bf)

#### `public Device `[`GetDevice`](#classLongArray_1a390aa49da495a88a8180bcc829790471)`()` {#classLongArray_1a390aa49da495a88a8180bcc829790471}

#### `public int `[`GetDeviceID`](#classLongArray_1a7ea4aa2f04851aa209017b6401f2b35f)`()` {#classLongArray_1a7ea4aa2f04851aa209017b6401f2b35f}

#### `public DTYPE * `[`GetCPULongArray`](#classLongArray_1a488167dabfb50194e2af76e31745d73a)`(unsigned int pTime)` {#classLongArray_1a488167dabfb50194e2af76e31745d73a}

m_aaHostLongArray중 pTime에 있는 LongArray를 반환하는 메소드.

m_CapacityOfLongArray를 m_TimeSize로 나눈 LongArray블럭 중 pTime번째의 LongArray블럭을 반환한다.

단, m_Device가 GPU일 시 CPU로 바꿔 준 후 값을 찾아 반환한다. 
#### Returns
m_aaHostLongArray[pTime] 

**See also**: [LongArray<DTYPE>::SetDeviceCPU()](#classLongArray_1a7a6546122e528c6f8934f08eefd1d9bf)

#### `public int `[`SetDeviceCPU`](#classLongArray_1a7a6546122e528c6f8934f08eefd1d9bf)`()` {#classLongArray_1a7a6546122e528c6f8934f08eefd1d9bf}

LongArray의 m_Device를 CPU로 바꾸는 메소드.

m_Device를 CPU로 바꾼다. CUDNN이 있을 경우 GPU 메모리의 값들을 CPU메모리로 복사한다. 
#### Returns
없음. 

**See also**: MemcpyGPU2CPU()

#### `public int `[`Save`](#classLongArray_1ac4039a1f176738fc44ef8f8c28aa0d50)`(FILE * fp)` {#classLongArray_1ac4039a1f176738fc44ef8f8c28aa0d50}

LongArray의 데이터를 파일에 저장하는 메소드.

fwrite함수를 통해 *fileForSave가 가리키는 파일에 LongArray데이터를 쓴다.

단, m_Device가 GPU일 시 CPU로 바꿔 준 후 값을 찾아 반환한다. 
#### Parameters
* `*fileForSave` 데이터를 저장할 file을 가리는 포인터. 

#### Returns
성공 시 TRUE. 

**See also**: [LongArray<DTYPE>::SetDeviceCPU()](#classLongArray_1a7a6546122e528c6f8934f08eefd1d9bf)

#### `public int `[`Load`](#classLongArray_1a76e8e08d27340622fb9a82603da15bd4)`(FILE * fp)` {#classLongArray_1a76e8e08d27340622fb9a82603da15bd4}

# class `LossFunction` {#classLossFunction}

손실 함수를 계산하는 클래스

뉴럴 네트워크의 순전파를 통해 계산된 출력 Tensor와 레이블 값을 비교해 손실 함수를 계산한다.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`LossFunction`](#classLossFunction_1ad16b1ebac0244fcf6f527e541f0b022d)`(std::string pName)` | [LossFunction](#classLossFunction) 클래스 생성자
`public  `[`LossFunction`](#classLossFunction_1a233884fd7efa12ecd4603188ad5dc17b)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | [LossFunction](#classLossFunction) 클래스 생성자
`public virtual  `[`~LossFunction`](#classLossFunction_1a6cae767962d4470457484f25a95dea7d)`()` | [LossFunction](#classLossFunction) 클래스 소멸자
`public virtual int `[`Alloc`](#classLossFunction_1ab391c591298aac6501a3ad2d69e4b2cd)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel)` | LossFunction의 입력과 레이블을 지정하는 메소드
`public virtual void `[`Delete`](#classLossFunction_1af1b7c7d302fdeb47d33a256c76132f7d)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public void `[`SetResult`](#classLossFunction_1a6360d14472a61345a94190e04fb5ca70)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public void `[`SetGradient`](#classLossFunction_1ab18d973fabc53cf0b7b7c611e491be39)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classLossFunction_1a157997c23d30330f3a1787c4e0494906)`() const` | 
`public `[`Tensor`](#classTensor)`< DTYPE > * `[`GetGradient`](#classLossFunction_1a91617741dcdf4d23564fdc76c142c967)`() const` | 
`public `[`Operator`](#classOperator)`< DTYPE > * `[`GetOperator`](#classLossFunction_1aedc2dee597a08ae40d53450a49c60aa5)`() const` | 
`public `[`Tensor`](#classTensor)`< DTYPE > * `[`GetTensor`](#classLossFunction_1a771cbf18cc9665a59ea3d85f05362f60)`() const` | 
`public `[`Operator`](#classOperator)`< DTYPE > * `[`GetLabel`](#classLossFunction_1abebca5aa479892712d16950432a50634)`() const` | 
`public std::string `[`GetName`](#classLossFunction_1a52036df919c793a38c67a86752e245ce)`() const` | 
`public virtual Device `[`GetDevice`](#classLossFunction_1a4d86b502935a77de60b41e4988224ae3)`()` | 
`public virtual int `[`GetDeviceID`](#classLossFunction_1a1498adc80e7109b4f3c1e4c3c5a97e88)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classLossFunction_1a8a564ed18072bb56e6c00c0538d93d2f)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classLossFunction_1a26a756b17dab553a0759f2cc6ffcfa3b)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드
`public DTYPE & `[`operator[]`](#classLossFunction_1a7ab1c185e2a902f8d1baf05b4300d21f)`(unsigned int index)` | [] 연산자 오버로딩
`public virtual void `[`SetDeviceCPU`](#classLossFunction_1aada7f95e69a5fd68aeeb0e92a5856032)`()` | 
`public int `[`ResetResult`](#classLossFunction_1a218be336d4c24afd3ca91ee58ea600e0)`()` | Result 텐서의 ELement를 0으로 초기화하는 메소드
`public int `[`ResetGradient`](#classLossFunction_1a3c75534f1638c50c062ae129e322aee0)`()` | Gradient 텐서의 ELement를 0으로 초기화하는 메소드

## Members

#### `public  `[`LossFunction`](#classLossFunction_1ad16b1ebac0244fcf6f527e541f0b022d)`(std::string pName)` {#classLossFunction_1ad16b1ebac0244fcf6f527e541f0b022d}

[LossFunction](#classLossFunction) 클래스 생성자

LossFunction의 멤버 변수 포인터들을 NULL값으로 초기화하고, 매개변수로 받은 스트링을 m_name에 저장하고, m_Device를 CPU로 초기화한다. 
#### Parameters
* `pName` m_name에 할당할 LossFunction의 이름, 값을 전달하지 않을 시 "NO NAME"으로 초기화 됨 

#### Returns
없음

#### `public  `[`LossFunction`](#classLossFunction_1a233884fd7efa12ecd4603188ad5dc17b)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classLossFunction_1a233884fd7efa12ecd4603188ad5dc17b}

[LossFunction](#classLossFunction) 클래스 생성자

LossFunction의 멤버 변수 포인터들을 NULL값으로 초기화하고, 매개변수로 받은 스트링을 m_name에 저장하고, m_Device를 CPU로 초기화한다.

pOperator와 pLabel을 매개변수로 [LossFunction<DTYPE>::Alloc(Operator<DTYPE> *pOperator, Operator<DTYPE> *pLabel)](#classLossFunction_1ab391c591298aac6501a3ad2d69e4b2cd) 메소드를 호출한다. 
#### Parameters
* `pOperator` Alloc 메소드의 매개변수로 전달할 LossFunction의 입력에 해당하는 [Operator](#classOperator)

* `pLabel` Alloc 메소드의 매개변수로 전달할 LossFunction의 입력에 해당하는 레이블 

* `pName` m_name에 할당할 LossFunction의 이름, 값을 전달하지 않을 시 "NO NAME"으로 초기화 됨 

#### Returns
없음

#### `public virtual  `[`~LossFunction`](#classLossFunction_1a6cae767962d4470457484f25a95dea7d)`()` {#classLossFunction_1a6cae767962d4470457484f25a95dea7d}

[LossFunction](#classLossFunction) 클래스 소멸자

[LossFunction<DTYPE>::Delete()](#classLossFunction_1af1b7c7d302fdeb47d33a256c76132f7d) 메소드를 호출하고 클래스를 소멸시킨다. 
#### Returns
없음

#### `public virtual int `[`Alloc`](#classLossFunction_1ab391c591298aac6501a3ad2d69e4b2cd)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel)` {#classLossFunction_1ab391c591298aac6501a3ad2d69e4b2cd}

LossFunction의 입력과 레이블을 지정하는 메소드

매개변수로 전달받은 Operator와 Operator의 Result 포인터 값과 레이블 값을 저장한다. 
#### Parameters
* `pOperator` LossFunction의 입력이 되는 [Operator](#classOperator)

* `plabel` LossFunction의 입력이 되는 레이블 

#### Returns
TRUE

#### `public virtual void `[`Delete`](#classLossFunction_1af1b7c7d302fdeb47d33a256c76132f7d)`()` {#classLossFunction_1af1b7c7d302fdeb47d33a256c76132f7d}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public void `[`SetResult`](#classLossFunction_1a6360d14472a61345a94190e04fb5ca70)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classLossFunction_1a6360d14472a61345a94190e04fb5ca70}

#### `public void `[`SetGradient`](#classLossFunction_1ab18d973fabc53cf0b7b7c611e491be39)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classLossFunction_1ab18d973fabc53cf0b7b7c611e491be39}

#### `public `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classLossFunction_1a157997c23d30330f3a1787c4e0494906)`() const` {#classLossFunction_1a157997c23d30330f3a1787c4e0494906}

#### `public `[`Tensor`](#classTensor)`< DTYPE > * `[`GetGradient`](#classLossFunction_1a91617741dcdf4d23564fdc76c142c967)`() const` {#classLossFunction_1a91617741dcdf4d23564fdc76c142c967}

#### `public `[`Operator`](#classOperator)`< DTYPE > * `[`GetOperator`](#classLossFunction_1aedc2dee597a08ae40d53450a49c60aa5)`() const` {#classLossFunction_1aedc2dee597a08ae40d53450a49c60aa5}

#### `public `[`Tensor`](#classTensor)`< DTYPE > * `[`GetTensor`](#classLossFunction_1a771cbf18cc9665a59ea3d85f05362f60)`() const` {#classLossFunction_1a771cbf18cc9665a59ea3d85f05362f60}

#### `public `[`Operator`](#classOperator)`< DTYPE > * `[`GetLabel`](#classLossFunction_1abebca5aa479892712d16950432a50634)`() const` {#classLossFunction_1abebca5aa479892712d16950432a50634}

#### `public std::string `[`GetName`](#classLossFunction_1a52036df919c793a38c67a86752e245ce)`() const` {#classLossFunction_1a52036df919c793a38c67a86752e245ce}

#### `public virtual Device `[`GetDevice`](#classLossFunction_1a4d86b502935a77de60b41e4988224ae3)`()` {#classLossFunction_1a4d86b502935a77de60b41e4988224ae3}

#### `public virtual int `[`GetDeviceID`](#classLossFunction_1a1498adc80e7109b4f3c1e4c3c5a97e88)`()` {#classLossFunction_1a1498adc80e7109b4f3c1e4c3c5a97e88}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classLossFunction_1a8a564ed18072bb56e6c00c0538d93d2f)`(int pTime)` {#classLossFunction_1a8a564ed18072bb56e6c00c0538d93d2f}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classLossFunction_1a26a756b17dab553a0759f2cc6ffcfa3b)`(int pTime)` {#classLossFunction_1a26a756b17dab553a0759f2cc6ffcfa3b}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public DTYPE & `[`operator[]`](#classLossFunction_1a7ab1c185e2a902f8d1baf05b4300d21f)`(unsigned int index)` {#classLossFunction_1a7ab1c185e2a902f8d1baf05b4300d21f}

[] 연산자 오버로딩

매개변수로 전달받은 index 값 매개변수로 전달하여 Result 텐서에서 []연산자 메소드를 호출한다. 
#### Parameters
* `index` Tensor의 [] 연산자 메소드에 매개변수로 전달할 인덱스 값 

#### Returns
(*m_aResult)[index] 

**See also**: Tensor<DTYPE>::operator[](unsigned int index)

#### `public virtual void `[`SetDeviceCPU`](#classLossFunction_1aada7f95e69a5fd68aeeb0e92a5856032)`()` {#classLossFunction_1aada7f95e69a5fd68aeeb0e92a5856032}

#### `public int `[`ResetResult`](#classLossFunction_1a218be336d4c24afd3ca91ee58ea600e0)`()` {#classLossFunction_1a218be336d4c24afd3ca91ee58ea600e0}

Result 텐서의 ELement를 0으로 초기화하는 메소드

Result 텐서의 Device 멤버 변수가 CPU인 경우 CPU 메모리에서 초기화하고, CPU인 경우 GPU 메모리에서 초기화한다. 
#### Returns
Result 텐서의 Device 멤버 변수가 Invalid한 값을 가지고 있는 경우 FALSE를 그 외의 경우 TRUE를 반환한다.

#### `public int `[`ResetGradient`](#classLossFunction_1a3c75534f1638c50c062ae129e322aee0)`()` {#classLossFunction_1a3c75534f1638c50c062ae129e322aee0}

Gradient 텐서의 ELement를 0으로 초기화하는 메소드

Gradient 텐서의 Device 멤버 변수가 CPU인 경우 CPU 메모리에서 초기화하고, CPU인 경우 GPU 메모리에서 초기화한다. 
#### Returns
Gradient 텐서의 Device 멤버 변수가 Invalid한 값을 가지고 있는 경우 FALSE를 그 외의 경우 TRUE를 반환한다.

# class `LRelu` {#classLRelu}

```
class LRelu
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`LRelu`](#classLRelu_1a890bd4b4423289342bf76cd8dec4ded2)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float negativeSlope,int pLoadflag)` | LRelu의 생성자.
`public inline  `[`LRelu`](#classLRelu_1a4703113933cac094b879ba9dedb4bc36)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float negativeSlope,std::string pName,int pLoadflag)` | LRelu의 생성자.
`public inline  `[`~LRelu`](#classLRelu_1af07aac4e93018681985799014b5c19b4)`()` | LRelu의 소멸자.
`public inline int `[`Alloc`](#classLRelu_1af51d676679f90ed10690e0920e03c459)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float negativeSlope)` | 파라미터로 받은 pinput으로부터 맴버 변수들을 초기화 한다.
`public inline void `[`Delete`](#classLRelu_1a61814364f8bfe1c0297e0ebb1727aef8)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classLRelu_1a9c7970df9d473b47301d42ffe3838c1b)`(int pTime)` | LRelu의 ForwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classLRelu_1a8322f90cae9c6c0c704fc8ad87a3c2e5)`(int pTime)` | LRelu의 BackPropagate매소드.

## Members

#### `public inline  `[`LRelu`](#classLRelu_1a890bd4b4423289342bf76cd8dec4ded2)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float negativeSlope,int pLoadflag)` {#classLRelu_1a890bd4b4423289342bf76cd8dec4ded2}

LRelu의 생성자.

파라미터로 받은 pInput, negativeSlope으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator)

* `negativeSlope` 입력값이 음수일 경우 사용하는 기울기 int [Alloc(Operator<DTYPE> *pInput, float negativeSlope)](#classLRelu_1af51d676679f90ed10690e0920e03c459)

#### `public inline  `[`LRelu`](#classLRelu_1a4703113933cac094b879ba9dedb4bc36)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float negativeSlope,std::string pName,int pLoadflag)` {#classLRelu_1a4703113933cac094b879ba9dedb4bc36}

LRelu의 생성자.

파라미터로 받은 pInput, negativeSlope으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator)

* `negativeSlope` 입력값이 음수일 경우 사용하는 기울기 

* `pName` Operator에 사용자가 부여한 이름. int [Alloc(Operator<DTYPE> *pInput, float negativeSlope)](#classLRelu_1af51d676679f90ed10690e0920e03c459)

#### `public inline  `[`~LRelu`](#classLRelu_1af07aac4e93018681985799014b5c19b4)`()` {#classLRelu_1af07aac4e93018681985799014b5c19b4}

LRelu의 소멸자.

**See also**: void Delete()

#### `public inline int `[`Alloc`](#classLRelu_1af51d676679f90ed10690e0920e03c459)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,float negativeSlope)` {#classLRelu_1af51d676679f90ed10690e0920e03c459}

파라미터로 받은 pinput으로부터 맴버 변수들을 초기화 한다.

Result와 Gradient를 저장하기 위해 pInput의 Shape과 같은 dim을 갖는 Tensor를 생성한다.

negativeSlope은 m_negativeSlope에 저장한다. 
#### Parameters
* `pInput` 생성할 Tensor의 Shape정보를 가진 [Operator](#classOperator)

* `negativeSlope` 입력값이 음수일 경우 사용하는 기울기 

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classLRelu_1a61814364f8bfe1c0297e0ebb1727aef8)`()` {#classLRelu_1a61814364f8bfe1c0297e0ebb1727aef8}

#### `public inline virtual int `[`ForwardPropagate`](#classLRelu_1a9c7970df9d473b47301d42ffe3838c1b)`(int pTime)` {#classLRelu_1a9c7970df9d473b47301d42ffe3838c1b}

LRelu의 ForwardPropagate 매소드.

input의 Tensor값들 중 0.f이상의 값은 그대로 result에 저장하고,

0.f미만의 값은 m_negativeSlope을 곱한 후 저장한다. 
#### Parameters
* `pTime` pInput의 m_timesize값, default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classLRelu_1a8322f90cae9c6c0c704fc8ad87a3c2e5)`(int pTime)` {#classLRelu_1a8322f90cae9c6c0c704fc8ad87a3c2e5}

LRelu의 BackPropagate매소드.

result값이 0보다 클 경우 input_delta에 더하고,

0보다 작을 경우 input_delta에 m_negativeSlope을 곱한 후 더한다. 
#### Parameters
* `pTime` pInput의 m_timesize값, default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `MatMul` {#classMatMul}

```
class MatMul
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`MatMul`](#classMatMul_1afd77f3abc4bc600c045b74a634952ae8)`(`[`Operator`](#classOperator)`< DTYPE > * pWeight,`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` | MatMul의 생성자.
`public inline virtual  `[`~MatMul`](#classMatMul_1a3c436539092d145a8bd89a91285094f5)`()` | MatMul의 소멸자
`public inline int `[`Alloc`](#classMatMul_1aad34ca11b1ed37b103381f8ef204bef2)`(`[`Operator`](#classOperator)`< DTYPE > * pWeight,`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 파라미터로 받은 pWeight, pInput으로 맴버 변수들을 초기화 한다.
`public inline void `[`Delete`](#classMatMul_1a45113c61efe47376cb0751d4a1106568)`()` | GPU에 할당했던 메모리를 해제하고 각 포인터들을 NULL로 초기화한다.
`public inline virtual int `[`ForwardPropagate`](#classMatMul_1a44c66bf3826370257a718bf974a2af68)`(int pTime)` | MatMul의 ForwardPropagate매소드.
`public inline virtual int `[`BackPropagate`](#classMatMul_1aebaeb2eee8735a3bdb1c7f2bc64a96a8)`(int pTime)` | MatMul의 BackPropagate 매소드.

## Members

#### `public inline  `[`MatMul`](#classMatMul_1afd77f3abc4bc600c045b74a634952ae8)`(`[`Operator`](#classOperator)`< DTYPE > * pWeight,`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` {#classMatMul_1afd77f3abc4bc600c045b74a634952ae8}

MatMul의 생성자.

파라미터로 받은 pWeight와 pInput으로 Alloc한다. 
#### Parameters
* `pWeight` MatMul할 weight. 

* `pInput` Matmul할 input [Operator](#classOperator). 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pWeight, Operator<DTYPE> *pInput)](#classMatMul_1aad34ca11b1ed37b103381f8ef204bef2)

#### `public inline virtual  `[`~MatMul`](#classMatMul_1a3c436539092d145a8bd89a91285094f5)`()` {#classMatMul_1a3c436539092d145a8bd89a91285094f5}

MatMul의 소멸자

Delete매소드를 사용해 GPU에 할당했던 값들을 해제한다. void [Delete()](#classMatMul_1a45113c61efe47376cb0751d4a1106568)

#### `public inline int `[`Alloc`](#classMatMul_1aad34ca11b1ed37b103381f8ef204bef2)`(`[`Operator`](#classOperator)`< DTYPE > * pWeight,`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classMatMul_1aad34ca11b1ed37b103381f8ef204bef2}

파라미터로 받은 pWeight, pInput으로 맴버 변수들을 초기화 한다.

timesize, batchsize, channelsize, row_size는 pInput의 Shape과 같게, colsize는 pWeight와 같게 초기화한다.

input x weight을 하기 때문에 rowsize는 pInput의 Shape을, colsize는 pWeight의 Shape을 받는다.

Result와 Delta를 저장하기 위해 input의 rowsize, weight의 colsize를 갖는 Tensor를 생성한다. 
#### Parameters
* `pWeight` MatMul할 weight. 

* `pInput` Matmul할 input [Operator](#classOperator). 

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classMatMul_1a45113c61efe47376cb0751d4a1106568)`()` {#classMatMul_1a45113c61efe47376cb0751d4a1106568}

GPU에 할당했던 메모리를 해제하고 각 포인터들을 NULL로 초기화한다.

inputTensorDesc, outputTensorDesc,deltaDesc, inputDeltaDesc, convDesc, filterDesc,filterDeltaDesc들을 삭제하고 NULL로 초기화한다.

m_devWorkSpace, m_dataDevWorkSpace, m_filterDevWorkSpace들이 가리키는 메모리를 해제한다.

#### `public inline virtual int `[`ForwardPropagate`](#classMatMul_1a44c66bf3826370257a718bf974a2af68)`(int pTime)` {#classMatMul_1a44c66bf3826370257a718bf974a2af68}

MatMul의 ForwardPropagate매소드.

weight의 각 row의 값들과 input의 Colunm의 각 값들을 곱하여 result에 더한다.

[2 x 3] x [3 x 1]일때 3이 hiddensize 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classMatMul_1aebaeb2eee8735a3bdb1c7f2bc64a96a8)`(int pTime)` {#classMatMul_1aebaeb2eee8735a3bdb1c7f2bc64a96a8}

MatMul의 BackPropagate 매소드.

input_delta에 weight * this_delta값을 더해주고,

weight_gradient에는 input * this_delta값을 더해준다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `Maxpooling2D` {#classMaxpooling2D}

```
class Maxpooling2D
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Maxpooling2D`](#classMaxpooling2D_1a884f8b84ac999382d21ee08b3e040d17)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,std::string pName,int pLoadflag)` | Maxpooling2D의 생성자
`public inline  `[`Maxpooling2D`](#classMaxpooling2D_1a9ab7589f765b6e90625e0b7ff28120e9)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,int padding,std::string pName,int pLoadflag)` | Maxpooling2D의 생성자
`public inline  `[`~Maxpooling2D`](#classMaxpooling2D_1a90ae8c88a3734949c60293a1c5f1a166)`()` | Maxpooling2D의 소멸자
`public inline int `[`Alloc`](#classMaxpooling2D_1adcff3829a9ac557ba6e1e5852696d8d8)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int strideRow,int strideCol,int maskRow,int maskCol,int padding1,int padding2)` | 파라미터로 받은 변수로부터 맴버 변수들을 초기화 한다.
`public inline void `[`Delete`](#classMaxpooling2D_1a28058438060f1727637d4ad12b1b3fb7)`()` | Delete 메소드
`public inline virtual int `[`ForwardPropagate`](#classMaxpooling2D_1ac70d30d579150b568f3c24e9a35ce81f)`(int pTime)` | Maxpooling2D의 ForwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classMaxpooling2D_1ad9fbf7ae3ead0362607d12116c0e8bfe)`(int pTime)` | Maxpooling2D의 BackPropagate 매소드.

## Members

#### `public inline  `[`Maxpooling2D`](#classMaxpooling2D_1a884f8b84ac999382d21ee08b3e040d17)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,std::string pName,int pLoadflag)` {#classMaxpooling2D_1a884f8b84ac999382d21ee08b3e040d17}

Maxpooling2D의 생성자

파라미터로 받은 pInput, strideRow, strideCol, maskRow, maskCol으로 Alloc한다. 
#### Parameters
* `pInput` Maxpooling2D할 대상 [Operator](#classOperator). 

* `maskRow` Filter의 Row size 

* `maskCol` Filter의 Colunm size 

* `strideRow` Row stirde값 

* `strideCol` Colunm stride값 

* `pName` 사용자가 부여한 Operator이름

#### `public inline  `[`Maxpooling2D`](#classMaxpooling2D_1a9ab7589f765b6e90625e0b7ff28120e9)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int maskRow,int maskCol,int strideRow,int strideCol,int padding,std::string pName,int pLoadflag)` {#classMaxpooling2D_1a9ab7589f765b6e90625e0b7ff28120e9}

Maxpooling2D의 생성자

파라미터로 받은 pInput, strideRow, strideCol, maskRow, maskCol으로 Alloc한다. 
#### Parameters
* `pInput` Maxpooling2D할 대상 [Operator](#classOperator). 

* `maskRow` Filter의 Row size 

* `maskCol` Filter의 Colunm size 

* `strideRow` Row stirde값 

* `strideCol` Colunm stride값 

* `padding` padding size 

* `pName` 사용자가 부여한 Operator이름

#### `public inline  `[`~Maxpooling2D`](#classMaxpooling2D_1a90ae8c88a3734949c60293a1c5f1a166)`()` {#classMaxpooling2D_1a90ae8c88a3734949c60293a1c5f1a166}

Maxpooling2D의 소멸자

#### `public inline int `[`Alloc`](#classMaxpooling2D_1adcff3829a9ac557ba6e1e5852696d8d8)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int strideRow,int strideCol,int maskRow,int maskCol,int padding1,int padding2)` {#classMaxpooling2D_1adcff3829a9ac557ba6e1e5852696d8d8}

파라미터로 받은 변수로부터 맴버 변수들을 초기화 한다.

Result와 Gradient를 저장하기 위해 pInput의 Shape과 같은 dim을 갖는 Tensor를 생성한다.

m_stride, m_mask, m_padding값들을 초기화 하고 rowsize, colsize를 결정한다. 
#### Parameters
* `pInput` 생성 할 Tensor의 Shape정보를 가진 [Operator](#classOperator). 

* `strideRow` Row stirde값. 

* `strideCol` Colunm stride값. 

* `maskRow` Filter의 Row size. 

* `maskCol` Filter의 Colunm size. 

* `padding1` row_padding 값. 

* `padding2` col_padding 값. 

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classMaxpooling2D_1a28058438060f1727637d4ad12b1b3fb7)`()` {#classMaxpooling2D_1a28058438060f1727637d4ad12b1b3fb7}

Delete 메소드

cudnnDescriptor들을 GPU메모리에서 해제하고 포인터를 null로 초기화한다.

#### `public inline virtual int `[`ForwardPropagate`](#classMaxpooling2D_1ac70d30d579150b568f3c24e9a35ce81f)`(int pTime)` {#classMaxpooling2D_1ac70d30d579150b568f3c24e9a35ce81f}

Maxpooling2D의 ForwardPropagate 매소드.

Filter(temprow * tempcol)의 범위 중 가장 큰 값을 result에 저장하고, index는 indexOfMaxInput에 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classMaxpooling2D_1ad9fbf7ae3ead0362607d12116c0e8bfe)`(int pTime)` {#classMaxpooling2D_1ad9fbf7ae3ead0362607d12116c0e8bfe}

Maxpooling2D의 BackPropagate 매소드.

계산한 delta값을 input_delta에 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `Module` {#classModule}

```
class Module
  : public Operator< DTYPE >
```  

구성해 모듈화하는 클래스

Operator들을 뉴럴 네트워크의 서브 그래프로 구성해 단일 Operator로서 할 수 없는 기능들을 수행하게 한다

Module은 하나의 Operator처럼 뉴럴 네트워크 안에서 작동한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`Module`](#classModule_1ab8bf888e5ed0b51674053f4f3012b777)`(std::string pName)` | [Module](#classModule) 클래스 생성자
`public virtual  `[`~Module`](#classModule_1a45761c15cc79e282993449230e534884)`()` | [Module](#classModule) 클래스 소멸자
`public virtual int `[`SetInput`](#classModule_1a99353f5e7c249dcc0ce475c46998f962)`(int pNumOfInput,...)` | 
`public virtual `[`Operator`](#classOperator)`< DTYPE > * `[`SetInput`](#classModule_1a4cf759005542d3d8b0f4d69636fa03c7)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 
`public virtual `[`Operator`](#classOperator)`< DTYPE > * `[`SetParameter`](#classModule_1a6ecb67a59936e89ad89eced365697213)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` | 
`public virtual `[`Operator`](#classOperator)`< DTYPE > * `[`SetExecutableOperater`](#classModule_1a823107d07bf30b0e83c9f08ec96db88c)`(`[`Operator`](#classOperator)`< DTYPE > * pExecutableOperater)` | 
`public int `[`IsInput`](#classModule_1ae04c0f219dfa387c73a460a8ed5fe523)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` | 해당 Operator가 Module의 Input인지 확인하는 메소드
`public int `[`IsValid`](#classModule_1a8e3d501cd75cb65608108d0eef9c6c7c)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` | 해당 Operator의 Output Operator들이 모듈 그래프에 중복으로 포함되는 지 확인하는 메소드
`public `[`Operator`](#classOperator)`< DTYPE > * `[`AnalyzeGraph`](#classModule_1a7a8ca0c6ddde4bffde9d806ff64ba614)`(`[`Operator`](#classOperator)`< DTYPE > * pResultOperator)` | 학습 가능한 형태로 모듈 그래프를 구성해주는 메소드
`public int `[`FeedInputTensor`](#classModule_1aab82adebc4238c1ebe731a47c975ba92)`(int pNumOfInput,...)` | 신경망에 Input 리스트를 추가하는 메소드
`public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetExcutableOperatorContainer`](#classModule_1aa32d7ec18eb178a4ad00009bc71b98fa)`()` | 
`public int `[`GetNumOfExcutableOperator`](#classModule_1ad47616271ad57492c19e937f4d9bb539)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classModule_1acbe814aa648ece32c4f6ea5f4421bdf0)`() const` | 
`public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetResultContainer`](#classModule_1aad4a03f8d46feda2213d5285ce00a1de)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetGradient`](#classModule_1a599a20137470952839e61b0860dc7109)`() const` | 
`public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetGradientContainer`](#classModule_1afdcf83fc8ccbcf6a5f77cd95799ec4d3)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetDelta`](#classModule_1a14084c16219f9e53908427229702a3d8)`() const` | 
`public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetDeltaContainer`](#classModule_1ae9735791ddce3b989262c825e2078f70)`()` | 
`public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetParameterContainer`](#classModule_1a6aff064f12e13edc59a8b6c12d6d7af8)`()` | 
`public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetParameter`](#classModule_1a5bd36cbe8d7bb82ba7dc93a84a37948b)`()` | 
`public virtual int `[`SetIsTensorholder`](#classModule_1ac1224ac02d8c0d36f739a17232bb64da)`(int pIsParameter)` | 
`public virtual int `[`SetIsTrainable`](#classModule_1a32a996291f7465b8596ebe61f18f682a)`(int pIsTrainable)` | 
`public virtual int `[`SetModeTrain`](#classModule_1a746ba9e663c2b56854c26a53cb5bd554)`()` | 
`public virtual int `[`SetModeAccumulate`](#classModule_1a93d4a4c2cc70fc27f1c7e9d98451fa0e)`()` | 
`public virtual int `[`SetModeInference`](#classModule_1a5fadf1f06188eeaa07f59f23b094e098)`()` | 
`public virtual int `[`ForwardPropagate`](#classModule_1a1bea4bd0b2831e0c21696998393cc263)`(int pTime)` | 모듈 그래프의 순전파를 수행하는 메소드
`public virtual int `[`BackPropagate`](#classModule_1a561a89214a6252632cbc507ef6e35b58)`(int pTime)` | 모듈 그래프의 역전파를 수행하는 메소드
`public virtual int `[`ResetResult`](#classModule_1a3f82395e6c6063bc8d70cf1e0fe48260)`()` | 연산에 참여하는 Operator들의 Result Container를 초기화시킨다.
`public virtual int `[`ResetGradient`](#classModule_1a498ecc0aebdc2e1d47d15ed1d3a34190)`()` | 연산에 참여하는 Operator들의 Gradient Container를 초기화시킨다.
`public virtual void `[`PrintInformation`](#classModule_1a1fe0649b5922714869c9727e6e48af86)`(int level)` | 
`public virtual void `[`SetDeviceCPU`](#classModule_1a002890bc0726abfe5807ed7fdc2b7009)`()` | 모듈 그래프 학습에 사용되는 장치를 CPU로 전환하는 메소드
`public void `[`SetDeviceCPUOnModule`](#classModule_1afebb7db4c54e6405cb2a9fabf7ec4014)`()` | 
`public virtual int `[`Save`](#classModule_1ab932898db0934f08b11e58c527a21d3e)`(char * nameOfFile)` | 
`public virtual int `[`Load`](#classModule_1a533bb3a09eaaf78f468a8714f5897dd4)`(char * nameOfFile)` | 
`public virtual int `[`Save`](#classModule_1a8d201e11894e203c26443830059247f4)`(FILE * fp)` | 
`public virtual int `[`Load`](#classModule_1ae72b4ff6dca516608f7e86cedc707b97)`(FILE * fp)` | 
`public virtual int `[`SaveComponents`](#classModule_1a4e7ab899a27e1f29c16d12e12ce51c5f)`(char * nameOfDir)` | 
`public virtual int `[`LoadComponents`](#classModule_1af089e75acd169b00241e3b33b9406da5)`(char * nameOfDir)` | 

## Members

#### `public  `[`Module`](#classModule_1ab8bf888e5ed0b51674053f4f3012b777)`(std::string pName)` {#classModule_1ab8bf888e5ed0b51674053f4f3012b777}

[Module](#classModule) 클래스 생성자

각 멤버 변수들을 초기화하고 [Module](#classModule) 클래스를 생성한다.

각 포인터들을 NULL 값으로, 각 정수 타입 변수들은 0으로 초기화하고 Module<DTYPE>::Alloc() 메소드를 호출한다. 
**See also**: Module<DTYPE>::Alloc() 

#### Returns
없음

#### `public virtual  `[`~Module`](#classModule_1a45761c15cc79e282993449230e534884)`()` {#classModule_1a45761c15cc79e282993449230e534884}

[Module](#classModule) 클래스 소멸자

동적으로 할당 받은 [Module](#classModule) 클래스의 멤버 변수들을 할당 해제하고 클래스를 소멸시킨다. 
#### Returns
없음 

**See also**: Module<DTYPE>::Delete()

#### `public virtual int `[`SetInput`](#classModule_1a99353f5e7c249dcc0ce475c46998f962)`(int pNumOfInput,...)` {#classModule_1a99353f5e7c249dcc0ce475c46998f962}

#### `public virtual `[`Operator`](#classOperator)`< DTYPE > * `[`SetInput`](#classModule_1a4cf759005542d3d8b0f4d69636fa03c7)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classModule_1a4cf759005542d3d8b0f4d69636fa03c7}

#### `public virtual `[`Operator`](#classOperator)`< DTYPE > * `[`SetParameter`](#classModule_1a6ecb67a59936e89ad89eced365697213)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` {#classModule_1a6ecb67a59936e89ad89eced365697213}

#### `public virtual `[`Operator`](#classOperator)`< DTYPE > * `[`SetExecutableOperater`](#classModule_1a823107d07bf30b0e83c9f08ec96db88c)`(`[`Operator`](#classOperator)`< DTYPE > * pExecutableOperater)` {#classModule_1a823107d07bf30b0e83c9f08ec96db88c}

#### `public int `[`IsInput`](#classModule_1ae04c0f219dfa387c73a460a8ed5fe523)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` {#classModule_1ae04c0f219dfa387c73a460a8ed5fe523}

해당 Operator가 Module의 Input인지 확인하는 메소드

매개변수로 받은 Operator가 Module의 Input Container에 포함되어 있는 지 확인한다. 
#### Parameters
* `pOperator` Input 여부를 확인하고자 하는 [Operator](#classOperator)

#### Returns
Input container에 포함되어 있는 경우 TRUE, 포함되어 있지 않는 경우 FALSE를 반환한다.

#### `public int `[`IsValid`](#classModule_1a8e3d501cd75cb65608108d0eef9c6c7c)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` {#classModule_1a8e3d501cd75cb65608108d0eef9c6c7c}

해당 Operator의 Output Operator들이 모듈 그래프에 중복으로 포함되는 지 확인하는 메소드

해당 Operator의 Output container 멤버 변수에 담겨 있는 Operator들이 Module의 Excutable [Operator](#classOperator) container에 중복되어 포함되어 있는 지 여부를 확인한다. 
#### Parameters
* `pOperator` Output [Container](#classContainer) 멤버 변수가 Excutable [Operator](#classOperator) Container에 포함되어 있는 지 확인하고자 하는 [Operator](#classOperator)

#### Returns
해당 Operator의 Output [Container](#classContainer) 멤버 변수가 Excutable [Operator](#classOperator) Container에 중복되어 포함되어 있으면 TRUE를 아니면 FALSE를 반환한다.

#### `public `[`Operator`](#classOperator)`< DTYPE > * `[`AnalyzeGraph`](#classModule_1a7a8ca0c6ddde4bffde9d806ff64ba614)`(`[`Operator`](#classOperator)`< DTYPE > * pResultOperator)` {#classModule_1a7a8ca0c6ddde4bffde9d806ff64ba614}

학습 가능한 형태로 모듈 그래프를 구성해주는 메소드

모듈의 Output에 해당하는 Operator를 매개변수로 받아 너비 우선 탐색으로 모듈 그래프를 구성한다.

매개변수로 받은 모듈의 Output에 해당하는 Operator를 시작으로 모듈의 Input에 해당하는 Operator까지 역순으로, Operator가 Input [Tensor](#classTensor) 및 학습 파라미터인 경우 [Module](#classModule) 클래스의 Input [Container](#classContainer) 멤버 변수에 추가하고 나머지 경우에는 [Module](#classModule) 클래스의 Excutable [Operator](#classOperator)[Container](#classContainer) 멤버 변수에 추가한다.

[NeuralNetwork](#classNeuralNetwork) 클래스의 Excutable [Operator](#classOperator)[Container](#classContainer) 멤버 변수에 Operator들이 모두 추가되면 Container를 역순으로 변경한다.

[Operator](#classOperator) 탐색 순서는 너비 우선 탐색을 따르며, 매개변수로 받은 Output Operator부터 해당 Operator의 Input [Operator](#classOperator) 리스트를 너비 우선 탐색 방식을 이용해 순서대로 진행한다.

각 Operator들은 [Module<DTYPE>::IsValid(Operator<DTYPE> *pOperator)](#classModule_1a8e3d501cd75cb65608108d0eef9c6c7c) 메소드를 이용하여 모듈 그래프 안에서의 중복 여부를 확인하며 중복되는 경우 그래프에 추가하지 않는다. 
#### Parameters
* `pResultOperator` 그래프를 구성하고자 하는 신경망의 Output에 해당하는 [Operator](#classOperator)

#### Returns
매개변수로 받은 그래프를 구성하고자 하는 신경망의 Output에 해당하는 [Operator](#classOperator)

#### `public int `[`FeedInputTensor`](#classModule_1aab82adebc4238c1ebe731a47c975ba92)`(int pNumOfInput,...)` {#classModule_1aab82adebc4238c1ebe731a47c975ba92}

신경망에 Input 리스트를 추가하는 메소드

매개변수로 받은 Tensor들을 순서대로 NeuralNetwork의 Input Container에 담겨 있는 Operator들의 Result로 설정한다. 
#### Parameters
* `pNumOfInput` Input Container에 추가하고 싶은 Tensor들의 개수 

* `...` Input Container에 추가하고 싶은 Tensor들의 리스트 

#### Returns
TRUE 

**See also**: Operator<DTYPE>::SetResult(Tensor<DTYPE> *pTensor)

#### `public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetExcutableOperatorContainer`](#classModule_1aa32d7ec18eb178a4ad00009bc71b98fa)`()` {#classModule_1aa32d7ec18eb178a4ad00009bc71b98fa}

#### `public int `[`GetNumOfExcutableOperator`](#classModule_1ad47616271ad57492c19e937f4d9bb539)`()` {#classModule_1ad47616271ad57492c19e937f4d9bb539}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classModule_1acbe814aa648ece32c4f6ea5f4421bdf0)`() const` {#classModule_1acbe814aa648ece32c4f6ea5f4421bdf0}

#### `public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetResultContainer`](#classModule_1aad4a03f8d46feda2213d5285ce00a1de)`()` {#classModule_1aad4a03f8d46feda2213d5285ce00a1de}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetGradient`](#classModule_1a599a20137470952839e61b0860dc7109)`() const` {#classModule_1a599a20137470952839e61b0860dc7109}

#### `public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetGradientContainer`](#classModule_1afdcf83fc8ccbcf6a5f77cd95799ec4d3)`()` {#classModule_1afdcf83fc8ccbcf6a5f77cd95799ec4d3}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetDelta`](#classModule_1a14084c16219f9e53908427229702a3d8)`() const` {#classModule_1a14084c16219f9e53908427229702a3d8}

#### `public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetDeltaContainer`](#classModule_1ae9735791ddce3b989262c825e2078f70)`()` {#classModule_1ae9735791ddce3b989262c825e2078f70}

#### `public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetParameterContainer`](#classModule_1a6aff064f12e13edc59a8b6c12d6d7af8)`()` {#classModule_1a6aff064f12e13edc59a8b6c12d6d7af8}

#### `public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetParameter`](#classModule_1a5bd36cbe8d7bb82ba7dc93a84a37948b)`()` {#classModule_1a5bd36cbe8d7bb82ba7dc93a84a37948b}

#### `public virtual int `[`SetIsTensorholder`](#classModule_1ac1224ac02d8c0d36f739a17232bb64da)`(int pIsParameter)` {#classModule_1ac1224ac02d8c0d36f739a17232bb64da}

#### `public virtual int `[`SetIsTrainable`](#classModule_1a32a996291f7465b8596ebe61f18f682a)`(int pIsTrainable)` {#classModule_1a32a996291f7465b8596ebe61f18f682a}

#### `public virtual int `[`SetModeTrain`](#classModule_1a746ba9e663c2b56854c26a53cb5bd554)`()` {#classModule_1a746ba9e663c2b56854c26a53cb5bd554}

#### `public virtual int `[`SetModeAccumulate`](#classModule_1a93d4a4c2cc70fc27f1c7e9d98451fa0e)`()` {#classModule_1a93d4a4c2cc70fc27f1c7e9d98451fa0e}

#### `public virtual int `[`SetModeInference`](#classModule_1a5fadf1f06188eeaa07f59f23b094e098)`()` {#classModule_1a5fadf1f06188eeaa07f59f23b094e098}

#### `public virtual int `[`ForwardPropagate`](#classModule_1a1bea4bd0b2831e0c21696998393cc263)`(int pTime)` {#classModule_1a1bea4bd0b2831e0c21696998393cc263}

모듈 그래프의 순전파를 수행하는 메소드

Excutable [Operator](#classOperator) Container의 각 Operator들에서 Operator<DTYPE>::ForwardPropagate(int pTime) 메소드를 순서대로 호출한다. 
#### Parameters
* `pTime` 각 ForwardPropagate 메소드에 전달할 Time의 인덱스 

#### Returns
TRUE

#### `public virtual int `[`BackPropagate`](#classModule_1a561a89214a6252632cbc507ef6e35b58)`(int pTime)` {#classModule_1a561a89214a6252632cbc507ef6e35b58}

모듈 그래프의 역전파를 수행하는 메소드

역순으로 Excutable [Operator](#classOperator) Container의 각 Operator들에서 Operator<DTYPE>::ForwardPropagate(int pTime) 메소드를 호출한다. 
#### Parameters
* `pTime` 각 ForwardPropagate 메소드에 전달할 Time의 인덱스 

#### Returns
TRUE

#### `public virtual int `[`ResetResult`](#classModule_1a3f82395e6c6063bc8d70cf1e0fe48260)`()` {#classModule_1a3f82395e6c6063bc8d70cf1e0fe48260}

연산에 참여하는 Operator들의 Result Container를 초기화시킨다.

Excutable [Operator](#classOperator) Container에 포함되어 있는 각 Operator들에서 Operator<DTYPE>::ResetResult() 메소드를 호출한다. 
#### Returns
TRUE

#### `public virtual int `[`ResetGradient`](#classModule_1a498ecc0aebdc2e1d47d15ed1d3a34190)`()` {#classModule_1a498ecc0aebdc2e1d47d15ed1d3a34190}

연산에 참여하는 Operator들의 Gradient Container를 초기화시킨다.

Excutable [Operator](#classOperator) Container에 포함되어 있는 각 Operator들에서 Operator<DTYPE>::ResetGradient() 메소드를 호출한다. 
#### Returns
TRUE

#### `public virtual void `[`PrintInformation`](#classModule_1a1fe0649b5922714869c9727e6e48af86)`(int level)` {#classModule_1a1fe0649b5922714869c9727e6e48af86}

#### `public virtual void `[`SetDeviceCPU`](#classModule_1a002890bc0726abfe5807ed7fdc2b7009)`()` {#classModule_1a002890bc0726abfe5807ed7fdc2b7009}

모듈 그래프 학습에 사용되는 장치를 CPU로 전환하는 메소드

Module의 Device 멤버변수를 CPU로 전환하고, Excutable [Operator](#classOperator) Container의 각 Operator들에서 Operator<DTYPE>::SetDeviceCPU() 메소드를 순서대로 호출한다. 
#### Returns
없음

#### `public void `[`SetDeviceCPUOnModule`](#classModule_1afebb7db4c54e6405cb2a9fabf7ec4014)`()` {#classModule_1afebb7db4c54e6405cb2a9fabf7ec4014}

#### `public virtual int `[`Save`](#classModule_1ab932898db0934f08b11e58c527a21d3e)`(char * nameOfFile)` {#classModule_1ab932898db0934f08b11e58c527a21d3e}

#### `public virtual int `[`Load`](#classModule_1a533bb3a09eaaf78f468a8714f5897dd4)`(char * nameOfFile)` {#classModule_1a533bb3a09eaaf78f468a8714f5897dd4}

#### `public virtual int `[`Save`](#classModule_1a8d201e11894e203c26443830059247f4)`(FILE * fp)` {#classModule_1a8d201e11894e203c26443830059247f4}

#### `public virtual int `[`Load`](#classModule_1ae72b4ff6dca516608f7e86cedc707b97)`(FILE * fp)` {#classModule_1ae72b4ff6dca516608f7e86cedc707b97}

#### `public virtual int `[`SaveComponents`](#classModule_1a4e7ab899a27e1f29c16d12e12ce51c5f)`(char * nameOfDir)` {#classModule_1a4e7ab899a27e1f29c16d12e12ce51c5f}

#### `public virtual int `[`LoadComponents`](#classModule_1af089e75acd169b00241e3b33b9406da5)`(char * nameOfDir)` {#classModule_1af089e75acd169b00241e3b33b9406da5}

# class `MSE` {#classMSE}

```
class MSE
  : public LossFunction< DTYPE >
```  

Squared Error) Metric를 이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스

[MSE(Mean Squared Error)](#classMSE) 계산 식을 이용해 뉴럴 네트워크의 순전파를 통해 계산된 출력 Tensor와 레이블 값의 손실 함수를 계산한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`MSE`](#classMSE_1abb2d56ecf64d8e9d173912bba69e1e41)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | [MSE(Mean Squared Error)](#classMSE)[LossFunction](#classLossFunction) 클래스 생성자
`public inline virtual  `[`~MSE`](#classMSE_1a1fa27e77c38d0cfaf93317494d5f71c2)`()` | [MSE(Mean Squared Error)](#classMSE)[LossFunction](#classLossFunction) 클래스 소멸자
`public inline virtual int `[`Alloc`](#classMSE_1a70cb2a38095ef6da239ccee54d8464b6)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` | [MSE(Mean Squared Error)](#classMSE) LossFunction의 멤버 변수들을 동적 할당하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classMSE_1ae6cc6fffb56cc7ff699718451d446140)`(int pTime)` | [MSE(Mean Squared Error)](#classMSE) LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classMSE_1a90e2d9b6a762af5caaf9da8e8f611e80)`(int pTime)` | [MSE(Mean Squared Error)](#classMSE) LossFunction의 역전파를 수행하는 메소드
`public inline DTYPE `[`Error`](#classMSE_1a2259437b634090e2e74f44254f5276d8)`(DTYPE pred,DTYPE ans)` | 

## Members

#### `public inline  `[`MSE`](#classMSE_1abb2d56ecf64d8e9d173912bba69e1e41)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classMSE_1abb2d56ecf64d8e9d173912bba69e1e41}

[MSE(Mean Squared Error)](#classMSE)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator를 매개변수로 전달하여 [MSE<DTYPE>::Alloc(Operator<DTYPE> *pOperator)](#classMSE_1a70cb2a38095ef6da239ccee54d8464b6) 메소드를 호출한다. 
#### Parameters
* `pOperator` [MSE<DTYPE>::Alloc(Operator<DTYPE> *pOperator)](#classMSE_1a70cb2a38095ef6da239ccee54d8464b6) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `pName` LossFunction의 이름 

#### Returns
없음 

**See also**: [MSE<DTYPE>::Alloc(Operator<DTYPE> *pOperator)](#classMSE_1a70cb2a38095ef6da239ccee54d8464b6)

#### `public inline virtual  `[`~MSE`](#classMSE_1a1fa27e77c38d0cfaf93317494d5f71c2)`()` {#classMSE_1a1fa27e77c38d0cfaf93317494d5f71c2}

[MSE(Mean Squared Error)](#classMSE)[LossFunction](#classLossFunction) 클래스 소멸자

#### Returns
없음

#### `public inline virtual int `[`Alloc`](#classMSE_1a70cb2a38095ef6da239ccee54d8464b6)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` {#classMSE_1a70cb2a38095ef6da239ccee54d8464b6}

[MSE(Mean Squared Error)](#classMSE) LossFunction의 멤버 변수들을 동적 할당하는 메소드

매개변수로 전달받은 Operator를 Input Operator에 할당하고 초기화 된 Result 텐서를 동적으로 할당 및 생성한다. 
#### Parameters
* `pOperator` [MSE](#classMSE) LossFunction의 입력에 해당하는 [Operator](#classOperator)

#### Returns
TRUE

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classMSE_1ae6cc6fffb56cc7ff699718451d446140)`(int pTime)` {#classMSE_1ae6cc6fffb56cc7ff699718451d446140}

[MSE(Mean Squared Error)](#classMSE) LossFunction의 순전파를 수행하는 메소드

구성한 뉴럴 네트워크에서 얻어진 결과 값을 레이블 값과 비교해 Mse(Mean Squared Error)를 구한다 
#### Parameters
* `pTime` 입력 Tensor의 Time 축의 Dimension 

#### Returns
뉴럴 네트워크의 결과 값에 대한 [MSE(Mean Squared Error)](#classMSE)

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classMSE_1a90e2d9b6a762af5caaf9da8e8f611e80)`(int pTime)` {#classMSE_1a90e2d9b6a762af5caaf9da8e8f611e80}

[MSE(Mean Squared Error)](#classMSE) LossFunction의 역전파를 수행하는 메소드

구성한 뉴럴 네트워크에서 얻어진 [MSE(Mean Squared Error)](#classMSE)에 대한 입력 Tensor의 Gradient를 계산한다 
#### Parameters
* `pTime` 입력 Tensor의 Time 축의 Dimension 

#### Returns
NULL

#### `public inline DTYPE `[`Error`](#classMSE_1a2259437b634090e2e74f44254f5276d8)`(DTYPE pred,DTYPE ans)` {#classMSE_1a2259437b634090e2e74f44254f5276d8}

# class `NagOptimizer` {#classNagOptimizer}

```
class NagOptimizer
  : public Optimizer< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`NagOptimizer`](#classNagOptimizer_1a750cdedf0a089eb87691a76ce6e0969b)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,OptimizeDirection pOptimizeDirection)` | NagOptimizer의 생성자.
`public inline  `[`NagOptimizer`](#classNagOptimizer_1a990cfcecd6d15f27cb0574e58fd44913)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,float weightDecayRate,OptimizeDirection pOptimizeDirection)` | NagOptimizer의 생성자.
`public inline  `[`~NagOptimizer`](#classNagOptimizer_1afc95f34429bdd9679b1bfc13e291e5ed)`()` | NagOptimizer의 소멸자
`public inline virtual void `[`Delete`](#classNagOptimizer_1a42d3725f2f08127b154dcab46a9c970c)`()` | Optimizer의 Delete 매소드
`public inline int `[`Alloc`](#classNagOptimizer_1a1eb291e54867352b01ca57c3da27d14b)`(float momentum)` | Optimizer의 Alloc 매소드
`public inline virtual int `[`UpdateParameter`](#classNagOptimizer_1aeb0295ed90b6752805136838910d2ce5)`()` | 파라미터 값들을 업데이트 하는 메소드
`public inline virtual int `[`UpdateParameter`](#classNagOptimizer_1a58a02e3959b18c588ff7629766375c3d)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` | UpdateParameter default 함수
`public inline int `[`UpdateParameter`](#classNagOptimizer_1a4ac96ef206ce18f94570dfb6373b259f)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * pVelocity)` | 파라미터 값들을 업데이트 하는 메소드

## Members

#### `public inline  `[`NagOptimizer`](#classNagOptimizer_1a750cdedf0a089eb87691a76ce6e0969b)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,OptimizeDirection pOptimizeDirection)` {#classNagOptimizer_1a750cdedf0a089eb87691a76ce6e0969b}

NagOptimizer의 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pLearningRate` Optimizer의 learning rate 

* `momentum` step size 조정 값 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(momentum)

#### `public inline  `[`NagOptimizer`](#classNagOptimizer_1a990cfcecd6d15f27cb0574e58fd44913)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float momentum,float weightDecayRate,OptimizeDirection pOptimizeDirection)` {#classNagOptimizer_1a990cfcecd6d15f27cb0574e58fd44913}

NagOptimizer의 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pLearningRate` Optimizer의 learning rate 

* `m_momentum` step size 조정 값 

* `weightDecayRate` 가중치 매개변수가 클 때 패널티를 부과하는 값 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(momentum)

#### `public inline  `[`~NagOptimizer`](#classNagOptimizer_1afc95f34429bdd9679b1bfc13e291e5ed)`()` {#classNagOptimizer_1afc95f34429bdd9679b1bfc13e291e5ed}

NagOptimizer의 소멸자

#### Returns
없음

#### `public inline virtual void `[`Delete`](#classNagOptimizer_1a42d3725f2f08127b154dcab46a9c970c)`()` {#classNagOptimizer_1a42d3725f2f08127b154dcab46a9c970c}

Optimizer의 Delete 매소드

맴버 변수 m_aaVelocity의 메모리 할당을 해제한다. 
#### Returns
없음

#### `public inline int `[`Alloc`](#classNagOptimizer_1a1eb291e54867352b01ca57c3da27d14b)`(float momentum)` {#classNagOptimizer_1a1eb291e54867352b01ca57c3da27d14b}

Optimizer의 Alloc 매소드

맴버 변수 m_ppParameter, m_numOfParameter, m_aaVelocity를 초기화한다.

m_aaVelocity를 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다. 
#### Parameters
* `m_momentum` step size 조정 값 

#### Returns
성공 시 TRUE 

**See also**: [Container](#classContainer)<[Operator<DTYPE>](#classOperator) *>* GetTrainableTensor() 

**See also**: int GetTrainableTensorDegree()

#### `public inline virtual int `[`UpdateParameter`](#classNagOptimizer_1aeb0295ed90b6752805136838910d2ce5)`()` {#classNagOptimizer_1aeb0295ed90b6752805136838910d2ce5}

파라미터 값들을 업데이트 하는 메소드

m_momentum 유무에 따라 UpdateParameter 호출과 에러 메세지 호출 
#### Returns
성공 시 TRUE 

**See also**: int [UpdateParameter](#classNagOptimizer_1aeb0295ed90b6752805136838910d2ce5)(([Operator<DTYPE>](#classOperator) *pParameter, [Tensor<DTYPE>](#classTensor) *pVelocity)

#### `public inline virtual int `[`UpdateParameter`](#classNagOptimizer_1a58a02e3959b18c588ff7629766375c3d)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` {#classNagOptimizer_1a58a02e3959b18c588ff7629766375c3d}

UpdateParameter default 함수

#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

#### Returns
성공 시 TRUE

#### `public inline int `[`UpdateParameter`](#classNagOptimizer_1a4ac96ef206ce18f94570dfb6373b259f)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * pVelocity)` {#classNagOptimizer_1a4ac96ef206ce18f94570dfb6373b259f}

파라미터 값들을 업데이트 하는 메소드

prev_Velocity 텐서 생성 후 현재 pVelocity 저장

pVelocity를 Update 한다.

m_momentum 값으로 조정된 prev_Velocity와 pVelocity의 연산으로 파라미터 Update

학습 초반 부, pFirstMomentum, pFirstVelocity는 0으로 biased 상태이므로 이를 unbiased 해주는 연산하여 업데이트 한다.

signed_learning_rate와 pUnbiasedMomentum곱을 root가 적용된 pUnbiasedVelocity와 m_epsilon으로 나눈 값으로 weight(trainable_data)를 업데이트 한다. 
#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pVelocity` 업데이트 할 pVelocity 

#### Returns
성공 시 TURE

# class `NeuralNetwork` {#classNeuralNetwork}

```
class NeuralNetwork
  : public Module< DTYPE >
```  

모델 생성, 학습 및 평가를 총괄하는 클래스

[Operator](#classOperator), [Module](#classModule), Loss Function, [Optimizer](#classOptimizer) 클래스를 생성 및 활용해 뉴럴 네트워크를 구성하고 학습시킨다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`NeuralNetwork`](#classNeuralNetwork_1a20d3f6e11c5829f2cd33a5201d730f15)`()` | [NeuralNetwork](#classNeuralNetwork) 클래스 생성자
`public virtual  `[`~NeuralNetwork`](#classNeuralNetwork_1a3a18db7bfba7c6b8c00cd8c3c227b9cf)`()` | [NeuralNetwork](#classNeuralNetwork) 클래스 소멸자
`public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`SetLossFunction`](#classNeuralNetwork_1a0f17e2c4a002186a336bb1c80e789a03)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pLossFunction)` | 특정 Loss Function을 매개 변수로 받아 이를 신경망의 Loss Function로 지정해주는 메소드
`public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`SetOptimizer`](#classNeuralNetwork_1a8324e148cc31f3fbb81667287bb4ee61)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pOptimizer)` | 특정 Optimizer를 매개 변수로 받아 이를 신경망의 Optimizer로 지정해주는 메소드
`public `[`Operator`](#classOperator)`< DTYPE > * `[`GetResultOperator`](#classNeuralNetwork_1a47ed18a44570c4868339187aebe0e3c9)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classNeuralNetwork_1aa00549772d4d9b5555cc123cd463638d)`()` | 
`public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`GetLossFunction`](#classNeuralNetwork_1ad54e92ce0198b90a4fba80c8f0fe4258)`()` | 
`public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`GetOptimizer`](#classNeuralNetwork_1a98292f1272832febf221f2660673b60c)`()` | 
`public virtual void `[`SetDeviceCPU`](#classNeuralNetwork_1a58c83f661d1afc455fa6a848d238e823)`()` | 신경망 그래프 학습에 사용되는 장치를 CPU로 전환하는 메소드
`public void `[`SetDeviceCPUOnNeuralNetwork`](#classNeuralNetwork_1a411566bb635a12dbbb67fa38af7eb10f)`()` | 
`public int `[`Train`](#classNeuralNetwork_1a9f60df7d21b76fc1a194bfc7f5857ebd)`()` | 신경망의 학습을 진행하는 메소드
`public int `[`Test`](#classNeuralNetwork_1ad38d080bc60559e6f37ac3006dea1bb6)`()` | 신경망의 테스트를 진행하는 메소드
`public int `[`TrainOnCPU`](#classNeuralNetwork_1a6527833265b19ba3d2aaf755ea0fdfa3)`()` | CPU를 활용해 신경망을 학습시키는 메소드
`public int `[`TestOnCPU`](#classNeuralNetwork_1a16bd0b041c7055340b0ef11bc95a59bf)`()` | CPU를 활용해 신경망을 테스트하는 메소드
`public int `[`TrainOnGPU`](#classNeuralNetwork_1ac6a18d638c34093a325ef4e09dbc2978)`()` | GPU를 활용해 신경망을 학습시키는 메소드
`public int `[`TestOnGPU`](#classNeuralNetwork_1afcdc8ca3b16f063b4d67c3e4b72d5ee0)`()` | GPU를 활용해 신경망을 테스트하는 메소드
`public float `[`GetAccuracy`](#classNeuralNetwork_1a3562597ed1ba1d43eae487a699bcf91a)`(int numOfClass)` | 분류(Classification)를 위해 학습된 신경망의 Top 1 Accuracy를 계산하는 메소드
`public int `[`GetMaxIndex`](#classNeuralNetwork_1a82da1af0e953ca99fff74684802dcd33)`(`[`Tensor`](#classTensor)`< DTYPE > * data,int ba,int ti,int numOfClass)` | Tensor의 LongArray의 Element들 중 가장 큰 값의 인덱스를 계산해 반환하는 메소드
`public float `[`GetTop5Accuracy`](#classNeuralNetwork_1a8b2e1e719ed1429aed9f425d228937fb)`(int numOfClass)` | 분류(Classification)를 위해 학습된 신경망의 Top 5 Accuracy를 계산하는 메소드
`public void `[`GetTop5Index`](#classNeuralNetwork_1aa068fb156df1718020f9ada53eb2cb38)`(`[`Tensor`](#classTensor)`< DTYPE > * data,int * top5Index,int ba,int ti,int numOfClass)` | Tensor의 LongArray의 Element들 중 가장 큰 다섯 개 값에 대한 인덱스를 계산해 반환하는 메소드
`public float `[`GetLoss`](#classNeuralNetwork_1af33f9fefe93bbaf0dc87f5fac6632539)`()` | 데이터에 대해 학습된 신경망의 평균 Loss를 계산하여 반환하는 메소드
`public void `[`PrintGraphInformation`](#classNeuralNetwork_1a8c2e90c65b99b7da8a4cf1ee70c7d479)`()` | 신경망 그래프의 각 구성 요소에 대해 정보를 출력하는 메소드
`public int `[`ResetLossFunctionResult`](#classNeuralNetwork_1af408546e239aab642945d8142223e278)`()` | LossFunction의 Result Tensor를 초기화시킨다.
`public int `[`ResetLossFunctionGradient`](#classNeuralNetwork_1a5e3c7ae5f4717a80089ccb89772394d3)`()` | LossFunction의 Gradient Tensor를 초기화시킨다.
`public int `[`ResetParameterGradient`](#classNeuralNetwork_1a4cb542f78efa4472bdcd317aa79087d6)`()` | Optimizer의 Gradient와 Parameter들의 Gradient를 초기화시킨다.
`public `[`Operator`](#classOperator)`< DTYPE > * `[`SearchOperator`](#classNeuralNetwork_1a28f8478e6b84704f11b52cfa6c291a81)`(std::string pName)` | 
`public void `[`InputToFeature`](#classNeuralNetwork_1abb8436142f9031d3c7385b5a7f274442)`(int inDim,int noSample,float * pSamples,int outDim,float * pFeatures,int batchSize)` | 

## Members

#### `public  `[`NeuralNetwork`](#classNeuralNetwork_1a20d3f6e11c5829f2cd33a5201d730f15)`()` {#classNeuralNetwork_1a20d3f6e11c5829f2cd33a5201d730f15}

[NeuralNetwork](#classNeuralNetwork) 클래스 생성자

각 멤버 변수들을 초기화하고 [NeuralNetwork](#classNeuralNetwork) 클래스를 생성한다.

각 포인터들을 NULL 값으로, 각 정수 타입 변수들은 0으로, Device는 CPU로 초기화하고 NeuralNetwork<DTYPE>::Alloc() 메소드를 호출한다. 
#### Returns
없음 

**See also**: NeuralNetwork<DTYPE>::Alloc()

#### `public virtual  `[`~NeuralNetwork`](#classNeuralNetwork_1a3a18db7bfba7c6b8c00cd8c3c227b9cf)`()` {#classNeuralNetwork_1a3a18db7bfba7c6b8c00cd8c3c227b9cf}

[NeuralNetwork](#classNeuralNetwork) 클래스 소멸자

동적으로 할당 받은 [NeuralNetwork](#classNeuralNetwork) 클래스의 멤버 변수들을 할당 해제하고 클래스를 소멸시킨다. 
#### Returns
없음 

**See also**: NeuralNetwork<DTYPE>::Delete()

#### `public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`SetLossFunction`](#classNeuralNetwork_1a0f17e2c4a002186a336bb1c80e789a03)`(`[`LossFunction`](#classLossFunction)`< DTYPE > * pLossFunction)` {#classNeuralNetwork_1a0f17e2c4a002186a336bb1c80e789a03}

특정 Loss Function을 매개 변수로 받아 이를 신경망의 Loss Function로 지정해주는 메소드

#### Parameters
* `pLossFunction` 신경망의 Loss Function로 지정하고자 하는 Loss Function 

#### Returns
매개변수로 받은 Loss Function

#### `public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`SetOptimizer`](#classNeuralNetwork_1a8324e148cc31f3fbb81667287bb4ee61)`(`[`Optimizer`](#classOptimizer)`< DTYPE > * pOptimizer)` {#classNeuralNetwork_1a8324e148cc31f3fbb81667287bb4ee61}

특정 Optimizer를 매개 변수로 받아 이를 신경망의 Optimizer로 지정해주는 메소드

#### Parameters
* `pLossFunction` 신경망의 Optimizer로 지정하고자 하는 [Optimizer](#classOptimizer)

#### Returns
매개변수로 받은 [Optimizer](#classOptimizer)

#### `public `[`Operator`](#classOperator)`< DTYPE > * `[`GetResultOperator`](#classNeuralNetwork_1a47ed18a44570c4868339187aebe0e3c9)`()` {#classNeuralNetwork_1a47ed18a44570c4868339187aebe0e3c9}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classNeuralNetwork_1aa00549772d4d9b5555cc123cd463638d)`()` {#classNeuralNetwork_1aa00549772d4d9b5555cc123cd463638d}

#### `public `[`LossFunction`](#classLossFunction)`< DTYPE > * `[`GetLossFunction`](#classNeuralNetwork_1ad54e92ce0198b90a4fba80c8f0fe4258)`()` {#classNeuralNetwork_1ad54e92ce0198b90a4fba80c8f0fe4258}

#### `public `[`Optimizer`](#classOptimizer)`< DTYPE > * `[`GetOptimizer`](#classNeuralNetwork_1a98292f1272832febf221f2660673b60c)`()` {#classNeuralNetwork_1a98292f1272832febf221f2660673b60c}

#### `public virtual void `[`SetDeviceCPU`](#classNeuralNetwork_1a58c83f661d1afc455fa6a848d238e823)`()` {#classNeuralNetwork_1a58c83f661d1afc455fa6a848d238e823}

신경망 그래프 학습에 사용되는 장치를 CPU로 전환하는 메소드

NeuralNetwork의 Device 멤버변수를 CPU로 전환하고, Excutable [Operator](#classOperator) Container의 각 Operator들에서 Operator<DTYPE>::SetDeviceCPU() 메소드를 순서대로 호출하고, Lossfunction의 LossFunction<DTYPE>::SetDeviceCPU() 메소드를 호출한다. 
#### Returns
없음

#### `public void `[`SetDeviceCPUOnNeuralNetwork`](#classNeuralNetwork_1a411566bb635a12dbbb67fa38af7eb10f)`()` {#classNeuralNetwork_1a411566bb635a12dbbb67fa38af7eb10f}

#### `public int `[`Train`](#classNeuralNetwork_1a9f60df7d21b76fc1a194bfc7f5857ebd)`()` {#classNeuralNetwork_1a9f60df7d21b76fc1a194bfc7f5857ebd}

신경망의 학습을 진행하는 메소드

NeuralNetwork의 Device 멤버 변수를 확인하여 CPU 시 NeuralNetwork<DTYPE>::TrainingOnCPU()을 호출하고, GPU 시 NeuralNetwork<DTYPE>::TrainingOnGPU()을 호출한다. 
#### Returns
성공 시 TRUE, m_Device 멤버 변수가 잘못된 값을 갖고 있을 때 FALSE를 반환한다.

#### `public int `[`Test`](#classNeuralNetwork_1ad38d080bc60559e6f37ac3006dea1bb6)`()` {#classNeuralNetwork_1ad38d080bc60559e6f37ac3006dea1bb6}

신경망의 테스트를 진행하는 메소드

NeuralNetwork의 Device 멤버 변수를 확인하여 CPU 시 NeuralNetwork<DTYPE>::TestingOnCPU()을 호출하고, GPU 시 NeuralNetwork<DTYPE>::TestingOnGPU()을 호출한다. 
#### Returns
성공 시 TRUE, m_Device 멤버 변수가 잘못된 값을 갖고 있을 때 FALSE를 반환한다.

#### `public int `[`TrainOnCPU`](#classNeuralNetwork_1a6527833265b19ba3d2aaf755ea0fdfa3)`()` {#classNeuralNetwork_1a6527833265b19ba3d2aaf755ea0fdfa3}

CPU를 활용해 신경망을 학습시키는 메소드

순서대로 Excutable Operator들의 Result와 Gradient를 초기화하고 Loss Function의 Result와 Gradient를 초기화하고 ForwardPropagate, BackwardPropagate 메소드를 호출하고 Optimizer로 파라미터를 학습시킨다.

각 메소드 참조 
#### Returns
TRUE 

**See also**: NeuralNetwork<DTYPE>::ResetOperatorResult() NeuralNetwork<DTYPE>::ResetOperatorGradient() [NeuralNetwork<DTYPE>::ResetLossFunctionResult()](#classNeuralNetwork_1af408546e239aab642945d8142223e278)[NeuralNetwork<DTYPE>::ResetLossFunctionGradient()](#classNeuralNetwork_1a5e3c7ae5f4717a80089ccb89772394d3)

**See also**: [NeuralNetwork<DTYPE>::ForwardPropagate()](#classModule_1a1bea4bd0b2831e0c21696998393cc263)[NeuralNetwork<DTYPE>::BackPropagate()](#classModule_1a561a89214a6252632cbc507ef6e35b58)[Optimizer<DTYPE>::UpdateParameter()](#classOptimizer_1a5a989eee4fa18a9b4ee81b1b9bac2814)

#### `public int `[`TestOnCPU`](#classNeuralNetwork_1a16bd0b041c7055340b0ef11bc95a59bf)`()` {#classNeuralNetwork_1a16bd0b041c7055340b0ef11bc95a59bf}

CPU를 활용해 신경망을 테스트하는 메소드

순서대로 Excutable Operator들의 Result를 초기화하고 Loss Function의 Result를 초기화하고 ForwardPropagate메소드를 호출한다.

각 메소드 참조 
#### Returns
TRUE 

**See also**: NeuralNetwork<DTYPE>::ResetOperatorResult() [NeuralNetwork<DTYPE>::ResetLossFunctionResult()](#classNeuralNetwork_1af408546e239aab642945d8142223e278)[NeuralNetwork<DTYPE>::ForwardPropagate()](#classModule_1a1bea4bd0b2831e0c21696998393cc263)

#### `public int `[`TrainOnGPU`](#classNeuralNetwork_1ac6a18d638c34093a325ef4e09dbc2978)`()` {#classNeuralNetwork_1ac6a18d638c34093a325ef4e09dbc2978}

GPU를 활용해 신경망을 학습시키는 메소드

순서대로 Excutable Operator들의 Result와 Gradient를 초기화하고 Loss Function의 Result와 Gradient를 초기화하고 @detaisl ForwardPropagateOnGPU, BackwardPropagateOnGPU 메소드를 호출하고 Optimizer로 파라미터를 학습시킨다.

각 메소드 참조 
#### Returns
TRUE 

**See also**: NeuralNetwork<DTYPE>::ResetOperatorResult() NeuralNetwork<DTYPE>::ResetOperatorGradient() [NeuralNetwork<DTYPE>::ResetLossFunctionResult()](#classNeuralNetwork_1af408546e239aab642945d8142223e278)[NeuralNetwork<DTYPE>::ResetLossFunctionGradient()](#classNeuralNetwork_1a5e3c7ae5f4717a80089ccb89772394d3)

**See also**: NeuralNetwork<DTYPE>::ForwardPropagateOnGPU() NeuralNetwork<DTYPE>::BackPropagateOnGPU() Optimizer<DTYPE>::UpdateParameterOnGPU()

#### `public int `[`TestOnGPU`](#classNeuralNetwork_1afcdc8ca3b16f063b4d67c3e4b72d5ee0)`()` {#classNeuralNetwork_1afcdc8ca3b16f063b4d67c3e4b72d5ee0}

GPU를 활용해 신경망을 테스트하는 메소드

순서대로 Excutable Operator들의 Result를 초기화하고 Loss Function의 Result를 초기화하고 ForwardPropagateOnGPU메소드를 호출한다.

각 메소드 참조 
#### Returns
TRUE 

**See also**: NeuralNetwork<DTYPE>::ResetOperatorResult() [NeuralNetwork<DTYPE>::ResetLossFunctionResult()](#classNeuralNetwork_1af408546e239aab642945d8142223e278) NeuralNetwork<DTYPE>::ForwardPropagateOnGPU()

#### `public float `[`GetAccuracy`](#classNeuralNetwork_1a3562597ed1ba1d43eae487a699bcf91a)`(int numOfClass)` {#classNeuralNetwork_1a3562597ed1ba1d43eae487a699bcf91a}

분류(Classification)를 위해 학습된 신경망의 Top 1 Accuracy를 계산하는 메소드

#### Parameters
* `numOfClass` 데이터의 분류(Classification)에 이용되는 label의 개수 

#### Returns
신경망의 Top 1 Accuracy : 0. ~ 1.

#### `public int `[`GetMaxIndex`](#classNeuralNetwork_1a82da1af0e953ca99fff74684802dcd33)`(`[`Tensor`](#classTensor)`< DTYPE > * data,int ba,int ti,int numOfClass)` {#classNeuralNetwork_1a82da1af0e953ca99fff74684802dcd33}

Tensor의 LongArray의 Element들 중 가장 큰 값의 인덱스를 계산해 반환하는 메소드

#### Parameters
* `data` 탐색하고자 하는 [Tensor](#classTensor)

* `ba` Tensor의 batch Size 

* `ti` Tensor의 Time Size 

* `numOfClass` Tensor의 LongArray의 Element 개수 

#### Returns
매개변수로 전달받은 Tensor의 LongArray의 Element들 중 가장 큰 값의 인덱스

#### `public float `[`GetTop5Accuracy`](#classNeuralNetwork_1a8b2e1e719ed1429aed9f425d228937fb)`(int numOfClass)` {#classNeuralNetwork_1a8b2e1e719ed1429aed9f425d228937fb}

분류(Classification)를 위해 학습된 신경망의 Top 5 Accuracy를 계산하는 메소드

#### Parameters
* `numOfClass` 데이터의 분류(Classification)에 이용되는 label의 개수 

#### Returns
신경망의 Accuracy : 0. ~ 1.

#### `public void `[`GetTop5Index`](#classNeuralNetwork_1aa068fb156df1718020f9ada53eb2cb38)`(`[`Tensor`](#classTensor)`< DTYPE > * data,int * top5Index,int ba,int ti,int numOfClass)` {#classNeuralNetwork_1aa068fb156df1718020f9ada53eb2cb38}

Tensor의 LongArray의 Element들 중 가장 큰 다섯 개 값에 대한 인덱스를 계산해 반환하는 메소드

#### Parameters
* `data` 탐색하고자 하는 [Tensor](#classTensor)

* `ba` Tensor의 batch Size 

* `ti` Tensor의 Time Size 

* `numOfClass` Tensor의 LongArray의 Element 개수 

#### Returns
매개변수로 전달받은 Tensor의 LongArray의 Element들 중 가장 큰 다섯 개 값에 대한 인덱스

#### `public float `[`GetLoss`](#classNeuralNetwork_1af33f9fefe93bbaf0dc87f5fac6632539)`()` {#classNeuralNetwork_1af33f9fefe93bbaf0dc87f5fac6632539}

데이터에 대해 학습된 신경망의 평균 Loss를 계산하여 반환하는 메소드

#### Returns
학습된 신경망의 평균 Loss

#### `public void `[`PrintGraphInformation`](#classNeuralNetwork_1a8c2e90c65b99b7da8a4cf1ee70c7d479)`()` {#classNeuralNetwork_1a8c2e90c65b99b7da8a4cf1ee70c7d479}

신경망 그래프의 각 구성 요소에 대해 정보를 출력하는 메소드

#### Returns
없음 

**See also**: Operator<DTYPE>::PrintInformation() LossFunction<DTYPE>::GetName()

#### `public int `[`ResetLossFunctionResult`](#classNeuralNetwork_1af408546e239aab642945d8142223e278)`()` {#classNeuralNetwork_1af408546e239aab642945d8142223e278}

LossFunction의 Result Tensor를 초기화시킨다.

LossFunction의 [LossFunction<DTYPE>::ResetResult()](#classLossFunction_1a218be336d4c24afd3ca91ee58ea600e0) 메소드를 호출한다. 
#### Returns
TRUE

#### `public int `[`ResetLossFunctionGradient`](#classNeuralNetwork_1a5e3c7ae5f4717a80089ccb89772394d3)`()` {#classNeuralNetwork_1a5e3c7ae5f4717a80089ccb89772394d3}

LossFunction의 Gradient Tensor를 초기화시킨다.

LossFunction의 Lossfunction<DTYPE>::ResetGradient() 메소드를 호출한다. 
#### Returns
TRUE

#### `public int `[`ResetParameterGradient`](#classNeuralNetwork_1a4cb542f78efa4472bdcd317aa79087d6)`()` {#classNeuralNetwork_1a4cb542f78efa4472bdcd317aa79087d6}

Optimizer의 Gradient와 Parameter들의 Gradient를 초기화시킨다.

Optimizer의 Optimzier<DTYPE>::ResetParameterGradient() 메소드를 호출한다. 
#### Returns
TRUE

#### `public `[`Operator`](#classOperator)`< DTYPE > * `[`SearchOperator`](#classNeuralNetwork_1a28f8478e6b84704f11b52cfa6c291a81)`(std::string pName)` {#classNeuralNetwork_1a28f8478e6b84704f11b52cfa6c291a81}

#### `public void `[`InputToFeature`](#classNeuralNetwork_1abb8436142f9031d3c7385b5a7f274442)`(int inDim,int noSample,float * pSamples,int outDim,float * pFeatures,int batchSize)` {#classNeuralNetwork_1abb8436142f9031d3c7385b5a7f274442}

# class `NoiseGenerator` {#classNoiseGenerator}

```
class NoiseGenerator
  : public Operator< DTYPE >
```  

[Tensor](#classTensor) 클래스의 Random_normal 함수를 사용하여 범위 내의 임의의 값을 갖는 [Tensor](#classTensor) 생성

[Operator](#classOperator) 형식이지만 Tensor를 저장하는 용도로만 사용

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`NoiseGenerator`](#classNoiseGenerator_1a0914cd702e5a449df57ca18a5771d157)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName)` | 
`public inline  `[`NoiseGenerator`](#classNoiseGenerator_1a7d16c1f9aa5bace194c7bfff7e9e0d3c)`(`[`Shape`](#classShape)` * pShape,std::string pName)` | 
`public inline  `[`~NoiseGenerator`](#classNoiseGenerator_1a0d7e50b7fe67c356c65023f4d672e4cf)`()` | 

## Members

#### `public inline  `[`NoiseGenerator`](#classNoiseGenerator_1a0914cd702e5a449df57ca18a5771d157)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName)` {#classNoiseGenerator_1a0914cd702e5a449df57ca18a5771d157}

#### `public inline  `[`NoiseGenerator`](#classNoiseGenerator_1a7d16c1f9aa5bace194c7bfff7e9e0d3c)`(`[`Shape`](#classShape)` * pShape,std::string pName)` {#classNoiseGenerator_1a7d16c1f9aa5bace194c7bfff7e9e0d3c}

#### `public inline  `[`~NoiseGenerator`](#classNoiseGenerator_1a0d7e50b7fe67c356c65023f4d672e4cf)`()` {#classNoiseGenerator_1a0d7e50b7fe67c356c65023f4d672e4cf}

# class `Operator` {#classOperator}

본 프래임워크의 가장 작은 연산 단위.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`Operator`](#classOperator_1acd1324c1a03947cd33fb88b445a0a39a)`(std::string pName,int pLoadflag)` | 
`public  `[`Operator`](#classOperator_1a08fa1d32571c8bd2ffd42fef58925a0e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` | 
`public  `[`Operator`](#classOperator_1a28b8580b946a75f0b8d5a58cb22954c5)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,std::string pName,int pLoadflag)` | 
`public  `[`Operator`](#classOperator_1a13392572eaf76c36e45534f492cda060)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,`[`Operator`](#classOperator)`< DTYPE > * pInput2,std::string pName,int pLoadflag)` | 
`public  `[`Operator`](#classOperator_1a620d301674f2a2f7b9cbf907ef31ad21)`(int numInput,...)` | 
`public virtual  `[`~Operator`](#classOperator_1a3fdf52b48772b7025c7baca76c7378f4)`()` | 
`public int `[`AddEdgebetweenOperators`](#classOperator_1ae7bbac482bcec78495554f1c65d35ef1)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 
`public int `[`AddEdgebetweenOperators`](#classOperator_1a991087201b942fab657c2c0b0443a178)`(int numInput,va_list ap)` | 
`public int `[`AddEdgebetweenOperators`](#classOperator_1aa2316371d2058460f3e62e13fba385f5)`(int numInput,...)` | 
`public int `[`AddResult`](#classOperator_1a93c7f1c2190df793af1260c0ca43a3f2)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public int `[`AddGradient`](#classOperator_1a0afb3e4d2c98796c513b98d259f7c9d8)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public int `[`AddDelta`](#classOperator_1a77805e7510c3f37ddfc3c736af3a012e)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public int `[`SetResult`](#classOperator_1a88221e83a8df456434bba59e3b30cabe)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public int `[`SetGradient`](#classOperator_1a6a0a0d6afabdedf0d8d9276e01136f92)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public int `[`SetDelta`](#classOperator_1ad12157211e348fef2dd17b6133724bc1)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public int `[`SetDevice`](#classOperator_1a1f176cc41bbb083ff1093c6257e385c5)`(Device pDevice)` | 
`public int `[`SetDeviceID`](#classOperator_1acb1289501c960cc9d1df70c70f97e40e)`(unsigned int idOfDevice)` | 
`public int `[`SetIsTensorholder`](#classOperator_1a06bd203382508c442b475c155c716977)`(int pIsParameter)` | 
`public int `[`SetIsTrainable`](#classOperator_1ab7944e858af96f1cecad24b323d26e82)`(int pIsTrainable)` | 
`public virtual int `[`SetModeTrain`](#classOperator_1a4824e1608881401f8d14a96c9e1c4438)`()` | 
`public virtual int `[`SetModeAccumulate`](#classOperator_1a142ad78819c1ecf4c49953e33119c8e6)`()` | 
`public virtual int `[`SetModeInference`](#classOperator_1ad81f3e8a1656100cbc4d79954957c29d)`()` | 
`public virtual `[`Operator`](#classOperator)`< DTYPE > ** `[`GetOutput`](#classOperator_1ad7be1cef2f71adcb0c22dc6f051cd445)`()` | 
`public virtual `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetOutputContainer`](#classOperator_1a2aaef42413eba0597b3566f15f3c0b30)`()` | 
`public virtual `[`Operator`](#classOperator)`< DTYPE > ** `[`GetInput`](#classOperator_1a42d8adb079719054278d20b080c427db)`()` | 
`public virtual `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetInputContainer`](#classOperator_1a7b3fea224107fbd9afbef5df03163caa)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classOperator_1adecf0400d0808f396df03409da96a7f1)`() const` | 
`public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetResultContainer`](#classOperator_1a9abbb587f199f755336dca416578cf6b)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetGradient`](#classOperator_1a4851981c3868c8b9755dc5e9294964a0)`() const` | 
`public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetGradientContainer`](#classOperator_1a56728499112d7d5c7ac46be21d443bd7)`()` | 
`public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetDelta`](#classOperator_1aa73e50f59bb10fa2ddd16f19ba746570)`() const` | 
`public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetDeltaContainer`](#classOperator_1ab45d910fd0780a845516acbbb336ddc7)`()` | 
`public std::string `[`GetName`](#classOperator_1a8d4325a95bcc43efc8f0b61f013afe89)`() const` | 
`public virtual Device `[`GetDevice`](#classOperator_1afba23ac8b7ef98da83a8d32b34a183df)`()` | 
`public virtual int `[`GetDeviceID`](#classOperator_1aa2450a0e0dc58a850c80003c3f38cd71)`()` | 
`public int `[`GetIsTensorholder`](#classOperator_1a790df61eaa66bcbdbfd5938848940ec9)`()` | 
`public int `[`GetIsTrainable`](#classOperator_1a5d0c55b1780c3d9cfcbcc1b5e6e0460e)`()` | 
`public virtual int `[`ForwardPropagate`](#classOperator_1a6a409fc71926fcc9839ad24fecf58a9a)`(int pTime)` | 
`public virtual int `[`BackPropagate`](#classOperator_1a6d587c2552338a90a7f59767bdbfef44)`(int pTime)` | 
`public virtual int `[`ResetResult`](#classOperator_1a5c980663d286c420e502450d5fc84867)`()` | 
`public virtual int `[`ResetGradient`](#classOperator_1a953a44849b76004f8e9e0ae76a4ed57a)`()` | 
`public virtual void `[`PrintInformation`](#classOperator_1a9ea8ed916722bc4bfbc8f765d62f3585)`(int level)` | 
`public virtual void `[`SetDeviceCPU`](#classOperator_1ae322cf78613b9c3c1b72dcbf133e6157)`()` | 
`public virtual int `[`SetResultOnCPU`](#classOperator_1a3a96036162c9c4e5af2c214793237ade)`()` | 
`public virtual int `[`SetGradientOnCPU`](#classOperator_1a58a436df26798b574dbb52065c226505)`()` | 
`public virtual int `[`Save`](#classOperator_1a7b06ca1781b552310dd8e05bd4afa369)`(char * nameOfFile)` | 
`public virtual int `[`Load`](#classOperator_1a241885dbc7d5e5b35e2106ef9bbed53c)`(char * nameOfFile)` | 
`public virtual int `[`Load`](#classOperator_1a16d495a83c27bad4aeacd6ce4569a8f7)`(FILE * fp)` | 
`public virtual int `[`Save`](#classOperator_1afd997818c44df1bdf94385cc1611d0e7)`(FILE * fp)` | 

## Members

#### `public  `[`Operator`](#classOperator_1acd1324c1a03947cd33fb88b445a0a39a)`(std::string pName,int pLoadflag)` {#classOperator_1acd1324c1a03947cd33fb88b445a0a39a}

#### `public  `[`Operator`](#classOperator_1a08fa1d32571c8bd2ffd42fef58925a0e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` {#classOperator_1a08fa1d32571c8bd2ffd42fef58925a0e}

#### `public  `[`Operator`](#classOperator_1a28b8580b946a75f0b8d5a58cb22954c5)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,std::string pName,int pLoadflag)` {#classOperator_1a28b8580b946a75f0b8d5a58cb22954c5}

#### `public  `[`Operator`](#classOperator_1a13392572eaf76c36e45534f492cda060)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,`[`Operator`](#classOperator)`< DTYPE > * pInput2,std::string pName,int pLoadflag)` {#classOperator_1a13392572eaf76c36e45534f492cda060}

#### `public  `[`Operator`](#classOperator_1a620d301674f2a2f7b9cbf907ef31ad21)`(int numInput,...)` {#classOperator_1a620d301674f2a2f7b9cbf907ef31ad21}

#### `public virtual  `[`~Operator`](#classOperator_1a3fdf52b48772b7025c7baca76c7378f4)`()` {#classOperator_1a3fdf52b48772b7025c7baca76c7378f4}

#### `public int `[`AddEdgebetweenOperators`](#classOperator_1ae7bbac482bcec78495554f1c65d35ef1)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classOperator_1ae7bbac482bcec78495554f1c65d35ef1}

#### `public int `[`AddEdgebetweenOperators`](#classOperator_1a991087201b942fab657c2c0b0443a178)`(int numInput,va_list ap)` {#classOperator_1a991087201b942fab657c2c0b0443a178}

#### `public int `[`AddEdgebetweenOperators`](#classOperator_1aa2316371d2058460f3e62e13fba385f5)`(int numInput,...)` {#classOperator_1aa2316371d2058460f3e62e13fba385f5}

#### `public int `[`AddResult`](#classOperator_1a93c7f1c2190df793af1260c0ca43a3f2)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classOperator_1a93c7f1c2190df793af1260c0ca43a3f2}

#### `public int `[`AddGradient`](#classOperator_1a0afb3e4d2c98796c513b98d259f7c9d8)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classOperator_1a0afb3e4d2c98796c513b98d259f7c9d8}

#### `public int `[`AddDelta`](#classOperator_1a77805e7510c3f37ddfc3c736af3a012e)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classOperator_1a77805e7510c3f37ddfc3c736af3a012e}

#### `public int `[`SetResult`](#classOperator_1a88221e83a8df456434bba59e3b30cabe)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classOperator_1a88221e83a8df456434bba59e3b30cabe}

#### `public int `[`SetGradient`](#classOperator_1a6a0a0d6afabdedf0d8d9276e01136f92)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classOperator_1a6a0a0d6afabdedf0d8d9276e01136f92}

#### `public int `[`SetDelta`](#classOperator_1ad12157211e348fef2dd17b6133724bc1)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classOperator_1ad12157211e348fef2dd17b6133724bc1}

#### `public int `[`SetDevice`](#classOperator_1a1f176cc41bbb083ff1093c6257e385c5)`(Device pDevice)` {#classOperator_1a1f176cc41bbb083ff1093c6257e385c5}

#### `public int `[`SetDeviceID`](#classOperator_1acb1289501c960cc9d1df70c70f97e40e)`(unsigned int idOfDevice)` {#classOperator_1acb1289501c960cc9d1df70c70f97e40e}

#### `public int `[`SetIsTensorholder`](#classOperator_1a06bd203382508c442b475c155c716977)`(int pIsParameter)` {#classOperator_1a06bd203382508c442b475c155c716977}

#### `public int `[`SetIsTrainable`](#classOperator_1ab7944e858af96f1cecad24b323d26e82)`(int pIsTrainable)` {#classOperator_1ab7944e858af96f1cecad24b323d26e82}

#### `public virtual int `[`SetModeTrain`](#classOperator_1a4824e1608881401f8d14a96c9e1c4438)`()` {#classOperator_1a4824e1608881401f8d14a96c9e1c4438}

#### `public virtual int `[`SetModeAccumulate`](#classOperator_1a142ad78819c1ecf4c49953e33119c8e6)`()` {#classOperator_1a142ad78819c1ecf4c49953e33119c8e6}

#### `public virtual int `[`SetModeInference`](#classOperator_1ad81f3e8a1656100cbc4d79954957c29d)`()` {#classOperator_1ad81f3e8a1656100cbc4d79954957c29d}

#### `public virtual `[`Operator`](#classOperator)`< DTYPE > ** `[`GetOutput`](#classOperator_1ad7be1cef2f71adcb0c22dc6f051cd445)`()` {#classOperator_1ad7be1cef2f71adcb0c22dc6f051cd445}

#### `public virtual `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetOutputContainer`](#classOperator_1a2aaef42413eba0597b3566f15f3c0b30)`()` {#classOperator_1a2aaef42413eba0597b3566f15f3c0b30}

#### `public virtual `[`Operator`](#classOperator)`< DTYPE > ** `[`GetInput`](#classOperator_1a42d8adb079719054278d20b080c427db)`()` {#classOperator_1a42d8adb079719054278d20b080c427db}

#### `public virtual `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetInputContainer`](#classOperator_1a7b3fea224107fbd9afbef5df03163caa)`()` {#classOperator_1a7b3fea224107fbd9afbef5df03163caa}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetResult`](#classOperator_1adecf0400d0808f396df03409da96a7f1)`() const` {#classOperator_1adecf0400d0808f396df03409da96a7f1}

#### `public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetResultContainer`](#classOperator_1a9abbb587f199f755336dca416578cf6b)`()` {#classOperator_1a9abbb587f199f755336dca416578cf6b}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetGradient`](#classOperator_1a4851981c3868c8b9755dc5e9294964a0)`() const` {#classOperator_1a4851981c3868c8b9755dc5e9294964a0}

#### `public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetGradientContainer`](#classOperator_1a56728499112d7d5c7ac46be21d443bd7)`()` {#classOperator_1a56728499112d7d5c7ac46be21d443bd7}

#### `public virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`GetDelta`](#classOperator_1aa73e50f59bb10fa2ddd16f19ba746570)`() const` {#classOperator_1aa73e50f59bb10fa2ddd16f19ba746570}

#### `public virtual `[`Container](#classContainer)< [Tensor`](#classTensor)`< DTYPE > * > * `[`GetDeltaContainer`](#classOperator_1ab45d910fd0780a845516acbbb336ddc7)`()` {#classOperator_1ab45d910fd0780a845516acbbb336ddc7}

#### `public std::string `[`GetName`](#classOperator_1a8d4325a95bcc43efc8f0b61f013afe89)`() const` {#classOperator_1a8d4325a95bcc43efc8f0b61f013afe89}

#### `public virtual Device `[`GetDevice`](#classOperator_1afba23ac8b7ef98da83a8d32b34a183df)`()` {#classOperator_1afba23ac8b7ef98da83a8d32b34a183df}

#### `public virtual int `[`GetDeviceID`](#classOperator_1aa2450a0e0dc58a850c80003c3f38cd71)`()` {#classOperator_1aa2450a0e0dc58a850c80003c3f38cd71}

#### `public int `[`GetIsTensorholder`](#classOperator_1a790df61eaa66bcbdbfd5938848940ec9)`()` {#classOperator_1a790df61eaa66bcbdbfd5938848940ec9}

#### `public int `[`GetIsTrainable`](#classOperator_1a5d0c55b1780c3d9cfcbcc1b5e6e0460e)`()` {#classOperator_1a5d0c55b1780c3d9cfcbcc1b5e6e0460e}

#### `public virtual int `[`ForwardPropagate`](#classOperator_1a6a409fc71926fcc9839ad24fecf58a9a)`(int pTime)` {#classOperator_1a6a409fc71926fcc9839ad24fecf58a9a}

#### `public virtual int `[`BackPropagate`](#classOperator_1a6d587c2552338a90a7f59767bdbfef44)`(int pTime)` {#classOperator_1a6d587c2552338a90a7f59767bdbfef44}

#### `public virtual int `[`ResetResult`](#classOperator_1a5c980663d286c420e502450d5fc84867)`()` {#classOperator_1a5c980663d286c420e502450d5fc84867}

#### `public virtual int `[`ResetGradient`](#classOperator_1a953a44849b76004f8e9e0ae76a4ed57a)`()` {#classOperator_1a953a44849b76004f8e9e0ae76a4ed57a}

#### `public virtual void `[`PrintInformation`](#classOperator_1a9ea8ed916722bc4bfbc8f765d62f3585)`(int level)` {#classOperator_1a9ea8ed916722bc4bfbc8f765d62f3585}

#### `public virtual void `[`SetDeviceCPU`](#classOperator_1ae322cf78613b9c3c1b72dcbf133e6157)`()` {#classOperator_1ae322cf78613b9c3c1b72dcbf133e6157}

#### `public virtual int `[`SetResultOnCPU`](#classOperator_1a3a96036162c9c4e5af2c214793237ade)`()` {#classOperator_1a3a96036162c9c4e5af2c214793237ade}

#### `public virtual int `[`SetGradientOnCPU`](#classOperator_1a58a436df26798b574dbb52065c226505)`()` {#classOperator_1a58a436df26798b574dbb52065c226505}

#### `public virtual int `[`Save`](#classOperator_1a7b06ca1781b552310dd8e05bd4afa369)`(char * nameOfFile)` {#classOperator_1a7b06ca1781b552310dd8e05bd4afa369}

#### `public virtual int `[`Load`](#classOperator_1a241885dbc7d5e5b35e2106ef9bbed53c)`(char * nameOfFile)` {#classOperator_1a241885dbc7d5e5b35e2106ef9bbed53c}

#### `public virtual int `[`Load`](#classOperator_1a16d495a83c27bad4aeacd6ce4569a8f7)`(FILE * fp)` {#classOperator_1a16d495a83c27bad4aeacd6ce4569a8f7}

#### `public virtual int `[`Save`](#classOperator_1afd997818c44df1bdf94385cc1611d0e7)`(FILE * fp)` {#classOperator_1afd997818c44df1bdf94385cc1611d0e7}

# class `Optimizer` {#classOptimizer}

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`Optimizer`](#classOptimizer_1aceb51b5bd9ed8a62dbc89c224402fe9a)`(`[`Operator`](#classOperator)`< DTYPE > ** pParameters,float pLearningRate,OptimizeDirection pOptimizeDirection)` | 
`public  `[`Optimizer`](#classOptimizer_1a0faabf351dc7d77fa7697fbe44926fb8)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,OptimizeDirection pOptimizeDirection)` | [Optimizer](#classOptimizer) 클래스 생성자
`public  `[`Optimizer`](#classOptimizer_1a805b3b65ce443424374a2afc83000bd0)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,float pWeightDecayRate,OptimizeDirection pOptimizeDirection)` | [Optimizer](#classOptimizer) 클래스 생성자
`public virtual  `[`~Optimizer`](#classOptimizer_1a83af99102cb516cf496aafbfea9c09cb)`()` | [Optimizer](#classOptimizer) 클래스 소멸자
`public int `[`Alloc`](#classOptimizer_1ada0841fe22979c1e14c265e06439e152)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,OptimizeDirection pOptimizeDirection)` | [Optimizer](#classOptimizer) 클래스의 멤버 변수들에 값을 할당하는 메소드
`public int `[`Alloc`](#classOptimizer_1a8d49956747bcf80e7bfd5a3a75539f6d)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,float pWeightDecayRate,OptimizeDirection pOptimizeDirection)` | [Optimizer](#classOptimizer) 클래스의 멤버 변수들에 값을 할당하는 메소드
`public int `[`Delete`](#classOptimizer_1a9231bd83ca0e7d78c20dd93621aedd96)`()` | 
`public virtual int `[`UpdateParameter`](#classOptimizer_1a5a989eee4fa18a9b4ee81b1b9bac2814)`()` | Trainable [Tensor](#classTensor) Container의 Operator들의 파라미터들을 순서대로 업데이트하는 메소드
`public int `[`UpdateParameter`](#classOptimizer_1ad76af45ccec70ffc2668f477b3ecc42e)`(`[`Operator`](#classOperator)`< DTYPE > * pTrainableTensor)` | 
`public void `[`SetLearningRate`](#classOptimizer_1a9d5d625eb42a27951b98757364e3f6b9)`(float pLearningRate)` | 
`public void `[`SetTrainableTensorDegree`](#classOptimizer_1a63213e3d65db1a88782afa122cc9fba5)`(int pTrainableTensorDegree)` | 
`public void `[`SetWeightDecayRate`](#classOptimizer_1aae30446ea6b1c7367d213ac5b868f6ba)`(int pWeightDecayRate)` | 
`public float `[`GetLearningRate`](#classOptimizer_1ad9387dd121ed55a119e98242359aa2f8)`() const` | 
`public int `[`GetOptimizeDirection`](#classOptimizer_1a993c37ff4e3e3bd572c9cf2f41d7a562)`() const` | 
`public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetTrainableTensor`](#classOptimizer_1a8aaa2dcbe9a5897a4817f14a3583d7f8)`()` | 
`public int `[`GetTrainableTensorDegree`](#classOptimizer_1a9ce341664492509a90ba11b335d4cebe)`() const` | 
`public float `[`GetWeightDecayRate`](#classOptimizer_1ac95806a3d3897f54cf1c3da8525db2e9)`() const` | 
`public int `[`ResetParameterGradient`](#classOptimizer_1a6afc4f5bf1b0da229aafeefe5ae2bb12)`()` | Trainable [Tensor](#classTensor) Container의 Operator들의 Gradient를 초기화하는 메소드

## Members

#### `public  `[`Optimizer`](#classOptimizer_1aceb51b5bd9ed8a62dbc89c224402fe9a)`(`[`Operator`](#classOperator)`< DTYPE > ** pParameters,float pLearningRate,OptimizeDirection pOptimizeDirection)` {#classOptimizer_1aceb51b5bd9ed8a62dbc89c224402fe9a}

#### `public  `[`Optimizer`](#classOptimizer_1a0faabf351dc7d77fa7697fbe44926fb8)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,OptimizeDirection pOptimizeDirection)` {#classOptimizer_1a0faabf351dc7d77fa7697fbe44926fb8}

[Optimizer](#classOptimizer) 클래스 생성자

멤버 변수들을 0 또는 NULL로 초기화하고,

전달받은 매개변수를 매개변수로 하여 Optimizer의 Alloc 메소드를 호출한다. 
#### Parameters
* `pParameters` [Optimizer](#classOptimizer) 클래스의 alloc 메소드의 파라미터로 전달할 Trainable [Tensor](#classTensor) container 

* `pLearningRate` [Optimizer](#classOptimizer) 클래스의 alloc 메소드의 파라미터로 전달할 learning Rate 

* `pOptimizeDirection` [Optimizer](#classOptimizer) 클래스의 alloc 메소드의 파라미터로 전달할 optimize Direction 

#### Returns
없음 

**See also**: [Optimizer<DTYPE>::Alloc(Container<Operator<DTYPE> *> *pParameters, float pLearningRate, OptimizeDirection pOptimizeDirection)](#classOptimizer_1ada0841fe22979c1e14c265e06439e152)

#### `public  `[`Optimizer`](#classOptimizer_1a805b3b65ce443424374a2afc83000bd0)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,float pWeightDecayRate,OptimizeDirection pOptimizeDirection)` {#classOptimizer_1a805b3b65ce443424374a2afc83000bd0}

[Optimizer](#classOptimizer) 클래스 생성자

멤버 변수들을 0 또는 NULL로 초기화하고,

전달받은 매개변수를 매개변수로 하여 Optimizer의 Alloc 메소드를 호출한다. 
#### Parameters
* `pParameters` [Optimizer](#classOptimizer) 클래스의 alloc 메소드의 파라미터로 전달할 Trainable [Tensor](#classTensor) container 

* `pLearningRate` [Optimizer](#classOptimizer) 클래스의 alloc 메소드의 파라미터로 전달할 learning Rate 

* `pWeightDecayRate` [Optimizer](#classOptimizer) 클래스의 alloc 메소드의 파라미터로 전달할 Weight Decay Rate 

* `pOptimizeDirection` [Optimizer](#classOptimizer) 클래스의 alloc 메소드의 파라미터로 전달할 optimize Direction 

#### Returns
없음 

**See also**: [Optimizer<DTYPE>::Alloc(Container<Operator<DTYPE> *> *pParameters, float pLearningRate, float pWeightDecayRate, OptimizeDirection pOptimizeDirection)](#classOptimizer_1a8d49956747bcf80e7bfd5a3a75539f6d)

#### `public virtual  `[`~Optimizer`](#classOptimizer_1a83af99102cb516cf496aafbfea9c09cb)`()` {#classOptimizer_1a83af99102cb516cf496aafbfea9c09cb}

[Optimizer](#classOptimizer) 클래스 소멸자

Optimizer<DTYPE>::Delete() 메소드를 호출하고 클래스를 소멸시킨다. 
#### Returns
없음

#### `public int `[`Alloc`](#classOptimizer_1ada0841fe22979c1e14c265e06439e152)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,OptimizeDirection pOptimizeDirection)` {#classOptimizer_1ada0841fe22979c1e14c265e06439e152}

[Optimizer](#classOptimizer) 클래스의 멤버 변수들에 값을 할당하는 메소드

매개변수로 전달 받은 값들을 각각 Trainable [Tensor](#classTensor) Conatiner, learning rate, Optimize Direction, Weight Decay Rate 멤버 변수에 할당한다. 
#### Parameters
* `pParameters` [Optimizer](#classOptimizer) 클래스에의 Trainable [Tensor](#classTensor) container 멤버 변수 

* `pLearningRate` [Optimizer](#classOptimizer) 클래스의 learning Rate 멤버 변수 

* `pOptimizeDirection` [Optimizer](#classOptimizer) 클래스의 optimize Direction 멤버 변수 

#### Returns
TRUE

#### `public int `[`Alloc`](#classOptimizer_1a8d49956747bcf80e7bfd5a3a75539f6d)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameters,float pLearningRate,float pWeightDecayRate,OptimizeDirection pOptimizeDirection)` {#classOptimizer_1a8d49956747bcf80e7bfd5a3a75539f6d}

[Optimizer](#classOptimizer) 클래스의 멤버 변수들에 값을 할당하는 메소드

매개변수로 전달 받은 값들을 각각 Trainable [Tensor](#classTensor) Conatiner, learning rate, Optimize Direction, Weight Decay Rate 멤버 변수에 할당한다. 
#### Parameters
* `pParameters` [Optimizer](#classOptimizer) 클래스에의 Trainable [Tensor](#classTensor) container 멤버 변수 

* `pLearningRate` [Optimizer](#classOptimizer) 클래스의 learning Rate 멤버 변수 

* `pWeightDecayRate` [Optimizer](#classOptimizer) 클래스의 Weight Decay Rate 멤버 변수 

* `pOptimizeDirection` [Optimizer](#classOptimizer) 클래스의 optimize Direction 멤버 변수 

#### Returns
TRUE

#### `public int `[`Delete`](#classOptimizer_1a9231bd83ca0e7d78c20dd93621aedd96)`()` {#classOptimizer_1a9231bd83ca0e7d78c20dd93621aedd96}

#### `public virtual int `[`UpdateParameter`](#classOptimizer_1a5a989eee4fa18a9b4ee81b1b9bac2814)`()` {#classOptimizer_1a5a989eee4fa18a9b4ee81b1b9bac2814}

Trainable [Tensor](#classTensor) Container의 Operator들의 파라미터들을 순서대로 업데이트하는 메소드

파생 클래스에서 오버라이드해서 사용하는 메소드 
#### Returns
TRUE

#### `public int `[`UpdateParameter`](#classOptimizer_1ad76af45ccec70ffc2668f477b3ecc42e)`(`[`Operator`](#classOperator)`< DTYPE > * pTrainableTensor)` {#classOptimizer_1ad76af45ccec70ffc2668f477b3ecc42e}

#### `public void `[`SetLearningRate`](#classOptimizer_1a9d5d625eb42a27951b98757364e3f6b9)`(float pLearningRate)` {#classOptimizer_1a9d5d625eb42a27951b98757364e3f6b9}

#### `public void `[`SetTrainableTensorDegree`](#classOptimizer_1a63213e3d65db1a88782afa122cc9fba5)`(int pTrainableTensorDegree)` {#classOptimizer_1a63213e3d65db1a88782afa122cc9fba5}

#### `public void `[`SetWeightDecayRate`](#classOptimizer_1aae30446ea6b1c7367d213ac5b868f6ba)`(int pWeightDecayRate)` {#classOptimizer_1aae30446ea6b1c7367d213ac5b868f6ba}

#### `public float `[`GetLearningRate`](#classOptimizer_1ad9387dd121ed55a119e98242359aa2f8)`() const` {#classOptimizer_1ad9387dd121ed55a119e98242359aa2f8}

#### `public int `[`GetOptimizeDirection`](#classOptimizer_1a993c37ff4e3e3bd572c9cf2f41d7a562)`() const` {#classOptimizer_1a993c37ff4e3e3bd572c9cf2f41d7a562}

#### `public `[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * `[`GetTrainableTensor`](#classOptimizer_1a8aaa2dcbe9a5897a4817f14a3583d7f8)`()` {#classOptimizer_1a8aaa2dcbe9a5897a4817f14a3583d7f8}

#### `public int `[`GetTrainableTensorDegree`](#classOptimizer_1a9ce341664492509a90ba11b335d4cebe)`() const` {#classOptimizer_1a9ce341664492509a90ba11b335d4cebe}

#### `public float `[`GetWeightDecayRate`](#classOptimizer_1ac95806a3d3897f54cf1c3da8525db2e9)`() const` {#classOptimizer_1ac95806a3d3897f54cf1c3da8525db2e9}

#### `public int `[`ResetParameterGradient`](#classOptimizer_1a6afc4f5bf1b0da229aafeefe5ae2bb12)`()` {#classOptimizer_1a6afc4f5bf1b0da229aafeefe5ae2bb12}

Trainable [Tensor](#classTensor) Container의 Operator들의 Gradient를 초기화하는 메소드

#### Returns
TRUE Operator<DTYPE>::ResetGradient()

# class `PRelu` {#classPRelu}

```
class PRelu
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`PRelu`](#classPRelu_1af1ed227113a7afffeed338913cdfcc86)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int pLoadflag)` | PRelu의 생성자.
`public inline  `[`PRelu`](#classPRelu_1af904bec278acd1c2cde8e0de5e830c74)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,std::string pName,int pLoadflag)` | PRelu의 생성자.
`public inline  `[`~PRelu`](#classPRelu_1aea861ee8bded154675345f7c92b1286d)`()` | LRelu의 소멸자.
`public inline int `[`Alloc`](#classPRelu_1ac58c97c1d86240738ee8add023ad8b63)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight)` | 파라미터로 받은 pinput으로부터 맴버 변수들을 초기화 한다.
`public inline void `[`Delete`](#classPRelu_1a98f94512a517db1016b77abbb5af7f86)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classPRelu_1ad14b9b7c039f16cac149b083c1fd091d)`(int pTime)` | PRelu의 ForwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classPRelu_1ac4bf8caf03e220deb028d81fb60de372)`(int pTime)` | PRelu의 BackPropagate매소드.

## Members

#### `public inline  `[`PRelu`](#classPRelu_1af1ed227113a7afffeed338913cdfcc86)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int pLoadflag)` {#classPRelu_1af1ed227113a7afffeed338913cdfcc86}

PRelu의 생성자.

파라미터로 받은 pInput, pWeight으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator)

* `pWeight` 입력값이 음수일 경우 사용하는 기울기 int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight)](#classPRelu_1ac58c97c1d86240738ee8add023ad8b63)

#### `public inline  `[`PRelu`](#classPRelu_1af904bec278acd1c2cde8e0de5e830c74)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,std::string pName,int pLoadflag)` {#classPRelu_1af904bec278acd1c2cde8e0de5e830c74}

PRelu의 생성자.

파라미터로 받은 pInput, pWeight으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator)

* `pWeight` 입력값이 음수일 경우 사용하는 기울기 

* `pName` Operator에 사용자가 부여한 이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight)](#classPRelu_1ac58c97c1d86240738ee8add023ad8b63)

#### `public inline  `[`~PRelu`](#classPRelu_1aea861ee8bded154675345f7c92b1286d)`()` {#classPRelu_1aea861ee8bded154675345f7c92b1286d}

LRelu의 소멸자.

**See also**: void Delete()

#### `public inline int `[`Alloc`](#classPRelu_1ac58c97c1d86240738ee8add023ad8b63)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight)` {#classPRelu_1ac58c97c1d86240738ee8add023ad8b63}

파라미터로 받은 pinput으로부터 맴버 변수들을 초기화 한다.

Result와 Gradient를 저장하기 위해 pInput의 Shape과 같은 dim을 갖는 Tensor를 생성한다. 
#### Parameters
* `pInput` 생성 할 Tensor의 Shape정보를 가진 [Operator](#classOperator)

* `pWeight` 입력값이 음수일 경우 사용하는 Tensor의 정보를 가진 [Operator](#classOperator)

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classPRelu_1a98f94512a517db1016b77abbb5af7f86)`()` {#classPRelu_1a98f94512a517db1016b77abbb5af7f86}

#### `public inline virtual int `[`ForwardPropagate`](#classPRelu_1ad14b9b7c039f16cac149b083c1fd091d)`(int pTime)` {#classPRelu_1ad14b9b7c039f16cac149b083c1fd091d}

PRelu의 ForwardPropagate 매소드.

input의 Tensor값들 중 0.f이상의 값은 그대로 result에 저장하고,

0.f미만의 값은 weight Tensor의 값과 곱한 후 저장한다. 
#### Parameters
* `pTime` pInput의 m_timesize값, default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classPRelu_1ac4bf8caf03e220deb028d81fb60de372)`(int pTime)` {#classPRelu_1ac4bf8caf03e220deb028d81fb60de372}

PRelu의 BackPropagate매소드.

input_delta는 result값이 0보다 클 경우 input_delta에 더하고,

0보다 작을 경우 input_delta에 weight을 곱한 후 더한다.

weight_delta는 result값이 0보다 클 경우 0에 더하고,

0보다 작을 경우 input_delta에 input을 곱한 후 더한다. 
#### Parameters
* `pTime` pInput의 m_timesize값, default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `ReconstructionError` {#classReconstructionError}

```
class ReconstructionError
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`ReconstructionError`](#classReconstructionError_1a42bb64ce990b27859ce8f3e5b96d627a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | 
`public inline virtual  `[`~ReconstructionError`](#classReconstructionError_1a47509ee05c71ffdd7c800fb0d201c06d)`()` | 
`public inline virtual int `[`Alloc`](#classReconstructionError_1a170ac27ced0bcdf8b914aa7a096c3fd2)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 
`public inline virtual int `[`ForwardPropagate`](#classReconstructionError_1a467a2f8d2f5c9b110962bb9e3e3e3bfd)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classReconstructionError_1a8bc001621b3e481734ad8c4628a664f1)`(int pTime)` | 

## Members

#### `public inline  `[`ReconstructionError`](#classReconstructionError_1a42bb64ce990b27859ce8f3e5b96d627a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classReconstructionError_1a42bb64ce990b27859ce8f3e5b96d627a}

#### `public inline virtual  `[`~ReconstructionError`](#classReconstructionError_1a47509ee05c71ffdd7c800fb0d201c06d)`()` {#classReconstructionError_1a47509ee05c71ffdd7c800fb0d201c06d}

#### `public inline virtual int `[`Alloc`](#classReconstructionError_1a170ac27ced0bcdf8b914aa7a096c3fd2)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classReconstructionError_1a170ac27ced0bcdf8b914aa7a096c3fd2}

#### `public inline virtual int `[`ForwardPropagate`](#classReconstructionError_1a467a2f8d2f5c9b110962bb9e3e3e3bfd)`(int pTime)` {#classReconstructionError_1a467a2f8d2f5c9b110962bb9e3e3e3bfd}

#### `public inline virtual int `[`BackPropagate`](#classReconstructionError_1a8bc001621b3e481734ad8c4628a664f1)`(int pTime)` {#classReconstructionError_1a8bc001621b3e481734ad8c4628a664f1}

# class `Recurrent` {#classRecurrent}

```
class Recurrent
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Recurrent`](#classRecurrent_1a3562481a571babfb398903433aef90a5)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeightXH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHY)` | 
`public inline  `[`Recurrent`](#classRecurrent_1af14bf54fb5aa314ddbfd60261835b586)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeightXH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHY,std::string pName)` | 
`public inline  `[`~Recurrent`](#classRecurrent_1acae26988a139a05841174c810c682961)`()` | 
`public inline int `[`Alloc`](#classRecurrent_1a59099f3fd92474384462c87539fa3605)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeightXH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHY)` | 
`public inline void `[`Delete`](#classRecurrent_1a1675e9d111d5b1320d9f15fda459135b)`()` | 
`public inline int `[`ForwardPropagate`](#classRecurrent_1ad5bdcf85fb28e8e8b64edab2a5da615f)`(int pTime,int pThreadNum)` | 
`public inline int `[`BackPropagate`](#classRecurrent_1a70db063ca6efe80e69af73cd67e0789c)`(int pTime,int pThreadNum)` | 

## Members

#### `public inline  `[`Recurrent`](#classRecurrent_1a3562481a571babfb398903433aef90a5)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeightXH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHY)` {#classRecurrent_1a3562481a571babfb398903433aef90a5}

#### `public inline  `[`Recurrent`](#classRecurrent_1af14bf54fb5aa314ddbfd60261835b586)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeightXH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHY,std::string pName)` {#classRecurrent_1af14bf54fb5aa314ddbfd60261835b586}

#### `public inline  `[`~Recurrent`](#classRecurrent_1acae26988a139a05841174c810c682961)`()` {#classRecurrent_1acae26988a139a05841174c810c682961}

#### `public inline int `[`Alloc`](#classRecurrent_1a59099f3fd92474384462c87539fa3605)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeightXH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHH,`[`Operator`](#classOperator)`< DTYPE > * pWeightHY)` {#classRecurrent_1a59099f3fd92474384462c87539fa3605}

#### `public inline void `[`Delete`](#classRecurrent_1a1675e9d111d5b1320d9f15fda459135b)`()` {#classRecurrent_1a1675e9d111d5b1320d9f15fda459135b}

#### `public inline int `[`ForwardPropagate`](#classRecurrent_1ad5bdcf85fb28e8e8b64edab2a5da615f)`(int pTime,int pThreadNum)` {#classRecurrent_1ad5bdcf85fb28e8e8b64edab2a5da615f}

#### `public inline int `[`BackPropagate`](#classRecurrent_1a70db063ca6efe80e69af73cd67e0789c)`(int pTime,int pThreadNum)` {#classRecurrent_1a70db063ca6efe80e69af73cd67e0789c}

# class `Relu` {#classRelu}

```
class Relu
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Relu`](#classRelu_1a4f35caa00fa86940cdc1a65933108418)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pLoadflag)` | Relu의 생성자.
`public inline  `[`Relu`](#classRelu_1a414112090cda5ec045e471f2d8b3af0a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` | Relu의 생성자.
`public inline  `[`~Relu`](#classRelu_1a6f3c23501b1755c4b97dd8f6873a975c)`()` | Relu의 소멸자.
`public inline int `[`Alloc`](#classRelu_1a65c4666084bb5bd929c6b7881ceb957c)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 파라미터로 받은 pinput으로부터 맴버 변수들을 초기화 한다.
`public inline void `[`Delete`](#classRelu_1a74e3682d6b222c36cf5f6f49668aae37)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classRelu_1aceeba8398158f592380232690e2e90ec)`(int pTime)` | Relu의 ForwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classRelu_1a7c41f1cf4e9cad9efb70fdbc9b6d7ea3)`(int pTime)` | Relu의 BackPropagate매소드.

## Members

#### `public inline  `[`Relu`](#classRelu_1a4f35caa00fa86940cdc1a65933108418)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pLoadflag)` {#classRelu_1a4f35caa00fa86940cdc1a65933108418}

Relu의 생성자.

파라미터로 받은 pInput으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator) int [Alloc(Operator<DTYPE> *pInput)](#classRelu_1a65c4666084bb5bd929c6b7881ceb957c)

#### `public inline  `[`Relu`](#classRelu_1a414112090cda5ec045e471f2d8b3af0a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` {#classRelu_1a414112090cda5ec045e471f2d8b3af0a}

Relu의 생성자.

파라미터로 받은 pInput으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator)

* `pName` Operator에 사용자가 부여한 이름. int [Alloc(Operator<DTYPE> *pInput)](#classRelu_1a65c4666084bb5bd929c6b7881ceb957c)

#### `public inline  `[`~Relu`](#classRelu_1a6f3c23501b1755c4b97dd8f6873a975c)`()` {#classRelu_1a6f3c23501b1755c4b97dd8f6873a975c}

Relu의 소멸자.

**See also**: void Delete()

#### `public inline int `[`Alloc`](#classRelu_1a65c4666084bb5bd929c6b7881ceb957c)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classRelu_1a65c4666084bb5bd929c6b7881ceb957c}

파라미터로 받은 pinput으로부터 맴버 변수들을 초기화 한다.

Result와 Gradient를 저장하기 위해 pInput의 Shape과 같은 dim을 갖는 Tensor를 생성한다. 
#### Parameters
* `pInput` 생성 할 Tensor의 Shape정보를 가진 [Operator](#classOperator)

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classRelu_1a74e3682d6b222c36cf5f6f49668aae37)`()` {#classRelu_1a74e3682d6b222c36cf5f6f49668aae37}

#### `public inline virtual int `[`ForwardPropagate`](#classRelu_1aceeba8398158f592380232690e2e90ec)`(int pTime)` {#classRelu_1aceeba8398158f592380232690e2e90ec}

Relu의 ForwardPropagate 매소드.

input의 Tensor값들 중 0.f이상의 값은 그대로 result에 저장하고, 0.f미만의 값은 0.f로 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classRelu_1a7c41f1cf4e9cad9efb70fdbc9b6d7ea3)`(int pTime)` {#classRelu_1a7c41f1cf4e9cad9efb70fdbc9b6d7ea3}

Relu의 BackPropagate매소드.

result값이 0보다 클 경우 input_delta에 더하고, 0보다 작을 경우 0.f를 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `ReShape` {#classReShape}

```
class ReShape
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`ReShape`](#classReShape_1a8889691defdc4983f9b41ca045d11365)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pRowSize,int pColSize,std::string pName,int pLoadflag)` | ReShape의 생성자
`public inline  `[`ReShape`](#classReShape_1aa3d007e81b3be85578554788bc95dd4b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pLoadflag)` | ReShape의 생성자
`public inline  `[`ReShape`](#classReShape_1af1b6f437bce0d7f39351f213d6dd4d50)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pLoadflag)` | ReShape의 생성자
`public inline  `[`ReShape`](#classReShape_1ac0a21e892c406fe07c36e35f082af659)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pLoadflag)` | ReShape의 생성자
`public inline  `[`~ReShape`](#classReShape_1a23509148e95c2172165783cd831bf494)`()` | ReShape의 소멸자.
`public inline int `[`Alloc`](#classReShape_1a2bfd17eb047885e116a164533744c82b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize)` | 파라미터로 받은 값들로 Shape의 dim들을 바꾼다.
`public inline void `[`Delete`](#classReShape_1ad24521b23a6fc48405711e0dc9e145b6)`()` | Delete 매소드.
`public inline virtual int `[`ForwardPropagate`](#classReShape_1a85b38b417b41399119460adbc6e9be40)`(int pTime)` | ReShape의 ForwardPropagate 매소드
`public inline virtual int `[`BackPropagate`](#classReShape_1a707731ef524b6abc57de318d56960558)`(int pTime)` | ReShape의 BackPropagate 매소드.

## Members

#### `public inline  `[`ReShape`](#classReShape_1a8889691defdc4983f9b41ca045d11365)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pRowSize,int pColSize,std::string pName,int pLoadflag)` {#classReShape_1a8889691defdc4983f9b41ca045d11365}

ReShape의 생성자

파라미터로 받은 pInput, pRowSize, pColSize으로 Alloc한다. 
#### Parameters
* `pInput` ReShape할 [Operator](#classOperator). 

* `pRowSize` ReShape으로 새로 만들어질 Tensor의 rowsize. 

* `pColSize` ReShape으로 새로 만들어질 Tensor의 colsize. @paramp pName 사용자가 부여한 Operator의 이름. int [Alloc(Operator<DTYPE> *pInput, int pTimeSize, int pBatchSize, int pChannelSize, int pRowSize, int pColSize)](#classReShape_1a2bfd17eb047885e116a164533744c82b)

#### `public inline  `[`ReShape`](#classReShape_1aa3d007e81b3be85578554788bc95dd4b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pLoadflag)` {#classReShape_1aa3d007e81b3be85578554788bc95dd4b}

ReShape의 생성자

파라미터로 받은 pInput, pRowSize, pColSize으로 Alloc한다. 
#### Parameters
* `pInput` ReShape할 [Operator](#classOperator). 

* `pChannelSize` ReShape으로 새로 만들어질 Tensor의 channelsize 

* `pRowSize` ReShape으로 새로 만들어질 Tensor의 rowsize. 

* `pColSize` ReShape으로 새로 만들어질 Tensor의 colsize. @paramp pName 사용자가 부여한 Operator의 이름. int [Alloc(Operator<DTYPE> *pInput, int pTimeSize, int pBatchSize, int pChannelSize, int pRowSize, int pColSize)](#classReShape_1a2bfd17eb047885e116a164533744c82b)

#### `public inline  `[`ReShape`](#classReShape_1af1b6f437bce0d7f39351f213d6dd4d50)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pLoadflag)` {#classReShape_1af1b6f437bce0d7f39351f213d6dd4d50}

ReShape의 생성자

파라미터로 받은 pInput, pRowSize, pColSize으로 Alloc한다. 
#### Parameters
* `pInput` ReShape할 [Operator](#classOperator). 

* `pBatchSize` ReShape으로 새로 만들어질 Tensor의 batchsize. 

* `pChannelSize` ReShape으로 새로 만들어질 Tensor의 channelsize. 

* `pRowSize` ReShape으로 새로 만들어질 Tensor의 rowsize. 

* `pColSize` ReShape으로 새로 만들어질 Tensor의 colsize. @paramp pName 사용자가 부여한 Operator의 이름. int [Alloc(Operator<DTYPE> *pInput, int pTimeSize, int pBatchSize, int pChannelSize, int pRowSize, int pColSize)](#classReShape_1a2bfd17eb047885e116a164533744c82b)

#### `public inline  `[`ReShape`](#classReShape_1ac0a21e892c406fe07c36e35f082af659)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pLoadflag)` {#classReShape_1ac0a21e892c406fe07c36e35f082af659}

ReShape의 생성자

파라미터로 받은 pInput, pRowSize, pColSize으로 Alloc한다. 
#### Parameters
* `pInput` ReShape할 [Operator](#classOperator). 

* `pTimeSize` ReShape으로 새로 만들어질 Tensor의 timesize. 

* `pBatchSize` ReShape으로 새로 만들어질 Tensor의 batchsize. 

* `pChannelSize` ReShape으로 새로 만들어질 Tensor의 channelsize. 

* `pRowSize` ReShape으로 새로 만들어질 Tensor의 rowsize. 

* `pColSize` ReShape으로 새로 만들어질 Tensor의 colsize. @paramp pName 사용자가 부여한 Operator의 이름. int [Alloc(Operator<DTYPE> *pInput, int pTimeSize, int pBatchSize, int pChannelSize, int pRowSize, int pColSize)](#classReShape_1a2bfd17eb047885e116a164533744c82b)

#### `public inline  `[`~ReShape`](#classReShape_1a23509148e95c2172165783cd831bf494)`()` {#classReShape_1a23509148e95c2172165783cd831bf494}

ReShape의 소멸자.

Delete 매소드를 사용한다. void [Delete()](#classReShape_1ad24521b23a6fc48405711e0dc9e145b6)

#### `public inline int `[`Alloc`](#classReShape_1a2bfd17eb047885e116a164533744c82b)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize)` {#classReShape_1a2bfd17eb047885e116a164533744c82b}

파라미터로 받은 값들로 Shape의 dim들을 바꾼다.

result에 파라미터로 받은 값들로 result의 shape을 바꾸어 넣고,

Delta도 마찬가지로 받은 Dimension 정보들로 새로운 Tensor를 생성하여 넣는다, 
#### Parameters
* `pInput` ReShape할 [Operator](#classOperator). 

* `pTimeSize` ReShape으로 새로 만들어질 Tensor의 timesize. 

* `pBatchSize` ReShape으로 새로 만들어질 Tensor의 batchsize. 

* `pChannelSize` ReShape으로 새로 만들어질 Tensor의 channelsize. 

* `pRowSize` ReShape으로 새로 만들어질 Tensor의 rowsize. 

* `pColSize` ReShape으로 새로 만들어질 Tensor의 colsize. 

#### Returns
성공 시 TRUE.

#### `public inline void `[`Delete`](#classReShape_1ad24521b23a6fc48405711e0dc9e145b6)`()` {#classReShape_1ad24521b23a6fc48405711e0dc9e145b6}

Delete 매소드.

별다른 기능은 없다.

#### `public inline virtual int `[`ForwardPropagate`](#classReShape_1a85b38b417b41399119460adbc6e9be40)`(int pTime)` {#classReShape_1a85b38b417b41399119460adbc6e9be40}

ReShape의 ForwardPropagate 매소드

input값을 result(새로운 Shape을 갖는 [Tensor](#classTensor))에 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classReShape_1a707731ef524b6abc57de318d56960558)`(int pTime)` {#classReShape_1a707731ef524b6abc57de318d56960558}

ReShape의 BackPropagate 매소드.

input_delta에 this_delta값을 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `RMSPropOptimizer` {#classRMSPropOptimizer}

```
class RMSPropOptimizer
  : public Optimizer< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`RMSPropOptimizer`](#classRMSPropOptimizer_1a4cdaa40c01f87df1c5836946fa441113)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float decay,float epsilon,bool centered,OptimizeDirection pOptimizeDirection)` | RMSPropOptmizer 생성자.
`public inline  `[`RMSPropOptimizer`](#classRMSPropOptimizer_1ac6abe48a03b007d65a8b960e92724433)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float decay,float epsilon,bool centered,float weightDecayRate,OptimizeDirection pOptimizeDirection)` | RMSPropOptmizer 생성자.
`public inline  `[`~RMSPropOptimizer`](#classRMSPropOptimizer_1aed19a3794af1602fb18279a0a6340440)`()` | RMSPropOpmitzer 소멸자
`public inline virtual void `[`Delete`](#classRMSPropOptimizer_1a64a80ea59e761895c33582baf4577dce)`()` | Optimizer의 Delete 매소드
`public inline int `[`Alloc`](#classRMSPropOptimizer_1a6aa8a7a4aa983f2187a537f9260c12be)`(float decay,float epsilon,bool centered)` | Optimizer의 Alloc 매소드
`public inline virtual int `[`UpdateParameter`](#classRMSPropOptimizer_1aa13c77558353eacbdfc3421bd4b460cd)`()` | 파라미터 값들을 업데이트 하는 메소드
`public inline virtual int `[`UpdateParameter`](#classRMSPropOptimizer_1aae96f574cf5bb4fca59f0c0bc8ff114c)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` | UpdateParameter default 함수
`public inline int `[`UpdateParameter`](#classRMSPropOptimizer_1a166ce01205a276ebfe7260d03d6c5a3c)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * m_pMeanSquared)` | 파라미터 값들을 업데이트 하는 메소드
`public inline int `[`UpdateParameter`](#classRMSPropOptimizer_1a1e9bcebf06655abf5380b83c36c89bf2)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * m_pMeanSquared,`[`Tensor`](#classTensor)`< DTYPE > * m_pMeanGrad)` | 파라미터 값들을 업데이트 하는 메소드

## Members

#### `public inline  `[`RMSPropOptimizer`](#classRMSPropOptimizer_1a4cdaa40c01f87df1c5836946fa441113)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float decay,float epsilon,bool centered,OptimizeDirection pOptimizeDirection)` {#classRMSPropOptimizer_1a4cdaa40c01f87df1c5836946fa441113}

RMSPropOptmizer 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pLearningRate` Optimizer의 learning rate 

* `decay` m_aaMeanSquared, m_pMeanGrad, m_aaMeanGrad, gradient 조정 가중치 값 

* `epsilon` 분모 값이 0이 되는 것을 방지 하는 값 

* `centered` cemtered version enable boolean 변수 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(decay, epsilon, centered)

#### `public inline  `[`RMSPropOptimizer`](#classRMSPropOptimizer_1ac6abe48a03b007d65a8b960e92724433)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,float decay,float epsilon,bool centered,float weightDecayRate,OptimizeDirection pOptimizeDirection)` {#classRMSPropOptimizer_1ac6abe48a03b007d65a8b960e92724433}

RMSPropOptmizer 생성자.

맴버변수들을 초기화하고 Alloc 매소드를 호출한다. 
#### Parameters
* `*pParameterContainer` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pLearningRate` Optimizer의 learning rate 

* `decay` m_aaMeanSquared, m_pMeanGrad, m_aaMeanGrad, gradient 조정 가중치 값 

* `epsilon` 분모 값이 0이 되는 것을 방지 하는 값 

* `weightDecayRate` 가중치 매개변수가 클 때 패널티를 부과하는 값 

* `pOptimizeDirection` Optimizing의 방향(MAXIMIZE or MINIMIZE) 

#### Returns
없음 

**See also**: int Alloc(decay, epsilon, centered)

#### `public inline  `[`~RMSPropOptimizer`](#classRMSPropOptimizer_1aed19a3794af1602fb18279a0a6340440)`()` {#classRMSPropOptimizer_1aed19a3794af1602fb18279a0a6340440}

RMSPropOpmitzer 소멸자

#### Returns
없음

#### `public inline virtual void `[`Delete`](#classRMSPropOptimizer_1a64a80ea59e761895c33582baf4577dce)`()` {#classRMSPropOptimizer_1a64a80ea59e761895c33582baf4577dce}

Optimizer의 Delete 매소드

맴버 변수 m_aaMeanSquared, m_aaMeanGrad의 메모리 할당을 해제한다. 
#### Returns
없음

#### `public inline int `[`Alloc`](#classRMSPropOptimizer_1a6aa8a7a4aa983f2187a537f9260c12be)`(float decay,float epsilon,bool centered)` {#classRMSPropOptimizer_1a6aa8a7a4aa983f2187a537f9260c12be}

Optimizer의 Alloc 매소드

맴버 변수 m_ppParameter, m_numOfParameter, m_aaMeanSquared, m_aaMeanGrad를 초기화한다.

m_aaMeanSquared를 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다.

m_aaMeanGrad를 m_ppParameter와 같은 Shape의 Tensor를 생성하여 넣는다. 
#### Parameters
* `decay` m_aaMeanSquared, m_pMeanGrad, m_aaMeanGrad, gradient 조정 가중치 값 

* `epsilon` Root Sqaure 값이 0이 되는 것을 방지 하는 값 

* `centered` cemtered version enable boolean 변수 

#### Returns
성공 시 TRUE 

**See also**: [Container](#classContainer)<[Operator<DTYPE>](#classOperator) *>* GetTrainableTensor() 

**See also**: int GetTrainableTensorDegree()

#### `public inline virtual int `[`UpdateParameter`](#classRMSPropOptimizer_1aa13c77558353eacbdfc3421bd4b460cd)`()` {#classRMSPropOptimizer_1aa13c77558353eacbdfc3421bd4b460cd}

파라미터 값들을 업데이트 하는 메소드

m_centered 유무에 따라 centered version 과 not use RMSProp UpdateParameter 호출 
#### Returns
성공 시 TRUE 

**See also**: int [UpdateParameter(Operator<DTYPE> *pParameter, Tensor<DTYPE> *m_pMeanSquared)](#classRMSPropOptimizer_1a166ce01205a276ebfe7260d03d6c5a3c)

**See also**: int [UpdateParameter(Operator<DTYPE> *pParameter, Tensor<DTYPE> *m_pMeanSquared, Tensor<DTYPE> *m_pMeanGrad)](#classRMSPropOptimizer_1a1e9bcebf06655abf5380b83c36c89bf2)

#### `public inline virtual int `[`UpdateParameter`](#classRMSPropOptimizer_1aae96f574cf5bb4fca59f0c0bc8ff114c)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter)` {#classRMSPropOptimizer_1aae96f574cf5bb4fca59f0c0bc8ff114c}

UpdateParameter default 함수

#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

#### Returns
성공 시 TRUE

#### `public inline int `[`UpdateParameter`](#classRMSPropOptimizer_1a166ce01205a276ebfe7260d03d6c5a3c)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * m_pMeanSquared)` {#classRMSPropOptimizer_1a166ce01205a276ebfe7260d03d6c5a3c}

파라미터 값들을 업데이트 하는 메소드

m_decay 가중치로 조정된 m_pMeanSquared, gradinet로 m_pMeanSquared 업데이트 한다.

업데이트 된 m_pMeanSquared로 지수평균 이동 공식을 적용하여 파라미터를 업데이트 한다. 
#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pMeanSquared` 업데이트 할 pMeanSquared 

#### Returns
성공 시 TURE

#### `public inline int `[`UpdateParameter`](#classRMSPropOptimizer_1a1e9bcebf06655abf5380b83c36c89bf2)`(`[`Operator`](#classOperator)`< DTYPE > * pParameter,`[`Tensor`](#classTensor)`< DTYPE > * m_pMeanSquared,`[`Tensor`](#classTensor)`< DTYPE > * m_pMeanGrad)` {#classRMSPropOptimizer_1a1e9bcebf06655abf5380b83c36c89bf2}

파라미터 값들을 업데이트 하는 메소드

m_decay 가중치로 조정된 gradient로 m_pMeanGrad를 업데이트한다.

m_decay 가중치로 조정된 m_pMeanSquared, gradinet로 m_pMeanSquared 업데이트 한다.

업데이트 된 m_pMeanSquared와 업데이트 된 m_pMeanGrad의 제곱의 차를 지수평균이동공식에 적용하여 파라미터를 업데이트 한다. 
#### Parameters
* `pParameter` 업데이트 할 Tensor를 가지고 있는 Operator포인터 

* `pMeanSquared` 업데이트 할 pMeanSquared 

* `pMeanGrad` 업데이트 할 pMeanGrad 

#### Returns
성공 시 TURE

# class `Sequential` {#classSequential}

```
class Sequential
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Sequential`](#classSequential_1acae5d700ca6c1ff7f235514b81ebffa3)`(int numOfOperator,...)` | 
`public inline  `[`~Sequential`](#classSequential_1a36fed062f234a7448dac6fe388dc09e5)`()` | 
`public inline int `[`Alloc`](#classSequential_1acde7e6f535cea4e323aed1646b5cdfa8)`(int numOfOperator,va_list * ap)` | 
`public inline int `[`ForwardPropagate`](#classSequential_1a94b9a0a9690d3eabdba4ce7e6dc9bf40)`()` | 
`public inline int `[`BackPropagate`](#classSequential_1a6857585bbadfa1175483341a56d72523)`()` | 

## Members

#### `public inline  `[`Sequential`](#classSequential_1acae5d700ca6c1ff7f235514b81ebffa3)`(int numOfOperator,...)` {#classSequential_1acae5d700ca6c1ff7f235514b81ebffa3}

#### `public inline  `[`~Sequential`](#classSequential_1a36fed062f234a7448dac6fe388dc09e5)`()` {#classSequential_1a36fed062f234a7448dac6fe388dc09e5}

#### `public inline int `[`Alloc`](#classSequential_1acde7e6f535cea4e323aed1646b5cdfa8)`(int numOfOperator,va_list * ap)` {#classSequential_1acde7e6f535cea4e323aed1646b5cdfa8}

#### `public inline int `[`ForwardPropagate`](#classSequential_1a94b9a0a9690d3eabdba4ce7e6dc9bf40)`()` {#classSequential_1a94b9a0a9690d3eabdba4ce7e6dc9bf40}

#### `public inline int `[`BackPropagate`](#classSequential_1a6857585bbadfa1175483341a56d72523)`()` {#classSequential_1a6857585bbadfa1175483341a56d72523}

# class `Shape` {#classShape}

정보를 담고 있는 Shape을 저장하고 관리하는 클래스

Tensor의 차원 정보를 담고 있는 Shape을 저장하고 관리하는 클래스

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`Shape`](#classShape_1a2a7cd5aaf62c49a15140e8fc042d68a2)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4)` | 5D-Shape 생성자
`public  `[`Shape`](#classShape_1ab33a5234bbfa48f9fdd050f85602b093)`(int pSize0,int pSize1,int pSize2,int pSize3)` | 4D-Shape 생성자
`public  `[`Shape`](#classShape_1aa8720e80e9c9624a33a1a16ce9e559b6)`(int pSize0,int pSize1,int pSize2)` | 3D-Shape 생성자
`public  `[`Shape`](#classShape_1a4816b3286c1d5150aaafdacc56c2df33)`(int pSize0,int pSize1)` | 2D-Shape 생성자
`public  `[`Shape`](#classShape_1a66339a1e7618d1a27ad04bb216a1683b)`(int pSize0)` | 1D-Shape 생성자
`public  `[`Shape`](#classShape_1a482c2a9c1b71e8229dea5052b94fdcf8)`(`[`Shape`](#classShape)` * pShape)` | [Shape](#classShape) 클래스를 매개변수로 받아 깊은 복사(Deep Copy)하는 [Shape](#classShape) 생성자
`public virtual  `[`~Shape`](#classShape_1a935afc9e576015f967d90de56977167d)`()` | [Shape](#classShape) 클래스 소멸자
`public int `[`GetRank`](#classShape_1a93bc73b3237c0398c302b9014f5727aa)`()` | [Shape](#classShape) 클래스의 Rank 멤버 변수를 반환하는 메소드
`public int `[`GetDim`](#classShape_1a5418dc21436c259b6d715a42f4455315)`(int pRanknum)` | Rank 인덱스를 파라미터로 받아 Dimension을 반환하는 메소드
`public int & `[`operator[]`](#classShape_1afb2f25c23fa4217c06bdc0ebc022d647)`(int pRanknum)` | []연산자 오버로딩
`public Device `[`GetDevice`](#classShape_1ad3bf16f5fdf16e37694e882dcd800da3)`()` | [Shape](#classShape) 클래스의 Device 멤버 변수를 반환하는 메소드
`public int `[`GetDeviceID`](#classShape_1a9dae5e077c70b9b4d89626a0cea57929)`()` | [Shape](#classShape) 클래스의 idOfDevice 멤버 변수를 반환하는 메소드
`public int `[`ReShape`](#classShape_1aa6aba3540be5482aeaebff24636727e0)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4)` | 새로운 Shape을 만들어 반환 하는 메소드.
`public int `[`ReShape`](#classShape_1ac33a6b0013bd8e66b86a61e03cc131ce)`(int pRank,...)` | [Shape](#classShape) 각 축의 Dimension정보를 초기화 하는 메소드.
`public int `[`SetDeviceCPU`](#classShape_1a053362e2b59b2965bdcb765d9158003c)`()` | [Shape](#classShape) 클래스의 Device 멤버 변수를 CPU로 변경한다.

## Members

#### `public  `[`Shape`](#classShape_1a2a7cd5aaf62c49a15140e8fc042d68a2)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4)` {#classShape_1a2a7cd5aaf62c49a15140e8fc042d68a2}

5D-Shape 생성자

5개의 축의 Dimension을 매개변수로 받아 [Shape](#classShape) 클래스를 생성하는 생성자 
#### Parameters
* `pSize0` 첫 번째 축의 Dimension 크기 

* `pSize1` 두 번째 축의 Dimension 크기 

* `pSize2` 세 번째 축의 Dimension 크기 

* `pSize3` 네 번째 축의 Dimension 크기 

* `pSize4` 다섯 번째 축의 Dimension 크기 

#### Returns
없음 

**See also**: Shape::Alloc(int pRank, ...)

#### `public  `[`Shape`](#classShape_1ab33a5234bbfa48f9fdd050f85602b093)`(int pSize0,int pSize1,int pSize2,int pSize3)` {#classShape_1ab33a5234bbfa48f9fdd050f85602b093}

4D-Shape 생성자

4개의 축의 Dimension을 매개변수로 받아 [Shape](#classShape) 클래스를 생성하는 생성자 
#### Parameters
* `pSize0` 첫 번째 축의 Dimension 크기 

* `pSize1` 두 번째 축의 Dimension 크기 

* `pSize2` 세 번째 축의 Dimension 크기 

* `pSize3` 네 번째 축의 Dimension 크기 

**See also**: Shape::Alloc(int pRank, ...) 

#### Returns
없음

#### `public  `[`Shape`](#classShape_1aa8720e80e9c9624a33a1a16ce9e559b6)`(int pSize0,int pSize1,int pSize2)` {#classShape_1aa8720e80e9c9624a33a1a16ce9e559b6}

3D-Shape 생성자

3개의 축의 Dimension을 매개변수로 받아 [Shape](#classShape) 클래스를 생성하는 생성자 
#### Parameters
* `pSize0` 첫 번째 축의 Dimension 크기 

* `pSize1` 두 번째 축의 Dimension 크기 

* `pSize2` 세 번째 축의 Dimension 크기 

**See also**: Shape::Alloc(int pRank, ...) 

#### Returns
없음

#### `public  `[`Shape`](#classShape_1a4816b3286c1d5150aaafdacc56c2df33)`(int pSize0,int pSize1)` {#classShape_1a4816b3286c1d5150aaafdacc56c2df33}

2D-Shape 생성자

2개의 축의 Dimension을 매개변수로 받아 [Shape](#classShape) 클래스를 생성하는 생성자 
#### Parameters
* `pSize0` 첫 번째 축의 Dimension 크기 

* `pSize1` 두 번째 축의 Dimension 크기 

#### Returns
없음 

**See also**: Shape::Alloc(int pRank, ...)

#### `public  `[`Shape`](#classShape_1a66339a1e7618d1a27ad04bb216a1683b)`(int pSize0)` {#classShape_1a66339a1e7618d1a27ad04bb216a1683b}

1D-Shape 생성자

1개의 축의 Dimension을 매개변수로 받아 [Shape](#classShape) 클래스를 생성하는 생성자 
#### Parameters
* `pSize0` 첫 번째 축의 Dimension 크기 

#### Returns
없음 

**See also**: Shape::Alloc(int pRank, ...)

#### `public  `[`Shape`](#classShape_1a482c2a9c1b71e8229dea5052b94fdcf8)`(`[`Shape`](#classShape)` * pShape)` {#classShape_1a482c2a9c1b71e8229dea5052b94fdcf8}

[Shape](#classShape) 클래스를 매개변수로 받아 깊은 복사(Deep Copy)하는 [Shape](#classShape) 생성자

#### Parameters
* `pShape` 깊은 복사(Deep Copy)의 대상이 되는 [Shape](#classShape) 클래스 

#### Returns
없음 

**See also**: Shape::Alloc(Shape *pShape)

#### `public virtual  `[`~Shape`](#classShape_1a935afc9e576015f967d90de56977167d)`()` {#classShape_1a935afc9e576015f967d90de56977167d}

[Shape](#classShape) 클래스 소멸자

해당 [Shape](#classShape) 클래스를 위해 동적으로 할당된 메모리 공간을 반환하고 클래스를 소멸한다. 
#### Returns
없음 

**See also**: Shape::Delete()

#### `public int `[`GetRank`](#classShape_1a93bc73b3237c0398c302b9014f5727aa)`()` {#classShape_1a93bc73b3237c0398c302b9014f5727aa}

[Shape](#classShape) 클래스의 Rank 멤버 변수를 반환하는 메소드

#### Returns
m_Rank

#### `public int `[`GetDim`](#classShape_1a5418dc21436c259b6d715a42f4455315)`(int pRanknum)` {#classShape_1a5418dc21436c259b6d715a42f4455315}

Rank 인덱스를 파라미터로 받아 Dimension을 반환하는 메소드

#### Parameters
* `pRanknum` Dimension을 반환하고자 하는 축의 번호 

#### Returns
성공 시 m_aDim[pRanknum], 실패 시 예외 처리

#### `public int & `[`operator[]`](#classShape_1afb2f25c23fa4217c06bdc0ebc022d647)`(int pRanknum)` {#classShape_1afb2f25c23fa4217c06bdc0ebc022d647}

[]연산자 오버로딩

Rank 인덱스를 파라미터로 받아 Dimension을 반환하는 메소드 
#### Parameters
* `pRanknum` Dimension을 반환하고자 하는 축의 번호 

#### Returns
성공 시 m_aDim[pRanknum], 실패 시 예외 처리

#### `public Device `[`GetDevice`](#classShape_1ad3bf16f5fdf16e37694e882dcd800da3)`()` {#classShape_1ad3bf16f5fdf16e37694e882dcd800da3}

[Shape](#classShape) 클래스의 Device 멤버 변수를 반환하는 메소드

#### Returns
m_Device

#### `public int `[`GetDeviceID`](#classShape_1a9dae5e077c70b9b4d89626a0cea57929)`()` {#classShape_1a9dae5e077c70b9b4d89626a0cea57929}

[Shape](#classShape) 클래스의 idOfDevice 멤버 변수를 반환하는 메소드

#### Returns
m_idOfDevice

#### `public int `[`ReShape`](#classShape_1aa6aba3540be5482aeaebff24636727e0)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4)` {#classShape_1aa6aba3540be5482aeaebff24636727e0}

새로운 Shape을 만들어 반환 하는 메소드.

파마미터로 전달받은 각 축의 Dimension정보를 바탕으로 새로운 Shape을 생성하여 반환한다. 
#### Parameters
* `pSize0` Time의 Dimension 

* `pSize1` Batch의 Dimension 

* `pSize2` Channel의 Dimension 

* `pSize3` Row의 Dimension 

* `pSize4` Column의 Dimension 

#### Returns
파라미터 정보를 바탕으로 만든 [Shape](#classShape)

#### `public int `[`ReShape`](#classShape_1ac33a6b0013bd8e66b86a61e03cc131ce)`(int pRank,...)` {#classShape_1ac33a6b0013bd8e66b86a61e03cc131ce}

[Shape](#classShape) 각 축의 Dimension정보를 초기화 하는 메소드.

파마미터로 전달받은 각 축의 Dimension정보를 m_aDim에 저장한다. 
#### Parameters
* `pRank` Shape을 이루는 축의 갯수를 나타내는 변수. 

* `...` 각 축의 Dimension정보를 가지고 있는 가변인자. 

#### Returns
성공 시 TRUE

#### `public int `[`SetDeviceCPU`](#classShape_1a053362e2b59b2965bdcb765d9158003c)`()` {#classShape_1a053362e2b59b2965bdcb765d9158003c}

[Shape](#classShape) 클래스의 Device 멤버 변수를 CPU로 변경한다.

#### Returns
TRUE

# class `Sigmoid` {#classSigmoid}

```
class Sigmoid
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Sigmoid`](#classSigmoid_1a30edeafdf59c9729cec91dda2f40611e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` | Sigmoid의 생성자.
`public inline  `[`~Sigmoid`](#classSigmoid_1ac70e7aad5d73fbf3ba4c30490f388fda)`()` | Sigmoid의 소멸자.
`public inline int `[`Alloc`](#classSigmoid_1a7f6383b1af4f0d422fcd4a320a94f211)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 파라미터로 받은 pInput으로부터 맴버 변수들을 초기화 한다.
`public inline virtual int `[`ForwardPropagate`](#classSigmoid_1a5878f3b62b3c79e001192c186b7cfbec)`(int pTime)` | Sigmoid의 ForwardPropagate 매소드.
`public inline virtual int `[`BackPropagate`](#classSigmoid_1aab45c095325c1a08c0433d071acee4fc)`(int pTime)` | SIGMOID의 BackPropagate 매소드.
`public inline DTYPE `[`SIGMOID`](#classSigmoid_1aa4c668309336cef433d98b56abd3cda7)`(DTYPE data)` | SIGMOID 함수

## Members

#### `public inline  `[`Sigmoid`](#classSigmoid_1a30edeafdf59c9729cec91dda2f40611e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` {#classSigmoid_1a30edeafdf59c9729cec91dda2f40611e}

Sigmoid의 생성자.

파라미터로 받은 pInput으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator)

* `pName` Operator에 사용자가 부여한 이름. int [Alloc(Operator<DTYPE> *pInput)](#classSigmoid_1a7f6383b1af4f0d422fcd4a320a94f211)

#### `public inline  `[`~Sigmoid`](#classSigmoid_1ac70e7aad5d73fbf3ba4c30490f388fda)`()` {#classSigmoid_1ac70e7aad5d73fbf3ba4c30490f388fda}

Sigmoid의 소멸자.

#### `public inline int `[`Alloc`](#classSigmoid_1a7f6383b1af4f0d422fcd4a320a94f211)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classSigmoid_1a7f6383b1af4f0d422fcd4a320a94f211}

파라미터로 받은 pInput으로부터 맴버 변수들을 초기화 한다.

Result와 Gradient를 저장하기 위해 pInput의 Shape과 같은 dim을 갖는 Tensor를 생성한다. 
#### Parameters
* `pInput` 생성 할 Tensor의 Shape정보를 가진 [Operator](#classOperator)

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`ForwardPropagate`](#classSigmoid_1a5878f3b62b3c79e001192c186b7cfbec)`(int pTime)` {#classSigmoid_1a5878f3b62b3c79e001192c186b7cfbec}

Sigmoid의 ForwardPropagate 매소드.

input의 Tensor값들을 SIGMOID값을 취한 뒤 result에 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classSigmoid_1aab45c095325c1a08c0433d071acee4fc)`(int pTime)` {#classSigmoid_1aab45c095325c1a08c0433d071acee4fc}

SIGMOID의 BackPropagate 매소드.

result값으로 [Sigmoid](#classSigmoid) 미분 값을 계산하여 input_delta에 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline DTYPE `[`SIGMOID`](#classSigmoid_1aa4c668309336cef433d98b56abd3cda7)`(DTYPE data)` {#classSigmoid_1aa4c668309336cef433d98b56abd3cda7}

SIGMOID 함수

1.0/(1.0 + e^(-x)) 
#### Parameters
* `data` SIGMOID할 값 

#### Returns
data를 SIGMOID함수에 넣은 결과 값.

# class `Softmax` {#classSoftmax}

```
class Softmax
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Softmax`](#classSoftmax_1ab07477db41c81b4febd7cc7604c372a5)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon,int pLoadflag)` | Softmax의 생성자.
`public inline  `[`Softmax`](#classSoftmax_1a39d599cd7ecaa03d09435edba3077599)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,std::string pName,int pLoadflag)` | Softmax의 생성자.
`public inline  `[`Softmax`](#classSoftmax_1ae0a60d30946abed3d4147f24cebdee7e)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon,std::string pName,int pLoadflag)` | Softmax의 생성자.
`public inline  `[`~Softmax`](#classSoftmax_1a27d3ea98ca2e94214233277c6d256fb0)`()` | Softmax의 소멸자.
`public inline virtual int `[`Alloc`](#classSoftmax_1afe768ac9d4ccd2c9b21a36fe2c0a055e)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` | 파라미터로 받은 pOperator로 맴버변수들을 초기화 하고 Result, Gradient를 설정한다.
`public inline virtual void `[`Delete`](#classSoftmax_1accb5963f9a8216d02c3d58d008897eaa)`()` | Alloc매소드에서 할당했던 sum, max를 삭제하고 포인터를 NULL로 초기화 한다.
`public inline virtual int `[`ForwardPropagate`](#classSoftmax_1addd20110453a6d0c5fefbb6f336d34ef)`(int pTime)` | Softmax의 ForwardPropagate 매소드
`public inline virtual int `[`BackPropagate`](#classSoftmax_1a397299ec79b62770e6696996be661f41)`(int pTime)` | softmax의 BackPropagate 매소드.
`public inline DTYPE `[`Max`](#classSoftmax_1a575f0dfcdf281af95c020b03b6ee4fb7)`(`[`Tensor`](#classTensor)`< DTYPE > * input,int start,int end)` | 파라미터로 받은 Tensor에서 가장 큰 값을 반환하는 함수.

## Members

#### `public inline  `[`Softmax`](#classSoftmax_1ab07477db41c81b4febd7cc7604c372a5)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon,int pLoadflag)` {#classSoftmax_1ab07477db41c81b4febd7cc7604c372a5}

Softmax의 생성자.

파라미터로 받은 pOperator, epsilon을 Alloc시킨다. 
#### Parameters
* `pOperator` Softmax할 대상 [Operator](#classOperator), 이 매소드에서 Alloc시킨다. 

* `epsilon` ForwardPropagate에 사용힐 값. 0으로 나누어지는 것을 방지하는 역할을 한다. virtual int Alloc([Operator<DTYPE>](#classOperator) *pOperator, DTYPE epsilon = 1e-6f

#### `public inline  `[`Softmax`](#classSoftmax_1a39d599cd7ecaa03d09435edba3077599)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,std::string pName,int pLoadflag)` {#classSoftmax_1a39d599cd7ecaa03d09435edba3077599}

Softmax의 생성자.

파라미터로 받은 pOperator을 Alloc한다. 
#### Parameters
* `pOperator` Softmax할 대상 [Operator](#classOperator), 이 매소드에서 Alloc시킨다. 

* `pName` 사용자가 Operator에 부여한 이름. virtual int Alloc([Operator<DTYPE>](#classOperator) *pOperator, DTYPE epsilon = 1e-6f

#### `public inline  `[`Softmax`](#classSoftmax_1ae0a60d30946abed3d4147f24cebdee7e)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon,std::string pName,int pLoadflag)` {#classSoftmax_1ae0a60d30946abed3d4147f24cebdee7e}

Softmax의 생성자.

파라미터로 받은 pOperator, epsilon을 Alloc시킨다. 
#### Parameters
* `pOperator` Softmax할 대상 [Operator](#classOperator), 이 매소드에서 Alloc시킨다. @prram epsilon ForwardPropagate에 사용힐 값. 0으로 나누어지는 것을 방지하는 역할을 한다. 

* `pName` 사용자가 Operator에 부여한 이름. virtual int Alloc([Operator<DTYPE>](#classOperator) *pOperator, DTYPE epsilon = 1e-6f

#### `public inline  `[`~Softmax`](#classSoftmax_1a27d3ea98ca2e94214233277c6d256fb0)`()` {#classSoftmax_1a27d3ea98ca2e94214233277c6d256fb0}

Softmax의 소멸자.

#### `public inline virtual int `[`Alloc`](#classSoftmax_1afe768ac9d4ccd2c9b21a36fe2c0a055e)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` {#classSoftmax_1afe768ac9d4ccd2c9b21a36fe2c0a055e}

파라미터로 받은 pOperator로 맴버변수들을 초기화 하고 Result, Gradient를 설정한다.

input으로 받은 Operator의 Shape정보들로 맴버 변수드을 초기화 하고, 같은 Shape을 갖는 Tensor를 만들어 Result와 Gradient로 설정한다. 
#### Parameters
* `pOperator` Softmax할 Operator들 

* `epsilon` 0으로 나누어지는 것을 방지하기위해 softmax식의 분모에 더하는 값. 

#### Returns
성공 시 TRUE.

#### `public inline virtual void `[`Delete`](#classSoftmax_1accb5963f9a8216d02c3d58d008897eaa)`()` {#classSoftmax_1accb5963f9a8216d02c3d58d008897eaa}

Alloc매소드에서 할당했던 sum, max를 삭제하고 포인터를 NULL로 초기화 한다.

#### `public inline virtual int `[`ForwardPropagate`](#classSoftmax_1addd20110453a6d0c5fefbb6f336d34ef)`(int pTime)` {#classSoftmax_1addd20110453a6d0c5fefbb6f336d34ef}

Softmax의 ForwardPropagate 매소드

max값을 계산하고, exp()한 모든 값들을 더해 sum을 구한 뒤, 각각의 exp(input)한 값을 sum으로 나누어주어 확률값을 구하고 result에 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classSoftmax_1a397299ec79b62770e6696996be661f41)`(int pTime)` {#classSoftmax_1a397299ec79b62770e6696996be661f41}

softmax의 BackPropagate 매소드.

softmax의 미분 값을 구하여 input_delta에 넣어준다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline DTYPE `[`Max`](#classSoftmax_1a575f0dfcdf281af95c020b03b6ee4fb7)`(`[`Tensor`](#classTensor)`< DTYPE > * input,int start,int end)` {#classSoftmax_1a575f0dfcdf281af95c020b03b6ee4fb7}

파라미터로 받은 Tensor에서 가장 큰 값을 반환하는 함수.

#### Parameters
* `input` 가장 큰 값을 찾을 대상 [Tensor](#classTensor). 

* `start` 값을 찾을 Tensor안에서의 시작위치. 

* `end` 값을 찾을 Tensor안에서의 종료위치. 

#### Returns
input Tensor의 값들 중 가장 큰 값..

# class `SoftmaxCrossEntropy` {#classSoftmaxCrossEntropy}

```
class SoftmaxCrossEntropy
  : public LossFunction< DTYPE >
```  

이용해 뉴럴 네트워크의 손실 함수를 계산하는 클래스

Cross Entropy 계산 식을 이용해 뉴럴 네트워크의 순전파를 통해 계산된 출력 Tensor와 레이블 값의 손실 함수를 계산한다

[Softmax](#classSoftmax) Function을 뉴럴 네트워크의 마지막 Operator로 사용해 뉴럴 네트워크의 Gradient 계산을 용이하게 한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`SoftmaxCrossEntropy`](#classSoftmaxCrossEntropy_1a0190d98c392818fee9d3d3e2668ecb76)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE epsilon,std::string pName)` | [SoftmaxCrossEntropy](#classSoftmaxCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자
`public inline  `[`SoftmaxCrossEntropy`](#classSoftmaxCrossEntropy_1a9964624a80b390e30b20d5ce408080d3)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | [SoftmaxCrossEntropy](#classSoftmaxCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자
`public inline virtual  `[`~SoftmaxCrossEntropy`](#classSoftmaxCrossEntropy_1ac40b96b5be1ce3338f005ae694a53e90)`()` | [SoftmaxCrossEntropy](#classSoftmaxCrossEntropy)[LossFunction](#classLossFunction) 클래스 소멸자
`public inline int `[`Alloc`](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` | [SoftmaxCrossEntropy](#classSoftmaxCrossEntropy) 클래스의 멤버 변수들을 초기화하는 메소드
`public inline virtual void `[`Delete`](#classSoftmaxCrossEntropy_1a1b4820bab7f3c703b701d616fb3a11c9)`()` | 동적으로 할당한 멤버 변수들을 메모리 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classSoftmaxCrossEntropy_1a4daa0844f71d8f660dc19178b77a186a)`(int pTime)` | [SoftmaxCrossEntropy](#classSoftmaxCrossEntropy) LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classSoftmaxCrossEntropy_1a74ade47b66aa72fd0b712ed0e5cb18c3)`(int pTime)` | [Softmax](#classSoftmax)[CrossEntropy](#classCrossEntropy) LossFunction의 역전파를 수행하는 메소드
`public inline DTYPE `[`Max`](#classSoftmaxCrossEntropy_1a2f9be5e8bec2ef55ec57a8d7cbb902be)`(`[`Tensor`](#classTensor)`< DTYPE > * input,int start,int end)` | 지정된 범위 안에서 입력 Tensor의 데이터 값 중 최댓값을 반환하는 메소드

## Members

#### `public inline  `[`SoftmaxCrossEntropy`](#classSoftmaxCrossEntropy_1a0190d98c392818fee9d3d3e2668ecb76)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE epsilon,std::string pName)` {#classSoftmaxCrossEntropy_1a0190d98c392818fee9d3d3e2668ecb76}

[SoftmaxCrossEntropy](#classSoftmaxCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 epsilon을 매개변수로 전달하여 [SoftmaxCrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, DTYPE epsilon)](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a) 메소드를 호출한다. 
#### Parameters
* `pOperator` [SoftmaxCrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, DTYPE epsilon)](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `epsilon` 연산에 대한 translation 요소 

* `pName` LossFunction의 이름, 지정하지 않을 시 "NO NAME"으로 초기화 

#### Returns
없음 

**See also**: [SoftmaxCrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, DTYPE epsilon)](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a)

#### `public inline  `[`SoftmaxCrossEntropy`](#classSoftmaxCrossEntropy_1a9964624a80b390e30b20d5ce408080d3)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classSoftmaxCrossEntropy_1a9964624a80b390e30b20d5ce408080d3}

[SoftmaxCrossEntropy](#classSoftmaxCrossEntropy)[LossFunction](#classLossFunction) 클래스 생성자

[LossFunction](#classLossFunction) 클래스의 생성자를 호출하고, Operator와 1e-6f에 해당하는 epsilon 값을 매개변수로 전달하여 [SoftmaxCrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, DTYPE epsilon)](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a) 메소드를 호출한다. 
#### Parameters
* `pOperator` [SoftmaxCrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, DTYPE epsilon)](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a) 메소드의 매개변수로 전달할 [Operator](#classOperator)

* `pLabel` LossFunction의 입력 레이블에 해당하는 [Operator](#classOperator)

* `pName` LossFunction의 이름, 지정하지 않을 시 "NO NAME"으로 초기화 

#### Returns
없음 

**See also**: [SoftmaxCrossEntropy<DTYPE>::Alloc(Operator<DTYPE> *pOperator, DTYPE epsilon)](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a)

#### `public inline virtual  `[`~SoftmaxCrossEntropy`](#classSoftmaxCrossEntropy_1ac40b96b5be1ce3338f005ae694a53e90)`()` {#classSoftmaxCrossEntropy_1ac40b96b5be1ce3338f005ae694a53e90}

[SoftmaxCrossEntropy](#classSoftmaxCrossEntropy)[LossFunction](#classLossFunction) 클래스 소멸자

[SoftmaxCrossEntropy<DTYPE>::Delete()](#classSoftmaxCrossEntropy_1a1b4820bab7f3c703b701d616fb3a11c9) 메소드를 호출하고 클래스를 소멸시킨다 
#### Returns
없음

#### `public inline int `[`Alloc`](#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` {#classSoftmaxCrossEntropy_1a27e9fa313fea3f313e0db9465f096f0a}

[SoftmaxCrossEntropy](#classSoftmaxCrossEntropy) 클래스의 멤버 변수들을 초기화하는 메소드

[SoftmaxCrossEntropy](#classSoftmaxCrossEntropy) 클래스의 멤버 변수들의 값을 초기화 하고 포인터 멤버 변수들에 동적으로 메모리를 할당한다. 
#### Parameters
* `pOperator` [SoftmaxCrossEntropy](#classSoftmaxCrossEntropy) 클래스에 대한 입력 [Operator](#classOperator)

* `epsilon` 연산에 대한 translation 요소 

#### Returns
TRUE

#### `public inline virtual void `[`Delete`](#classSoftmaxCrossEntropy_1a1b4820bab7f3c703b701d616fb3a11c9)`()` {#classSoftmaxCrossEntropy_1a1b4820bab7f3c703b701d616fb3a11c9}

동적으로 할당한 멤버 변수들을 메모리 해제하는 메소드

softmax Result 텐서 포인터, sum 포인터, max 포인터를 할당 해제한다 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classSoftmaxCrossEntropy_1a4daa0844f71d8f660dc19178b77a186a)`(int pTime)` {#classSoftmaxCrossEntropy_1a4daa0844f71d8f660dc19178b77a186a}

[SoftmaxCrossEntropy](#classSoftmaxCrossEntropy) LossFunction의 순전파를 수행하는 메소드

LossFunction의 입력 Operator의 [Tensor](#classTensor) 값에 대해서 softmax 함수 값을 계산하고 이를 레이블 값과 비교해 Cross Entropy를 구한다

연산을 용이하게 하기 위해 Max값과 epsilon 값을 사용한다 
#### Parameters
* `pTime` 입력 Tensor의 Time 축의 Dimension 

#### Returns
LossFunction의 입력 Operator에 대한 [Softmax](#classSoftmax) Cross Entropy

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classSoftmaxCrossEntropy_1a74ade47b66aa72fd0b712ed0e5cb18c3)`(int pTime)` {#classSoftmaxCrossEntropy_1a74ade47b66aa72fd0b712ed0e5cb18c3}

[Softmax](#classSoftmax)[CrossEntropy](#classCrossEntropy) LossFunction의 역전파를 수행하는 메소드

구성한 뉴럴 네트워크에서 얻어진 [Softmax](#classSoftmax)[CrossEntropy](#classCrossEntropy) LossFunction에 대한 입력 Tensor의 Gradient를 계산한다 
#### Parameters
* `pTime` 입력 Tensor의 Time 축의 Dimension 

#### Returns
NULL

#### `public inline DTYPE `[`Max`](#classSoftmaxCrossEntropy_1a2f9be5e8bec2ef55ec57a8d7cbb902be)`(`[`Tensor`](#classTensor)`< DTYPE > * input,int start,int end)` {#classSoftmaxCrossEntropy_1a2f9be5e8bec2ef55ec57a8d7cbb902be}

지정된 범위 안에서 입력 Tensor의 데이터 값 중 최댓값을 반환하는 메소드

#### Parameters
* `input` 입력 Tensor의 포인터 

* `start` 범위의 시작 인덱스 

* `end` 범위 종료 인덱스 

#### Returns
지정된 범위 안에서 입력 Tensor의 데이터 값의 최댓값

# class `Switch` {#classSwitch}

```
class Switch
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Switch`](#classSwitch_1adc84c8b3706ee8d27d590eaa161fe8a4)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,int pLoadflag)` | 
`public inline  `[`Switch`](#classSwitch_1a4d5ac4ec7af6e172ba4b7c552f38570e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,std::string pName,int pLoadflag)` | 
`public inline  `[`~Switch`](#classSwitch_1ac049eaffd119e48a3f67e2f2f2b71255)`()` | 
`public inline int `[`GetSwitchNumber`](#classSwitch_1a2fae9496027394657c2b388d637a1190)`()` | 
`public inline int `[`SetSwitchNumber`](#classSwitch_1ada8401727fb815f606fd68863a56c518)`(int pSwitchNumber)` | 
`public inline int `[`Alloc`](#classSwitch_1ac1c7ddc5229cd38ca5a526fc2f60cb96)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1)` | 
`public inline void `[`Delete`](#classSwitch_1a483b34050a7e839ad4b6d8aa489dc00d)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classSwitch_1a560d3a9c26ab6a09ca6189c556da225c)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classSwitch_1a39c9f3cf791c861696814d5aca4c1075)`(int pTime)` | 

## Members

#### `public inline  `[`Switch`](#classSwitch_1adc84c8b3706ee8d27d590eaa161fe8a4)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,int pLoadflag)` {#classSwitch_1adc84c8b3706ee8d27d590eaa161fe8a4}

#### `public inline  `[`Switch`](#classSwitch_1a4d5ac4ec7af6e172ba4b7c552f38570e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1,std::string pName,int pLoadflag)` {#classSwitch_1a4d5ac4ec7af6e172ba4b7c552f38570e}

#### `public inline  `[`~Switch`](#classSwitch_1ac049eaffd119e48a3f67e2f2f2b71255)`()` {#classSwitch_1ac049eaffd119e48a3f67e2f2f2b71255}

#### `public inline int `[`GetSwitchNumber`](#classSwitch_1a2fae9496027394657c2b388d637a1190)`()` {#classSwitch_1a2fae9496027394657c2b388d637a1190}

#### `public inline int `[`SetSwitchNumber`](#classSwitch_1ada8401727fb815f606fd68863a56c518)`(int pSwitchNumber)` {#classSwitch_1ada8401727fb815f606fd68863a56c518}

#### `public inline int `[`Alloc`](#classSwitch_1ac1c7ddc5229cd38ca5a526fc2f60cb96)`(`[`Operator`](#classOperator)`< DTYPE > * pInput0,`[`Operator`](#classOperator)`< DTYPE > * pInput1)` {#classSwitch_1ac1c7ddc5229cd38ca5a526fc2f60cb96}

#### `public inline void `[`Delete`](#classSwitch_1a483b34050a7e839ad4b6d8aa489dc00d)`()` {#classSwitch_1a483b34050a7e839ad4b6d8aa489dc00d}

#### `public inline virtual int `[`ForwardPropagate`](#classSwitch_1a560d3a9c26ab6a09ca6189c556da225c)`(int pTime)` {#classSwitch_1a560d3a9c26ab6a09ca6189c556da225c}

#### `public inline virtual int `[`BackPropagate`](#classSwitch_1a39c9f3cf791c861696814d5aca4c1075)`(int pTime)` {#classSwitch_1a39c9f3cf791c861696814d5aca4c1075}

# class `Tanh` {#classTanh}

```
class Tanh
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Tanh`](#classTanh_1aa6d97169d17ed3d91129261a372c4b3c)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` | Tanh의 생성자
`public inline  `[`~Tanh`](#classTanh_1af7916f1b1cd5a24826f6a1305f8fbc5d)`()` | Tanh의 소멸자.
`public inline int `[`Alloc`](#classTanh_1a5b67680673cd5ad16f5e4dfe12e1a3d8)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` | 파라미터로 받은 pInput으로부터 맴버 변수들을 초기화 한다.
`public inline virtual int `[`ForwardPropagate`](#classTanh_1ac7f3f0ff7e6a8f41d3cdec5ac1bf6439)`(int pTime)` | Tanh의 ForwardPropagate 매소드
`public inline virtual int `[`BackPropagate`](#classTanh_1a461a7d2e40e24b754dc440293996fff2)`(int pTime)` | Tanh의 BackPropagate 매소드.

## Members

#### `public inline  `[`Tanh`](#classTanh_1aa6d97169d17ed3d91129261a372c4b3c)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,std::string pName,int pLoadflag)` {#classTanh_1aa6d97169d17ed3d91129261a372c4b3c}

Tanh의 생성자

파라미터로 받은 pInput으로 Alloc한다. 
#### Parameters
* `pInput` Alloc할 대상 [Operator](#classOperator)

* `pName` Operator에 사용자가 부여한 이름.

#### `public inline  `[`~Tanh`](#classTanh_1af7916f1b1cd5a24826f6a1305f8fbc5d)`()` {#classTanh_1af7916f1b1cd5a24826f6a1305f8fbc5d}

Tanh의 소멸자.

#### `public inline int `[`Alloc`](#classTanh_1a5b67680673cd5ad16f5e4dfe12e1a3d8)`(`[`Operator`](#classOperator)`< DTYPE > * pInput)` {#classTanh_1a5b67680673cd5ad16f5e4dfe12e1a3d8}

파라미터로 받은 pInput으로부터 맴버 변수들을 초기화 한다.

Result와 Gradient를 저장하기 위해 pInput의 Shape과 같은 dim을 갖는 Tensor를 생성한다. 
#### Parameters
* `pInput` 생성 할 Tensor의 Shape정보를 가진 [Operator](#classOperator)

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`ForwardPropagate`](#classTanh_1ac7f3f0ff7e6a8f41d3cdec5ac1bf6439)`(int pTime)` {#classTanh_1ac7f3f0ff7e6a8f41d3cdec5ac1bf6439}

Tanh의 ForwardPropagate 매소드

input의 Tensor값들을 Tanh을 취한 뒤 result에 저장한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classTanh_1a461a7d2e40e24b754dc440293996fff2)`(int pTime)` {#classTanh_1a461a7d2e40e24b754dc440293996fff2}

Tanh의 BackPropagate 매소드.

result값으로 tanh의 미분 값을 계산하여 input_delta에 더한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `Tensor` {#classTensor}

저장하고 관리하는 클래스

학습에 사용될 Tensor를 정의하기 위한 클래스

Tensor클래스는 Shape와 LongArray를 이용하여 Tensor의 모양과 데이터를 저장한다.

Operator클래스에서 m_aaResult(ForwardPropagate한 값)와 m_aaGradient(BackPropagate한 값)을 저장한다.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public  `[`Tensor`](#classTensor_1aa20e4455987cf99194c00bd46286f8bf)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4,IsUseTime pAnswer)` | 
`public  `[`Tensor`](#classTensor_1a68da0c8c62a77512f83f5802b4716196)`(int pSize0,int pSize1,int pSize2,int pSize3,IsUseTime pAnswer)` | 
`public  `[`Tensor`](#classTensor_1aadb1340f4bed2b4e4babcf0c3fb65088)`(int pSize0,int pSize1,int pSize2,IsUseTime pAnswer)` | 
`public  `[`Tensor`](#classTensor_1afe220f73c7aa5a5c8da12141a095e49c)`(int pSize0,int pSize1,IsUseTime pAnswer)` | 
`public  `[`Tensor`](#classTensor_1a84b521a3f07d8e26a7c7fe64e2fc0289)`(int pSize0,IsUseTime pAnswer)` | 
`public  `[`Tensor`](#classTensor_1a406cfed64111646a8007d0e9ba39f8fa)`(`[`Shape`](#classShape)` * pShape,IsUseTime pAnswer)` | 
`public  `[`Tensor`](#classTensor_1a2ccac9a451c8ca9a5685ac6e4c177a02)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 
`public virtual  `[`~Tensor`](#classTensor_1af7a84a67cd4a8157d05a16bcbf81f735)`()` | 
`public `[`Shape`](#classShape)` * `[`GetShape`](#classTensor_1a6f3381bacc67b4251d1a0de0ed090ca2)`()` | 
`public int `[`GetRank`](#classTensor_1ad73ec299e9298a7530f61d8103839de1)`()` | 
`public int `[`GetDim`](#classTensor_1a249f6eb67fec9e3cb5eda26fbb81bbc4)`(int pRanknum)` | 
`public `[`LongArray`](#classLongArray)`< DTYPE > * `[`GetLongArray`](#classTensor_1a78cf4c5b86e1fc2ffe7f3bd1bdcf7cea)`()` | 
`public int `[`GetCapacity`](#classTensor_1a7c835b1abb2c0d5b441c662288630537)`()` | 
`public int `[`GetElement`](#classTensor_1a7234157cfe4cd02e72e7d6c5490a8aad)`(unsigned int index)` | 
`public DTYPE & `[`operator[]`](#classTensor_1a11cfde5038c40ab36f315960079e3d77)`(unsigned int index)` | 
`public Device `[`GetDevice`](#classTensor_1a5e25ecadd90a889393c9ec1340644492)`()` | 
`public IsUseTime `[`GetIsUseTime`](#classTensor_1ab736c3bd8f1ab90285fcb2ff6d0e57ec)`()` | 
`public DTYPE * `[`GetCPULongArray`](#classTensor_1a2f0d3b84baa1fc052c6bfe8e58b24497)`(unsigned int pTime)` | 
`public int `[`GetTimeSize`](#classTensor_1ab0eb9c7f66e536582df4af3718667d3b)`()` | 
`public int `[`GetBatchSize`](#classTensor_1a164dacb610b0ad1436362fbdbe6b63b5)`()` | 
`public int `[`GetChannelSize`](#classTensor_1a8dc5ce2ae24cddd6f9d9979e795dedeb)`()` | 
`public int `[`GetRowSize`](#classTensor_1aaa893ffee48e86000bd372128e39a173)`()` | 
`public int `[`GetColSize`](#classTensor_1a92ffa915d8e09ba68409528ac3048df8)`()` | 
`public int `[`ReShape`](#classTensor_1a12190442774f6293243d64be2330470e)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4)` | 
`public int `[`ReShape`](#classTensor_1a4c47e331e35d5de574ecd3995e43ba6b)`(int pSize0,int pSize1,int pSize2,int pSize3)` | 
`public int `[`ReShape`](#classTensor_1a30a392fb7d63b589428442a0d72eeb81)`(int pSize0,int pSize1,int pSize2)` | 
`public int `[`ReShape`](#classTensor_1aa573a9456feaa4a43e85be4a7f9c686d)`(int pSize0,int pSize1)` | 
`public int `[`ReShape`](#classTensor_1affe015e33f9bc1db0f2c21b86a1abf97)`(int pSize0)` | 
`public void `[`Reset`](#classTensor_1aa38f808b76ef62ebd82452a9bc5ff7b2)`()` | 
`public void `[`SetDeviceCPU`](#classTensor_1a8b86a6ff0bc43a13636c1a9b04238884)`()` | 
`public int `[`Save`](#classTensor_1ab53312ec1be20f5c2f252bf08c8002cc)`(FILE * fp)` | 
`public int `[`Load`](#classTensor_1a6c3a5202d2fb1dacc51c155e4d1c46e2)`(FILE * fp)` | 
`public void `[`Clip`](#classTensor_1a1fbf9588e12fba1c08fb673e77d18a33)`(float min,float max)` | 
`public void `[`MultiplyScalar`](#classTensor_1a9fb8c0ccec9bb0ea615e3d2c7551d6bf)`(unsigned int pTime,float pScalar)` | 

## Members

#### `public  `[`Tensor`](#classTensor_1aa20e4455987cf99194c00bd46286f8bf)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4,IsUseTime pAnswer)` {#classTensor_1aa20e4455987cf99194c00bd46286f8bf}

#### `public  `[`Tensor`](#classTensor_1a68da0c8c62a77512f83f5802b4716196)`(int pSize0,int pSize1,int pSize2,int pSize3,IsUseTime pAnswer)` {#classTensor_1a68da0c8c62a77512f83f5802b4716196}

#### `public  `[`Tensor`](#classTensor_1aadb1340f4bed2b4e4babcf0c3fb65088)`(int pSize0,int pSize1,int pSize2,IsUseTime pAnswer)` {#classTensor_1aadb1340f4bed2b4e4babcf0c3fb65088}

#### `public  `[`Tensor`](#classTensor_1afe220f73c7aa5a5c8da12141a095e49c)`(int pSize0,int pSize1,IsUseTime pAnswer)` {#classTensor_1afe220f73c7aa5a5c8da12141a095e49c}

#### `public  `[`Tensor`](#classTensor_1a84b521a3f07d8e26a7c7fe64e2fc0289)`(int pSize0,IsUseTime pAnswer)` {#classTensor_1a84b521a3f07d8e26a7c7fe64e2fc0289}

#### `public  `[`Tensor`](#classTensor_1a406cfed64111646a8007d0e9ba39f8fa)`(`[`Shape`](#classShape)` * pShape,IsUseTime pAnswer)` {#classTensor_1a406cfed64111646a8007d0e9ba39f8fa}

#### `public  `[`Tensor`](#classTensor_1a2ccac9a451c8ca9a5685ac6e4c177a02)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classTensor_1a2ccac9a451c8ca9a5685ac6e4c177a02}

#### `public virtual  `[`~Tensor`](#classTensor_1af7a84a67cd4a8157d05a16bcbf81f735)`()` {#classTensor_1af7a84a67cd4a8157d05a16bcbf81f735}

#### `public `[`Shape`](#classShape)` * `[`GetShape`](#classTensor_1a6f3381bacc67b4251d1a0de0ed090ca2)`()` {#classTensor_1a6f3381bacc67b4251d1a0de0ed090ca2}

#### `public int `[`GetRank`](#classTensor_1ad73ec299e9298a7530f61d8103839de1)`()` {#classTensor_1ad73ec299e9298a7530f61d8103839de1}

#### `public int `[`GetDim`](#classTensor_1a249f6eb67fec9e3cb5eda26fbb81bbc4)`(int pRanknum)` {#classTensor_1a249f6eb67fec9e3cb5eda26fbb81bbc4}

#### `public `[`LongArray`](#classLongArray)`< DTYPE > * `[`GetLongArray`](#classTensor_1a78cf4c5b86e1fc2ffe7f3bd1bdcf7cea)`()` {#classTensor_1a78cf4c5b86e1fc2ffe7f3bd1bdcf7cea}

#### `public int `[`GetCapacity`](#classTensor_1a7c835b1abb2c0d5b441c662288630537)`()` {#classTensor_1a7c835b1abb2c0d5b441c662288630537}

#### `public int `[`GetElement`](#classTensor_1a7234157cfe4cd02e72e7d6c5490a8aad)`(unsigned int index)` {#classTensor_1a7234157cfe4cd02e72e7d6c5490a8aad}

#### `public DTYPE & `[`operator[]`](#classTensor_1a11cfde5038c40ab36f315960079e3d77)`(unsigned int index)` {#classTensor_1a11cfde5038c40ab36f315960079e3d77}

#### `public Device `[`GetDevice`](#classTensor_1a5e25ecadd90a889393c9ec1340644492)`()` {#classTensor_1a5e25ecadd90a889393c9ec1340644492}

#### `public IsUseTime `[`GetIsUseTime`](#classTensor_1ab736c3bd8f1ab90285fcb2ff6d0e57ec)`()` {#classTensor_1ab736c3bd8f1ab90285fcb2ff6d0e57ec}

#### `public DTYPE * `[`GetCPULongArray`](#classTensor_1a2f0d3b84baa1fc052c6bfe8e58b24497)`(unsigned int pTime)` {#classTensor_1a2f0d3b84baa1fc052c6bfe8e58b24497}

#### `public int `[`GetTimeSize`](#classTensor_1ab0eb9c7f66e536582df4af3718667d3b)`()` {#classTensor_1ab0eb9c7f66e536582df4af3718667d3b}

#### `public int `[`GetBatchSize`](#classTensor_1a164dacb610b0ad1436362fbdbe6b63b5)`()` {#classTensor_1a164dacb610b0ad1436362fbdbe6b63b5}

#### `public int `[`GetChannelSize`](#classTensor_1a8dc5ce2ae24cddd6f9d9979e795dedeb)`()` {#classTensor_1a8dc5ce2ae24cddd6f9d9979e795dedeb}

#### `public int `[`GetRowSize`](#classTensor_1aaa893ffee48e86000bd372128e39a173)`()` {#classTensor_1aaa893ffee48e86000bd372128e39a173}

#### `public int `[`GetColSize`](#classTensor_1a92ffa915d8e09ba68409528ac3048df8)`()` {#classTensor_1a92ffa915d8e09ba68409528ac3048df8}

#### `public int `[`ReShape`](#classTensor_1a12190442774f6293243d64be2330470e)`(int pSize0,int pSize1,int pSize2,int pSize3,int pSize4)` {#classTensor_1a12190442774f6293243d64be2330470e}

#### `public int `[`ReShape`](#classTensor_1a4c47e331e35d5de574ecd3995e43ba6b)`(int pSize0,int pSize1,int pSize2,int pSize3)` {#classTensor_1a4c47e331e35d5de574ecd3995e43ba6b}

#### `public int `[`ReShape`](#classTensor_1a30a392fb7d63b589428442a0d72eeb81)`(int pSize0,int pSize1,int pSize2)` {#classTensor_1a30a392fb7d63b589428442a0d72eeb81}

#### `public int `[`ReShape`](#classTensor_1aa573a9456feaa4a43e85be4a7f9c686d)`(int pSize0,int pSize1)` {#classTensor_1aa573a9456feaa4a43e85be4a7f9c686d}

#### `public int `[`ReShape`](#classTensor_1affe015e33f9bc1db0f2c21b86a1abf97)`(int pSize0)` {#classTensor_1affe015e33f9bc1db0f2c21b86a1abf97}

#### `public void `[`Reset`](#classTensor_1aa38f808b76ef62ebd82452a9bc5ff7b2)`()` {#classTensor_1aa38f808b76ef62ebd82452a9bc5ff7b2}

#### `public void `[`SetDeviceCPU`](#classTensor_1a8b86a6ff0bc43a13636c1a9b04238884)`()` {#classTensor_1a8b86a6ff0bc43a13636c1a9b04238884}

#### `public int `[`Save`](#classTensor_1ab53312ec1be20f5c2f252bf08c8002cc)`(FILE * fp)` {#classTensor_1ab53312ec1be20f5c2f252bf08c8002cc}

#### `public int `[`Load`](#classTensor_1a6c3a5202d2fb1dacc51c155e4d1c46e2)`(FILE * fp)` {#classTensor_1a6c3a5202d2fb1dacc51c155e4d1c46e2}

#### `public void `[`Clip`](#classTensor_1a1fbf9588e12fba1c08fb673e77d18a33)`(float min,float max)` {#classTensor_1a1fbf9588e12fba1c08fb673e77d18a33}

#### `public void `[`MultiplyScalar`](#classTensor_1a9fb8c0ccec9bb0ea615e3d2c7551d6bf)`(unsigned int pTime,float pScalar)` {#classTensor_1a9fb8c0ccec9bb0ea615e3d2c7551d6bf}

# class `Tensorholder` {#classTensorholder}

Result만 사용하기 위한 클래스.

주로 Network의 input, label값을 저장하기 위해 구현되었다.

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Tensorholder`](#classTensorholder_1abe241533158621e13d68ee4f24264623)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor,std::string pName,int pTrainable,int pLoadflag)` | Tensorholder의 생성자.
`public inline  `[`Tensorholder`](#classTensorholder_1a57d1fb2ecee587dccc045351d98792ae)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pTrainable,int pLoadflag)` | Tensorholder의 생성자.
`public inline  `[`~Tensorholder`](#classTensorholder_1a904cee43a83113a6e81ea56b90c1c575)`()` | Tensorholder의 소멸자.
`public inline int `[`Alloc`](#classTensorholder_1ab18caabed6344ba06bbb7f00f20a4c84)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor,int pTrainable)` | 파라미터로 뱓은 pTensor로 Tensorholder를 설정한다.
`public inline int `[`Alloc`](#classTensorholder_1ab7d9f1f53c524d2bd53d271033251415)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,int pTrainable)` | 파라미터로 뱓은 변수들로 pTensor를 생성하고 Tensorholder를 설정한다.
`public inline `[`Tensor`](#classTensor)`< DTYPE > * `[`GetTensor`](#classTensorholder_1a2e667f2bfd21edd144a1ff5c3b055094)`()` | 
`public inline void `[`SetTensor`](#classTensorholder_1a7ea9ae1a6146391965e7d351be8e8c1f)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 파라미터로 받은 Tensor를 Result로 설정한다.
`public inline void `[`FeedTensor`](#classTensorholder_1ab4e8ab628467d10a19951648cba83c40)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` | 파라미터로 받은 Tensor를 Result로 설정한다.

## Members

#### `public inline  `[`Tensorholder`](#classTensorholder_1abe241533158621e13d68ee4f24264623)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor,std::string pName,int pTrainable,int pLoadflag)` {#classTensorholder_1abe241533158621e13d68ee4f24264623}

Tensorholder의 생성자.

파라미터로 받은 pTensor, pTrainable으로 Alloc한다. 
#### Parameters
* `pTensor` Alloc에 사용할 [Tensor](#classTensor), 결론적으로 Tensorholder의 Result로 설정된다. 

* `pName` 사용자가 부여한 Tensorholder의 이름. 

* `pTrainable` 생성 할 [Operator(Tensorholder)](#classOperator)가 Trainable인지 알리는 변수. default로 TRUE를 사용한다. int [Alloc(Tensor<DTYPE> *pTensor, int pTrainable)](#classTensorholder_1ab18caabed6344ba06bbb7f00f20a4c84)

#### `public inline  `[`Tensorholder`](#classTensorholder_1a57d1fb2ecee587dccc045351d98792ae)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,std::string pName,int pTrainable,int pLoadflag)` {#classTensorholder_1a57d1fb2ecee587dccc045351d98792ae}

Tensorholder의 생성자.

파리미터로 받은 pTimeSize, pBatchSize, pChannelSize, pRowSize, pColSize, pTrainable로 Alloc한다.

파라미터로 받은 변수들은 Alloc에서 생성 할 Tensor의 Shape을 결정한다. 
#### Parameters
* `pTimeSize` Alloc에 사용 할 timesize. 

* `pBatchSize` Alloc에 사용 할 batchsize. 

* `pChannelSize` Alloc에 사용 할 channelsize. 

* `pRowSize` Alloc에 사용 할 rowsize 

* `pColSize` Alloc에 사용 할 colsize 

* `pName` 사용자가 부여한 Tensorholder의 이름. 

* `pTrainable` 생성 할 [Operator(Tensorholder)](#classOperator)가 Trainable인지 알리는 변수. default로 TRUE를 사용한다. int [Alloc(int pTimeSize, int pBatchSize, int pChannelSize, int pRowSize, int pColSize, int pTrainable)](#classTensorholder_1ab7d9f1f53c524d2bd53d271033251415)

#### `public inline  `[`~Tensorholder`](#classTensorholder_1a904cee43a83113a6e81ea56b90c1c575)`()` {#classTensorholder_1a904cee43a83113a6e81ea56b90c1c575}

Tensorholder의 소멸자.

딱히 하는 일은 없다.

#### `public inline int `[`Alloc`](#classTensorholder_1ab18caabed6344ba06bbb7f00f20a4c84)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor,int pTrainable)` {#classTensorholder_1ab18caabed6344ba06bbb7f00f20a4c84}

파라미터로 뱓은 pTensor로 Tensorholder를 설정한다.

파라미터로 받은 pTensor를 Result값으로 설정한다.

SetIsTensorholder를 통해 Tensorholder임을 설정하고, pTensor의 Shape과 같은 Shape을 갖는 Tensor를 만들어 Gradient로 설정한다. 
#### Parameters
* `pTensor` Tensorholder의 Result로 저장 될값을 가진 [Tensor](#classTensor). 

* `pTrainable` Training이 가능한지 아닌지 알리는 변수 

#### Returns
성공 시 TRUE. int Operator<DTYPE>::ResetResult() int Operator<DTYPE>::SetIsTensorholder(int pIsParameter) int Operator<DTYPE>::SetIsTrainable(int pIsTrainable) int Operator<DTYPE>::AddGradient(Tensor<DTYPE> *pTensor)

#### `public inline int `[`Alloc`](#classTensorholder_1ab7d9f1f53c524d2bd53d271033251415)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,int pTrainable)` {#classTensorholder_1ab7d9f1f53c524d2bd53d271033251415}

파라미터로 뱓은 변수들로 pTensor를 생성하고 Tensorholder를 설정한다.

파라미터로 받은 변수들로 pTensor를 생성하고 Result로 설정한다.

생성한 pTensor의 Shape과 같은 Tensor를 생성하여 Gradient로 설정한다. 
#### Parameters
* `pTimeSize` 생성할 pTensor의 timesize 

* `pBatchSize` 생성할 pTensor의 batchsize 

* `pChannelSize` 생성할 pTensor의 channelsize 

* `pRowSize` 생성할 pTensor의 rowsize 

* `pColSize` 생성할 pTensor의 colsize 

* `pTrainable` Training이 가능한지 아닌지 알리는 변수 

#### Returns
성공 시 TRUE. int Operator<DTYPE>::ResetResult() int Operator<DTYPE>::SetIsTensorholder(int pIsParameter) int Operator<DTYPE>::SetIsTrainable(int pIsTrainable) [Shape](#classShape) *Tensor<DTYPE>::GetShape() int Operator<DTYPE>::AddGradient(Tensor<DTYPE> *pTensor)

#### `public inline `[`Tensor`](#classTensor)`< DTYPE > * `[`GetTensor`](#classTensorholder_1a2e667f2bfd21edd144a1ff5c3b055094)`()` {#classTensorholder_1a2e667f2bfd21edd144a1ff5c3b055094}

#### `public inline void `[`SetTensor`](#classTensorholder_1a7ea9ae1a6146391965e7d351be8e8c1f)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classTensorholder_1a7ea9ae1a6146391965e7d351be8e8c1f}

파라미터로 받은 Tensor를 Result로 설정한다.

#### Parameters
* `pTensor` Result로 설정 할 [Tensor](#classTensor).

#### `public inline void `[`FeedTensor`](#classTensorholder_1ab4e8ab628467d10a19951648cba83c40)`(`[`Tensor`](#classTensor)`< DTYPE > * pTensor)` {#classTensorholder_1ab4e8ab628467d10a19951648cba83c40}

파라미터로 받은 Tensor를 Result로 설정한다.

#### Parameters
* `pTensor` Result로 설정 할 [Tensor](#classTensor).

# class `TransposedConvolution2D` {#classTransposedConvolution2D}

```
class TransposedConvolution2D
  : public Operator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`TransposedConvolution2D`](#classTransposedConvolution2D_1a4823926469a618fa912baf03150954dc)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,std::string pName,int pLoadflag)` | [TransposedConvolution2D](#classTransposedConvolution2D) 생성자.
`public inline  `[`TransposedConvolution2D`](#classTransposedConvolution2D_1ad03412e0c92c77e8a691ea68b6c6c00a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding,std::string pName,int pLoadflag)` | [TransposedConvolution2D](#classTransposedConvolution2D) 생성자.
`public inline  `[`TransposedConvolution2D`](#classTransposedConvolution2D_1a4ae7864232a60a094933f3350fbb4516)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2,std::string pName,int pLoadflag)` | [TransposedConvolution2D](#classTransposedConvolution2D) 생성자.
`public inline virtual  `[`~TransposedConvolution2D`](#classTransposedConvolution2D_1a4cf6b21bdcdf857b388b743a56059240)`()` | TransposedConvolution2D의 소멸자.
`public inline int `[`Alloc`](#classTransposedConvolution2D_1af65884be81ea23dd834a5820cec32fe6)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2)` | 파라미터로 받은 pInput, pWeight, stride1, stride2, padding1, padding2으로 맴버 변수들을 초기화 한다.
`public inline void `[`Delete`](#classTransposedConvolution2D_1aa3f3ecaa0bd9cd0752bfa171756be95d)`()` | GPU에 할당했던 메모리를 해제하고 각 포인터들을 NULL로 초기화한다.
`public inline virtual int `[`ForwardPropagate`](#classTransposedConvolution2D_1ada8f56cda24d89a955744add42df8742)`(int pTime)` | TransposedConvolution2D의 ForwardPropagate 메소드.
`public inline virtual int `[`BackPropagate`](#classTransposedConvolution2D_1a30821ce98f67cb3157a8749c70f2a12f)`(int pTime)` | TRANSPOSEDCONVOLUTION_2D의 BackPropagate 메소드.

## Members

#### `public inline  `[`TransposedConvolution2D`](#classTransposedConvolution2D_1a4823926469a618fa912baf03150954dc)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,std::string pName,int pLoadflag)` {#classTransposedConvolution2D_1a4823926469a618fa912baf03150954dc}

[TransposedConvolution2D](#classTransposedConvolution2D) 생성자.

파라미터로 받은 pInput, pWeight, stride1, stride2로 Alloc한다. 
#### Parameters
* `pInput` TransposedConvolution할 [Operator](#classOperator)

* `pWeight` TransposedConvolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight, int stride1, int stride2, int padding1, int padding2)](#classTransposedConvolution2D_1af65884be81ea23dd834a5820cec32fe6)

#### `public inline  `[`TransposedConvolution2D`](#classTransposedConvolution2D_1ad03412e0c92c77e8a691ea68b6c6c00a)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding,std::string pName,int pLoadflag)` {#classTransposedConvolution2D_1ad03412e0c92c77e8a691ea68b6c6c00a}

[TransposedConvolution2D](#classTransposedConvolution2D) 생성자.

파라미터로 받은 pInput, pWeight, stride1, stride2로 Alloc한다. 
#### Parameters
* `pInput` TransposedConvolution할 [Operator](#classOperator)

* `pWeight` TransposedConvolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `padding` padding 할 값. height, width 모두 이 값으로 한다. 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight, int stride1, int stride2, int padding1, int padding2)](#classTransposedConvolution2D_1af65884be81ea23dd834a5820cec32fe6)

#### `public inline  `[`TransposedConvolution2D`](#classTransposedConvolution2D_1a4ae7864232a60a094933f3350fbb4516)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2,std::string pName,int pLoadflag)` {#classTransposedConvolution2D_1a4ae7864232a60a094933f3350fbb4516}

[TransposedConvolution2D](#classTransposedConvolution2D) 생성자.

파라미터로 받은 pInput, pWeight, stride1, stride2, padding1, padding2로 Alloc한다. 
#### Parameters
* `pInput` TransposedConvolution할 [Operator](#classOperator)

* `pWeight` TransposedConvolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `padding1` height padding값 

* `padding2` width padding값 

* `pName` 사용자가 부여한 Operator이름. int [Alloc(Operator<DTYPE> *pInput, Operator<DTYPE> *pWeight, int stride1, int stride2, int padding1, int padding2)](#classTransposedConvolution2D_1af65884be81ea23dd834a5820cec32fe6)

#### `public inline virtual  `[`~TransposedConvolution2D`](#classTransposedConvolution2D_1a4cf6b21bdcdf857b388b743a56059240)`()` {#classTransposedConvolution2D_1a4cf6b21bdcdf857b388b743a56059240}

TransposedConvolution2D의 소멸자.

Delete매소드를 사용해 GPU에 할당했던 값들을 해제한다. void [Delete()](#classTransposedConvolution2D_1aa3f3ecaa0bd9cd0752bfa171756be95d)

#### `public inline int `[`Alloc`](#classTransposedConvolution2D_1af65884be81ea23dd834a5820cec32fe6)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,`[`Operator`](#classOperator)`< DTYPE > * pWeight,int stride1,int stride2,int padding1,int padding2)` {#classTransposedConvolution2D_1af65884be81ea23dd834a5820cec32fe6}

파라미터로 받은 pInput, pWeight, stride1, stride2, padding1, padding2으로 맴버 변수들을 초기화 한다.

pInput과 pWeight의 Shape과 stride, padding값으로 output으로 Result와 Delta로 사용 할 Tensor의 Shape을 정의한다. 
#### Parameters
* `pInput` transposedConvolution할 [Operator](#classOperator)

* `pWeight` transposedConvolution할 weight. 

* `stride1` stride row값 

* `stride2` stride colunm값 

* `padding1` height padding값 

* `padding2` width padding값

#### `public inline void `[`Delete`](#classTransposedConvolution2D_1aa3f3ecaa0bd9cd0752bfa171756be95d)`()` {#classTransposedConvolution2D_1aa3f3ecaa0bd9cd0752bfa171756be95d}

GPU에 할당했던 메모리를 해제하고 각 포인터들을 NULL로 초기화한다.

inputTensorDesc, outputTensorDesc,deltaDesc, inputDeltaDesc, convDesc, filterDesc,filterDeltaDesc들을 삭제하고 NULL로 초기화한다.

cudnn연산을 위해 할당 했던 메모리들을 해제시킨다.

#### `public inline virtual int `[`ForwardPropagate`](#classTransposedConvolution2D_1ada8f56cda24d89a955744add42df8742)`(int pTime)` {#classTransposedConvolution2D_1ada8f56cda24d89a955744add42df8742}

TransposedConvolution2D의 ForwardPropagate 메소드.

weight(filter size = rowsizeOfWeight * colsizeOfWeight)와 input의 곱한 값을 result에 더해 넣는다.

이때 m_stride값들 만큼 이동하며 result를 계산한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

#### `public inline virtual int `[`BackPropagate`](#classTransposedConvolution2D_1a30821ce98f67cb3157a8749c70f2a12f)`(int pTime)` {#classTransposedConvolution2D_1a30821ce98f67cb3157a8749c70f2a12f}

TRANSPOSEDCONVOLUTION_2D의 BackPropagate 메소드.

TransposedConvolution의 미분 값(weight * this_delta, input * this_delta)을 계산하여 input_delta와 weight_gradient에 각각 더해 넣는다.

이때 m_stride값들 만큼 이동하며 미분 값을 넣을 위치를 계산한다. 
#### Parameters
* `pTime` 연산 할 Tensor가 위치한 Time값. default는 0을 사용. 

#### Returns
성공 시 TRUE.

# class `TransposedConvolutionLayer2D` {#classTransposedConvolutionLayer2D}

```
class TransposedConvolutionLayer2D
  : public Module< DTYPE >
```  

구성해 2-Dimensional TransposedConvolution Layer의 기능을 수행하는 모듈을 생성하는 클래스

Operator들을 뉴럴 네트워크의 서브 그래프로 구성해 2-Dimensional Transposedconvolution Layer의 기능을 수행한다

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`TransposedConvolutionLayer2D`](#classTransposedConvolutionLayer2D_1a7d9568737d2ea26cee8bfab6c0293577)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPadding,int use_bias,std::string pName)` | [TransposedConvolutionLayer2D](#classTransposedConvolutionLayer2D) 클래스 생성자
`public inline virtual  `[`~TransposedConvolutionLayer2D`](#classTransposedConvolutionLayer2D_1a8f44ef6a070ba74789ff1eed98e60ab2)`()` | [TransposedConvolutionLayer2D](#classTransposedConvolutionLayer2D) 클래스 소멸자
`public inline int `[`Alloc`](#classTransposedConvolutionLayer2D_1a2e301be572bc7ece3487c7bc6f9f031e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPaddingRow,int pPaddingCol,int use_bias,std::string pName)` | 2D TransposedConvolution Layer 그래프를 동적으로 할당 및 구성하는 메소드

## Members

#### `public inline  `[`TransposedConvolutionLayer2D`](#classTransposedConvolutionLayer2D_1a7d9568737d2ea26cee8bfab6c0293577)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPadding,int use_bias,std::string pName)` {#classTransposedConvolutionLayer2D_1a7d9568737d2ea26cee8bfab6c0293577}

[TransposedConvolutionLayer2D](#classTransposedConvolutionLayer2D) 클래스 생성자

[TransposedConvolutionLayer2D](#classTransposedConvolutionLayer2D) 클래스의 Alloc 함수를 호출한다. 
**See also**: [TransposedConvolutionLayer2D<DTYPE>::Alloc(Operator<DTYPE> *pInput, int pNumInputChannel, int pNumOutputChannel, int pNumKernelRow, int pNumKernelCol, int pStrideRow, int pStrideCol, int pPaddingRow, int pPaddingCol, int use_bias, std::string pName)](#classTransposedConvolutionLayer2D_1a2e301be572bc7ece3487c7bc6f9f031e)

#### `public inline virtual  `[`~TransposedConvolutionLayer2D`](#classTransposedConvolutionLayer2D_1a8f44ef6a070ba74789ff1eed98e60ab2)`()` {#classTransposedConvolutionLayer2D_1a8f44ef6a070ba74789ff1eed98e60ab2}

[TransposedConvolutionLayer2D](#classTransposedConvolutionLayer2D) 클래스 소멸자

단, 동적 할당 받은 Operator들은 NeuralNetwork에서 할당 해제한다.

#### `public inline int `[`Alloc`](#classTransposedConvolutionLayer2D_1a2e301be572bc7ece3487c7bc6f9f031e)`(`[`Operator`](#classOperator)`< DTYPE > * pInput,int pNumInputChannel,int pNumOutputChannel,int pNumKernelRow,int pNumKernelCol,int pStrideRow,int pStrideCol,int pPaddingRow,int pPaddingCol,int use_bias,std::string pName)` {#classTransposedConvolutionLayer2D_1a2e301be572bc7ece3487c7bc6f9f031e}

2D TransposedConvolution Layer 그래프를 동적으로 할당 및 구성하는 메소드

Input Operator의 Element에 대해 2D TransposedConvolution 수행한다.

Input Operator의 Element에 대해 Weight를 이용해 2차원 전치합성 곱(2D TransposedConvolution)을 수행하고 Bias가 존재할 시 Bias를 합(Column Wise Addition)해 Output Operator로 내보내는 layer를 구성한다. 
#### Parameters
* `pInput` 해당 Layer의 Input에 해당하는 [Operator](#classOperator)

* `pNumInputChannel` 해당 Layer의 Input Operator의 Channel의 갯수, Input Column에 대한 Dimension 

* `pNumOutputChannel` 해당 Layer의 Output Operator의 Channel의 갯수, Output Column에 대한 Dimension 

* `pNumKernelRow` 2D TransposedConvolution Layer 커널의 Row Size 

* `pNumKernelCol` 2D TransposedConvolution Layer 커널의 Column Size 

* `pStrideRow` 2D TransposedConvolution Layer의 Row Stride Size 

* `pStrideCol` 2D TransposedConvolution Layer의 Column Stride Size 

* `pPaddingRow` 2D TransposedConvolution Layer의 Row Padding 값 

* `pPaddingCol` 2D TransposedConvolution Layer의 Column Padding 값 

* `use_bias` Bias 사용 유무, 0일 시 사용 안 함, 0이 아닐 시 사용 

* `pName` Module의 이름 

#### Returns
TRUE 

**See also**: [TransposedConvolutionLayer2D<DTYPE>::TransposedConvolutionLayer2D](#classTransposedConvolutionLayer2D_1a7d9568737d2ea26cee8bfab6c0293577)([Operator<DTYPE>](#classOperator) *pInput, [Operator<DTYPE>](#classOperator) *pWeight, int stride1, int stride2, std::string pName = "NO NAME") AddColWise<DTYPE>::AddColWise(Operator<DTYPE> *pInput, Operator<DTYPE> *pBias, std::string pName) [Module<DTYPE>::AnalyzeGraph(Operator<DTYPE> *pResultOperator)](#classModule_1a7a8ca0c6ddde4bffde9d806ff64ba614)

# class `TripletLoss` {#classTripletLoss}

```
class TripletLoss
  : public LossFunction< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`TripletLoss`](#classTripletLoss_1a23bba0ec84bc8109fa5610018e449f90)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE margin,std::string pName)` | 
`public inline  `[`TripletLoss`](#classTripletLoss_1aa73d1a54468e42cbeeab30a8a47c9730)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE margin,std::string pName)` | 
`public inline  `[`~TripletLoss`](#classTripletLoss_1a9d49800a7d2184db7598bb9561d0073e)`()` | 
`public inline int `[`Alloc`](#classTripletLoss_1a2e8b33b71498bbdbbcc3ece877446afa)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE margin)` | 
`public inline virtual void `[`Delete`](#classTripletLoss_1a2d992cd9dde39d73db9cffe5890c2d6f)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classTripletLoss_1a2feac7ce4fd47d6d1d2c87dc850fae47)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classTripletLoss_1a40d30a0c03da6f8ef5a9cfdaddbba1f0)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`TripletLoss`](#classTripletLoss_1a23bba0ec84bc8109fa5610018e449f90)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE margin,std::string pName)` {#classTripletLoss_1a23bba0ec84bc8109fa5610018e449f90}

#### `public inline  `[`TripletLoss`](#classTripletLoss_1aa73d1a54468e42cbeeab30a8a47c9730)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE margin,std::string pName)` {#classTripletLoss_1aa73d1a54468e42cbeeab30a8a47c9730}

#### `public inline  `[`~TripletLoss`](#classTripletLoss_1a9d49800a7d2184db7598bb9561d0073e)`()` {#classTripletLoss_1a9d49800a7d2184db7598bb9561d0073e}

#### `public inline int `[`Alloc`](#classTripletLoss_1a2e8b33b71498bbdbbcc3ece877446afa)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE margin)` {#classTripletLoss_1a2e8b33b71498bbdbbcc3ece877446afa}

#### `public inline virtual void `[`Delete`](#classTripletLoss_1a2d992cd9dde39d73db9cffe5890c2d6f)`()` {#classTripletLoss_1a2d992cd9dde39d73db9cffe5890c2d6f}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classTripletLoss_1a2feac7ce4fd47d6d1d2c87dc850fae47)`(int pTime)` {#classTripletLoss_1a2feac7ce4fd47d6d1d2c87dc850fae47}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classTripletLoss_1a40d30a0c03da6f8ef5a9cfdaddbba1f0)`(int pTime)` {#classTripletLoss_1a40d30a0c03da6f8ef5a9cfdaddbba1f0}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

# class `UniformNoiseGenerator` {#classUniformNoiseGenerator}

```
class UniformNoiseGenerator
  : public NoiseGenerator< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`UniformNoiseGenerator`](#classUniformNoiseGenerator_1a95696eba2f5b4068da94b4227503a02f)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,float pLowerLimit,float pUpperLimit,IsUseTime pAnswer,std::string pName)` | 
`public inline  `[`~UniformNoiseGenerator`](#classUniformNoiseGenerator_1a337fb04cd2395de389ee6918ed2b6f54)`()` | 
`public inline void `[`StartProduce`](#classUniformNoiseGenerator_1a29597ad355345a8121f2ffc2d709dae3)`()` | 
`public inline void `[`StopProduce`](#classUniformNoiseGenerator_1abbf991a8aac279bbb5b7afb686d57ba8)`()` | 
`public inline int `[`GenerateNoise`](#classUniformNoiseGenerator_1a6caf923bb95b14f09a8cc7c1bee20fdd)`()` | 
`public inline int `[`AddNoise2Buffer`](#classUniformNoiseGenerator_1a051db44452897a81c4e743efaa6aa292)`(`[`Tensor`](#classTensor)`< DTYPE > * noise)` | 
`public inline `[`Tensor`](#classTensor)`< DTYPE > * `[`GetNoiseFromBuffer`](#classUniformNoiseGenerator_1a5a290c30855ab3b7e45b7fcc03240a5d)`()` | 
`public inline virtual int `[`ForwardPropagate`](#classUniformNoiseGenerator_1a14a686b99bb811bb7bf8bfeaf8ddba8c)`(int pTime)` | 
`public inline virtual int `[`BackPropagate`](#classUniformNoiseGenerator_1a5165db89c318df8f72e73b4fa3f14be7)`(int pTime)` | 

## Members

#### `public inline  `[`UniformNoiseGenerator`](#classUniformNoiseGenerator_1a95696eba2f5b4068da94b4227503a02f)`(int pTimeSize,int pBatchSize,int pChannelSize,int pRowSize,int pColSize,float pLowerLimit,float pUpperLimit,IsUseTime pAnswer,std::string pName)` {#classUniformNoiseGenerator_1a95696eba2f5b4068da94b4227503a02f}

#### `public inline  `[`~UniformNoiseGenerator`](#classUniformNoiseGenerator_1a337fb04cd2395de389ee6918ed2b6f54)`()` {#classUniformNoiseGenerator_1a337fb04cd2395de389ee6918ed2b6f54}

#### `public inline void `[`StartProduce`](#classUniformNoiseGenerator_1a29597ad355345a8121f2ffc2d709dae3)`()` {#classUniformNoiseGenerator_1a29597ad355345a8121f2ffc2d709dae3}

#### `public inline void `[`StopProduce`](#classUniformNoiseGenerator_1abbf991a8aac279bbb5b7afb686d57ba8)`()` {#classUniformNoiseGenerator_1abbf991a8aac279bbb5b7afb686d57ba8}

#### `public inline int `[`GenerateNoise`](#classUniformNoiseGenerator_1a6caf923bb95b14f09a8cc7c1bee20fdd)`()` {#classUniformNoiseGenerator_1a6caf923bb95b14f09a8cc7c1bee20fdd}

#### `public inline int `[`AddNoise2Buffer`](#classUniformNoiseGenerator_1a051db44452897a81c4e743efaa6aa292)`(`[`Tensor`](#classTensor)`< DTYPE > * noise)` {#classUniformNoiseGenerator_1a051db44452897a81c4e743efaa6aa292}

#### `public inline `[`Tensor`](#classTensor)`< DTYPE > * `[`GetNoiseFromBuffer`](#classUniformNoiseGenerator_1a5a290c30855ab3b7e45b7fcc03240a5d)`()` {#classUniformNoiseGenerator_1a5a290c30855ab3b7e45b7fcc03240a5d}

#### `public inline virtual int `[`ForwardPropagate`](#classUniformNoiseGenerator_1a14a686b99bb811bb7bf8bfeaf8ddba8c)`(int pTime)` {#classUniformNoiseGenerator_1a14a686b99bb811bb7bf8bfeaf8ddba8c}

#### `public inline virtual int `[`BackPropagate`](#classUniformNoiseGenerator_1a5165db89c318df8f72e73b4fa3f14be7)`(int pTime)` {#classUniformNoiseGenerator_1a5165db89c318df8f72e73b4fa3f14be7}

# class `VanillaGANDiscriminatorLoss` {#classVanillaGANDiscriminatorLoss}

```
class VanillaGANDiscriminatorLoss
  : public LossFunction< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`VanillaGANDiscriminatorLoss`](#classVanillaGANDiscriminatorLoss_1a768fb6d1ee98c8759f94d750bc020691)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE epsilon,std::string pName)` | 
`public inline  `[`VanillaGANDiscriminatorLoss`](#classVanillaGANDiscriminatorLoss_1ab388824430697310825a387f9f7abc7f)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | 
`public inline virtual  `[`~VanillaGANDiscriminatorLoss`](#classVanillaGANDiscriminatorLoss_1ae43cf40a77a9fe4d80cd9503e3960bd7)`()` | 
`public inline virtual int `[`Alloc`](#classVanillaGANDiscriminatorLoss_1a3e3a8ba187653fabfa7a58386118d0d3)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` | 
`public inline virtual void `[`Delete`](#classVanillaGANDiscriminatorLoss_1a36da0c69fb3af583ca096bdbd50dda36)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classVanillaGANDiscriminatorLoss_1a8780b4f5d982cae80f5daf9206c83675)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classVanillaGANDiscriminatorLoss_1ac458b5ad199bcf7d0945618ee36c02d5)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`VanillaGANDiscriminatorLoss`](#classVanillaGANDiscriminatorLoss_1a768fb6d1ee98c8759f94d750bc020691)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE epsilon,std::string pName)` {#classVanillaGANDiscriminatorLoss_1a768fb6d1ee98c8759f94d750bc020691}

#### `public inline  `[`VanillaGANDiscriminatorLoss`](#classVanillaGANDiscriminatorLoss_1ab388824430697310825a387f9f7abc7f)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classVanillaGANDiscriminatorLoss_1ab388824430697310825a387f9f7abc7f}

#### `public inline virtual  `[`~VanillaGANDiscriminatorLoss`](#classVanillaGANDiscriminatorLoss_1ae43cf40a77a9fe4d80cd9503e3960bd7)`()` {#classVanillaGANDiscriminatorLoss_1ae43cf40a77a9fe4d80cd9503e3960bd7}

#### `public inline virtual int `[`Alloc`](#classVanillaGANDiscriminatorLoss_1a3e3a8ba187653fabfa7a58386118d0d3)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` {#classVanillaGANDiscriminatorLoss_1a3e3a8ba187653fabfa7a58386118d0d3}

#### `public inline virtual void `[`Delete`](#classVanillaGANDiscriminatorLoss_1a36da0c69fb3af583ca096bdbd50dda36)`()` {#classVanillaGANDiscriminatorLoss_1a36da0c69fb3af583ca096bdbd50dda36}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classVanillaGANDiscriminatorLoss_1a8780b4f5d982cae80f5daf9206c83675)`(int pTime)` {#classVanillaGANDiscriminatorLoss_1a8780b4f5d982cae80f5daf9206c83675}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classVanillaGANDiscriminatorLoss_1ac458b5ad199bcf7d0945618ee36c02d5)`(int pTime)` {#classVanillaGANDiscriminatorLoss_1ac458b5ad199bcf7d0945618ee36c02d5}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

# class `VanillaGANGeneratorLoss` {#classVanillaGANGeneratorLoss}

```
class VanillaGANGeneratorLoss
  : public LossFunction< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`VanillaGANGeneratorLoss`](#classVanillaGANGeneratorLoss_1ab47c3b1dd2a1f56e0696aac2b049c2b0)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE epsilon,std::string pName)` | 
`public inline  `[`VanillaGANGeneratorLoss`](#classVanillaGANGeneratorLoss_1ae1e28b7beedc4e546d029fe86c63ea88)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | 
`public inline virtual  `[`~VanillaGANGeneratorLoss`](#classVanillaGANGeneratorLoss_1a3e44ac1c339ec64db012d52ec9013b82)`()` | 
`public inline virtual int `[`Alloc`](#classVanillaGANGeneratorLoss_1a0fd0a5418cfa5c5d17807b583702d84b)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` | 
`public inline virtual void `[`Delete`](#classVanillaGANGeneratorLoss_1a3e7e87cd9571a031b4706d8c20819857)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classVanillaGANGeneratorLoss_1ae6499cffcfe3ca5755b10eea036bec58)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classVanillaGANGeneratorLoss_1ab6bff598db3fd349585638e0efb47c6a)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`VanillaGANGeneratorLoss`](#classVanillaGANGeneratorLoss_1ab47c3b1dd2a1f56e0696aac2b049c2b0)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,DTYPE epsilon,std::string pName)` {#classVanillaGANGeneratorLoss_1ab47c3b1dd2a1f56e0696aac2b049c2b0}

#### `public inline  `[`VanillaGANGeneratorLoss`](#classVanillaGANGeneratorLoss_1ae1e28b7beedc4e546d029fe86c63ea88)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classVanillaGANGeneratorLoss_1ae1e28b7beedc4e546d029fe86c63ea88}

#### `public inline virtual  `[`~VanillaGANGeneratorLoss`](#classVanillaGANGeneratorLoss_1a3e44ac1c339ec64db012d52ec9013b82)`()` {#classVanillaGANGeneratorLoss_1a3e44ac1c339ec64db012d52ec9013b82}

#### `public inline virtual int `[`Alloc`](#classVanillaGANGeneratorLoss_1a0fd0a5418cfa5c5d17807b583702d84b)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,DTYPE epsilon)` {#classVanillaGANGeneratorLoss_1a0fd0a5418cfa5c5d17807b583702d84b}

#### `public inline virtual void `[`Delete`](#classVanillaGANGeneratorLoss_1a3e7e87cd9571a031b4706d8c20819857)`()` {#classVanillaGANGeneratorLoss_1a3e7e87cd9571a031b4706d8c20819857}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classVanillaGANGeneratorLoss_1ae6499cffcfe3ca5755b10eea036bec58)`(int pTime)` {#classVanillaGANGeneratorLoss_1ae6499cffcfe3ca5755b10eea036bec58}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classVanillaGANGeneratorLoss_1ab6bff598db3fd349585638e0efb47c6a)`(int pTime)` {#classVanillaGANGeneratorLoss_1ab6bff598db3fd349585638e0efb47c6a}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

# class `WData` {#classWData}

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public DTYPE * `[`m_aData`](#classWData_1ad36845cd4699b9ab85a5ca524ab912aa) | 
`public int `[`m_capacity`](#classWData_1af06220886bb98127c3e3105f91763ba4) | 
`public inline  `[`WData`](#classWData_1a50e554ad7f5d167bf60b3e863742d304)`(DTYPE * data,int capacity)` | 
`public inline virtual  `[`~WData`](#classWData_1af665dc6eab06ac705fa3d08b83534634)`()` | 
`public inline virtual DTYPE * `[`GetData`](#classWData_1ae93432315649b12c3dbd834c4440df64)`()` | 
`public inline virtual int `[`GetCapacity`](#classWData_1af8f92f28b659824b59a55eabfde4cd0a)`()` | 
`public inline DTYPE & `[`operator[]`](#classWData_1a649cada43f6bedfd6039a59c52fecf19)`(int idx)` | 

## Members

#### `public DTYPE * `[`m_aData`](#classWData_1ad36845cd4699b9ab85a5ca524ab912aa) {#classWData_1ad36845cd4699b9ab85a5ca524ab912aa}

#### `public int `[`m_capacity`](#classWData_1af06220886bb98127c3e3105f91763ba4) {#classWData_1af06220886bb98127c3e3105f91763ba4}

#### `public inline  `[`WData`](#classWData_1a50e554ad7f5d167bf60b3e863742d304)`(DTYPE * data,int capacity)` {#classWData_1a50e554ad7f5d167bf60b3e863742d304}

#### `public inline virtual  `[`~WData`](#classWData_1af665dc6eab06ac705fa3d08b83534634)`()` {#classWData_1af665dc6eab06ac705fa3d08b83534634}

#### `public inline virtual DTYPE * `[`GetData`](#classWData_1ae93432315649b12c3dbd834c4440df64)`()` {#classWData_1ae93432315649b12c3dbd834c4440df64}

#### `public inline virtual int `[`GetCapacity`](#classWData_1af8f92f28b659824b59a55eabfde4cd0a)`()` {#classWData_1af8f92f28b659824b59a55eabfde4cd0a}

#### `public inline DTYPE & `[`operator[]`](#classWData_1a649cada43f6bedfd6039a59c52fecf19)`(int idx)` {#classWData_1a649cada43f6bedfd6039a59c52fecf19}

# class `WGANDiscriminatorLoss` {#classWGANDiscriminatorLoss}

```
class WGANDiscriminatorLoss
  : public LossFunction< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`WGANDiscriminatorLoss`](#classWGANDiscriminatorLoss_1a4c87bb209bfcd5200f4eed964db52e08)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | 
`public inline virtual  `[`~WGANDiscriminatorLoss`](#classWGANDiscriminatorLoss_1a33c614cb3dc1b874b3509ed6a4086b27)`()` | 
`public inline virtual int `[`Alloc`](#classWGANDiscriminatorLoss_1ad02ab0e0cb15d1da8aabb3b397c1e203)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` | 
`public inline virtual void `[`Delete`](#classWGANDiscriminatorLoss_1a2d10a3616ed329476fca86bf91eba47d)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classWGANDiscriminatorLoss_1ad788399d3f79109e938873c1217c4fda)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classWGANDiscriminatorLoss_1a1ebcb93edef6fee4c8a05cadfdfd4b4c)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`WGANDiscriminatorLoss`](#classWGANDiscriminatorLoss_1a4c87bb209bfcd5200f4eed964db52e08)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classWGANDiscriminatorLoss_1a4c87bb209bfcd5200f4eed964db52e08}

#### `public inline virtual  `[`~WGANDiscriminatorLoss`](#classWGANDiscriminatorLoss_1a33c614cb3dc1b874b3509ed6a4086b27)`()` {#classWGANDiscriminatorLoss_1a33c614cb3dc1b874b3509ed6a4086b27}

#### `public inline virtual int `[`Alloc`](#classWGANDiscriminatorLoss_1ad02ab0e0cb15d1da8aabb3b397c1e203)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` {#classWGANDiscriminatorLoss_1ad02ab0e0cb15d1da8aabb3b397c1e203}

#### `public inline virtual void `[`Delete`](#classWGANDiscriminatorLoss_1a2d10a3616ed329476fca86bf91eba47d)`()` {#classWGANDiscriminatorLoss_1a2d10a3616ed329476fca86bf91eba47d}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classWGANDiscriminatorLoss_1ad788399d3f79109e938873c1217c4fda)`(int pTime)` {#classWGANDiscriminatorLoss_1ad788399d3f79109e938873c1217c4fda}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classWGANDiscriminatorLoss_1a1ebcb93edef6fee4c8a05cadfdfd4b4c)`(int pTime)` {#classWGANDiscriminatorLoss_1a1ebcb93edef6fee4c8a05cadfdfd4b4c}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

# class `WGANGeneratorLoss` {#classWGANGeneratorLoss}

```
class WGANGeneratorLoss
  : public LossFunction< DTYPE >
```  

## Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`WGANGeneratorLoss`](#classWGANGeneratorLoss_1a8341d62f2b2a4bec46a9d4eb96c2c133)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` | 
`public inline virtual  `[`~WGANGeneratorLoss`](#classWGANGeneratorLoss_1a5ec911513d25ec26884a709ef60e79fd)`()` | 
`public inline virtual int `[`Alloc`](#classWGANGeneratorLoss_1a3e5b65237ee97ba99a6b16fbe75bf19d)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` | 
`public inline virtual void `[`Delete`](#classWGANGeneratorLoss_1a28dabeaf32a7d7ec03b0e84ccd8a322d)`()` | 동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classWGANGeneratorLoss_1a5354d9a780b8be53775610526787b3ec)`(int pTime)` | LossFunction의 순전파를 수행하는 메소드
`public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classWGANGeneratorLoss_1a36f645111dde1d73aa924ed539486286)`(int pTime)` | LossFunction의 역전파를 수행하는 메소드

## Members

#### `public inline  `[`WGANGeneratorLoss`](#classWGANGeneratorLoss_1a8341d62f2b2a4bec46a9d4eb96c2c133)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator,`[`Operator`](#classOperator)`< DTYPE > * pLabel,std::string pName)` {#classWGANGeneratorLoss_1a8341d62f2b2a4bec46a9d4eb96c2c133}

#### `public inline virtual  `[`~WGANGeneratorLoss`](#classWGANGeneratorLoss_1a5ec911513d25ec26884a709ef60e79fd)`()` {#classWGANGeneratorLoss_1a5ec911513d25ec26884a709ef60e79fd}

#### `public inline virtual int `[`Alloc`](#classWGANGeneratorLoss_1a3e5b65237ee97ba99a6b16fbe75bf19d)`(`[`Operator`](#classOperator)`< DTYPE > * pOperator)` {#classWGANGeneratorLoss_1a3e5b65237ee97ba99a6b16fbe75bf19d}

#### `public inline virtual void `[`Delete`](#classWGANGeneratorLoss_1a28dabeaf32a7d7ec03b0e84ccd8a322d)`()` {#classWGANGeneratorLoss_1a28dabeaf32a7d7ec03b0e84ccd8a322d}

동적으로 할당받은 LossFunction의 멤버 변수들을 할당 해제하는 메소드

Result와 Gradient에 해당하는 Tensor들의 메모리를 할당 해제한다. 
#### Returns
없음

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`ForwardPropagate`](#classWGANGeneratorLoss_1a5354d9a780b8be53775610526787b3ec)`(int pTime)` {#classWGANGeneratorLoss_1a5354d9a780b8be53775610526787b3ec}

LossFunction의 순전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

#### `public inline virtual `[`Tensor`](#classTensor)`< DTYPE > * `[`BackPropagate`](#classWGANGeneratorLoss_1a36f645111dde1d73aa924ed539486286)`(int pTime)` {#classWGANGeneratorLoss_1a36f645111dde1d73aa924ed539486286}

LossFunction의 역전파를 수행하는 메소드

#### Parameters
* `pTime` 학습 데이터 텐서의 Time 인덱스, 값을 전달하지 않을 시 0으로 초기화 됨 

#### Returns
NULL

Generated by [Moxygen](https://sourcey.com/moxygen)