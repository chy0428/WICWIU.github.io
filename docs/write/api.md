
[**WICWIU**](https://github.com/WICWIU/WICWIU) 는 [`doxygen`](https://www.doxygen.nl/index.html) 으로 API 를 자동생성합니다. `doxygen` 은 소스코드의 주석으로부터 **HTML**, **LaTex**, **XML** 등의 문서를 자동으로 생성해주는데, **Markdown** 형식은 지원하지 않습니다. 그래서 `doxygen` 으로 **XML** 형식의 API 를 생성한 다음 [`moxygen`](https://github.com/sourcey/moxygen) 으로 **Markdown** 으로 변환해주어야 합니다.

## HOW-TO

1. [**WICWIU**](https://github.com/WICWIU/WICWIU) 레포지토리를 **clone** 한 디렉토리에서 `doxygen -g` 를 실행합니다.

2. `Doxygen` 파일에서 `GENERATE_XML = no` 를 `GENERATE_XML = yes` 로 바꿉니다.

3. `doxygen Doxygen` 을 실행합니다.

4. `moxygen -a xml` 을 실행합니다. 그러면 `api.md` 파일이 생성됩니다.

## api.md 다듬기

하지만 생성된 `api.md` 를 곧바로 `mkdocs-material` 에 업로드하면 몇 가지 문제점이 있습니다. 클래스마다 있는 `## Summary` 와 `## Members` 가 Table-of-Contents 를 너무 더럽게 만들기 때문입니다. 따라서 `api.md` 파일에서 `## Summary` 와 `## Members` 를 `<h2> Summary </h2>` 와 `<h2> Members </h2>` 로 바꾸어 줍니다.

그리고 `api.md` 에는 다음과 같이 클래스 멤버를 설명하는데

````markdown
#### `public inline  `[`AdagradOptimizer`](#classAdagradOptimizer_1a57ec3fb8b88c955719598afba8dc7a85)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,OptimizeDirection pOptimizeDirection)` {#classAdagradOptimizer_1a57ec3fb8b88c955719598afba8dc7a85} 
````

헤더가 `####` 로 되어있어서 코드가 랜더링될 때 대문자로 랜더링됩니다. 이것을 해결하기 위하여 모든 ``` #### \` ``` 들을 ``` ### \` ``` 로 바꿉니다. 그러면 다음과 같이 바뀔 것입니다.

````markdown
### `public inline  `[`AdagradOptimizer`](#classAdagradOptimizer_1a57ec3fb8b88c955719598afba8dc7a85)`(`[`Container](#classContainer)< [Operator`](#classOperator)`< DTYPE > * > * pParameterContainer,float pLearningRate,OptimizeDirection pOptimizeDirection)` {#classAdagradOptimizer_1a57ec3fb8b88c955719598afba8dc7a85} 
````

그러면 업로드할 수 있는 `api.md` 가 완성됩니다.