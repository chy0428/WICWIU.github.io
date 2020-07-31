# WICWIU.github.io

[**WICWIU Github Pages**](https://wicwiu.github.io/) 는 [**WICWIU**](https://github.com/WICWIU/WICWIU) 와 관련된 내용들을 정리해둔 문서입니다.

*[**WICWIU Github Pages**](https://wicwiu.github.io/) 를 클릭해주세요!*

## Why?

한동대학교 학부생 주도로 제작된 딥러닝 프레임워크 **WICWIU** 프로젝트에 참여하기 위해서는 **(1)** 방대한 양의 **C++** 코드와 **(2)** 그 코드에 구현되어 있는 딥러닝 기술들, **(3)** **GPU** 코딩을 위한 **CUDA** 프로그래밍 기술들, **(4)** 협업을 위한 **Git**, **Github**, **Pull Requests**, **(5)** [Coding Convention](https://en.wikipedia.org/wiki/Coding_conventions) 에 대한 이해, **(6)** **C++** 코딩을 위하여 주의해야 할 내용들, **(7)** `Makefile` 에 대한 이해, 기타등등이 필요합니다.

하지만 이렇게 **WICWIU** 개발에 필요한 내용들이 지금까지 전임 개발자에 의하여 인수인계되서 **(1)** 일관된 내용으로 전달되지 않거나 문서(`.docx` 또는 `.pdf` 파일)에 의하여 전달되었기에 **(2)** 접근성이 떨어졌습니다.

이 두 가지 문제를 해결하기 위하여 **WICWIU** 프로젝트에 참여하기 위한 **(1)** 일관성 있는 통일된 내용을, **(2)** 접근성이 우수한 플랫폼에 게시할 필요가 있습니다. 이러한 조건을 모두 충족시켜주는 플랫폼은 [Github Pages](https://pages.github.com/) 입니다.

또 이 [**WICWIU Github Pages**](https://wicwiu.github.io/) 로써 **WICWIU** 에 참여하고 싶지만 자신에게 어떤 것이 부족한지 몰라서 막연한 두려움을 갖고 있는 한동대생들에게 무엇이 필요하고 어떤 지식들이 있어야 하는지 명확하게 알려줌으로써 **WICWIU** 참여에 자신감과 확신을 심어줄 수도 있을 것 같습니다.

## How?

**WICWIU** 개발자들은 **WICWIU** 에 참여하기 위하여 필요한 내용을 **Markdown** 형식으로 작성하고 `commit` 후 `push` 하기만 하면 됩니다. 만약 자신이 **RNN** 을 만들었다면 **RNN** 을 후배들이 물려받아서 잘 개발할 수 있도록 필요하고 충분한 내용을 작성하는 것이지요.

그러면 자동으로 필요한 처리들을 다 하고 [Github Pages](https://pages.github.com/) 에 잘 업로드되도록 [**CI**](.github/workflows/ci.yml) 파일을 설정해두었습니다.

## TODO 

[**WICWIU Github Pages**](https://wicwiu.github.io/) 에 작성할 것들을 메모해둔 것입니다.

- 코딩 생산성 높이기 & 여러가지 필수 기술들

  - Docker : https://github.com/ccss17/ProgrammerBase/blob/master/docker.md

  - Git : https://github.com/ccss17/ProgrammerBase/blob/master/git.md

  - Markdown : https://github.com/ccss17/ProgrammerBase/blob/master/markdown.md

  - VSCode 와 Git 연동해서 겁나 편하게 사용하기 : https://github.com/ccss17/ProgrammerBase/blob/master/vscode.md

  - 딥러닝 할때 tmux 로 편하게 하기 : https://github.com/ccss17/ProgrammerBase/blob/master/tmux.md

  - 시스템 모니터링 : https://github.com/ccss17/ProgrammerBase/blob/master/cli.md
  
    - 시스템 모니터링 top &rarr; htop &rarr; gotop
    
    - GPU 모니터링 nvidia-smi &rarr; nvtop

- CUDA 프로그래밍

  - https://cuda-tutorial.readthedocs.io/en/latest/

  - https://docs.nvidia.com/cuda/

  - https://ericzhng.github.io/eric-blogs/2018/10/11/vs-code-cuda/

  - https://github.com/Jokeren/Awesome-GPU

  - https://github.com/Erkaman/Awesome-CUDA

- [makefile](https://ccss17.github.io/makefile.html)

- [how to understand large c++ code](https://www.google.com/search?client=firefox-b-d&q=how+to+understand+large+c%2B%2B+code)

- [아무도 가르쳐 주지 않는 것](https://velog.io/@mowinckel/%EC%95%84%EB%AC%B4%EB%8F%84-%EA%B0%80%EB%A5%B4%EC%B3%90-%EC%A3%BC%EC%A7%80-%EC%95%8A%EB%8A%94-%EA%B2%83?fbclid=IwAR33Cn25eV-5MaqBWZPhA5uj_bReJLRVbhn6yewssYsh2tGO38T-iTDxnFQ)

- [WICWIU Documentation](https://github.com/WICWIU/WICWIU/tree/master/Documentation) 포팅

- [Google C++ Style](https://google.github.io/styleguide/cppguide.html) 

- C++ 

  - [C++ 코딩시 주의해야 할 것 내가 메모한 것](https://gist.github.com/ccss17/0ea062252bce9f2c26cfdcb7e2f99b2c)

  - [modern-cpp-features](https://github.com/AnthonyCalandra/modern-cpp-features)

  - https://github.com/isocpp/CppCoreGuidelines

  - https://github.com/lefticus/cppbestpractices

- Memory Leak

  - https://github.com/google/sanitizers

- Allreduce-ring Multi-GPU 

  - https://towardsdatascience.com/visual-intuition-on-ring-allreduce-for-distributed-deep-learning-d1f34b4911da

  - https://github.com/baidu-research/baidu-allreduce

  - https://github.com/microsoft/DeepSpeed