
**Markdown** 은 [여러가지 형식으로 텍스트를 작성할 수 있게 해주는 마크업 언어](https://en.wikipedia.org/wiki/Markdown)입니다. **Markdown** 파일은 확장자 `.md` 를 갖고 있습니다. **Markdown** 을 알아야 하는 주된 이유 중 하나는 레포지토리를 **Github** 에 공유할 때 프로그램을 효과적으로 설명하기 위해서입니다. 

**Markdown** 이 얼마나 효과적인 포맷팅 기능을 제공하는지는 지금 읽고 있는 이 파일들이 전부다 `.md` 파일인 것만 보아도 알 수 있습니다. **Markdown** 의 문법은 매우 간단하지만 매우 다양한 기능을 제공합니다. 

Markdown 파일의 기초 문법을 모르신다면 먼저 [이곳](https://github.com/ccss17/ProgrammerBase/blob/master/markdown.md)을 참고해주세요. 

!!! note

    더 자세한 **Markdown** 의 문법을 알아보려면 **Google** 에 검색하거나

    - [Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

    - [markdown-it](https://markdown-it.github.io/)

    을 참고하세요.

## 문서 추가하기

Markdown 파일의 기초 문법을 이해하였다면, [WICWIU Github Page](https://github.com/WICWIU/WICWIU.github.io) 를 **fork** 하고 **clone** 한 다음 `docs` 디렉토리 밑에 `.md` 파일을 추가해주세요.

가령 **RNN** 을 설명하기 위한 파일을 작성하고 싶다면 `RNN.md` 을 `docs` 디렉토리에 추가하여 내용을 작성합니다.

이후 `mkdocs.yml` 에 

```
nav:
  - RNN: RNN.md
```

을 추가하면 됩니다. 

### 하위 카테고리에 문서 추가하기

문서를 **Neural Network** 라는 하위 카테고리에 추가하고 싶다면 다음과 같이 하면 됩니다.

```
nav:
  - Neural Network
    - RNN: RNN.md
```

## Preview

하지만 추가되거나 변경된 `.md` 파일들을 **commit** 하기 전에 꼭 추가된 `.md` 파일이 어떻게 랜더링되는지 **Preivew** 를 통해 확인해야 합니다. **Preview** 를 보는 방법은 다음과 같습니다. 

1. `pip install mkdocs-material` 명령어로 **MkDocs** 와 **Material for MkDocs** 를 설치합니다.

    !!! note

        **Windows** 시스템에서는 `python -m pip install mkdocs-material` 명령어를 실행해야 할 수도 있습니다.

2. `mkdocs serve` 를 실행합니다. 그러면 `http://localhost:8000` 에 **Preview** 서버가 열립니다. 

이곳에서 추가되거나 변경된 `.md` 파일이 원하는대로 잘 나오는지 확인해주세요. 그리고 **commit**, **push** 후 **Pull Requests** 를 하면 됩니다.
