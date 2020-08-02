# Git

코딩을 막 배우기 시작하면 종종 카톡이나 메일에 소스코드를 백업 하곤 합니다. 하지만 이 방식에는 몇 가지 단점이 있습니다. 먼저 소스코드의 저장장소가 매우 산발적이고 일관성이 없어서 매번 찾기가 힘듭니다. 그리고 소스코드의 변화과정을 제대로 이해하기 힘듭니다. 만약 백업하는 것도 잊어버리고 백업을 하지 않았다가 실수로 소스코드를 삭제해버린다면 복구할 수 있는 방법이 전혀 없습니다.

!!! danger

    이런 문제는 규모가 큰 단체 프로젝트에서 더 심각해집니다. 누가 무엇을 고쳤는지, 소스코드 저장소가 어디에 있는지, 만약 누가 실수로 소스코드를 지워버렸을 때 복구를 할 수 없을 때 기업은 실질적인 금전적인 피해를 받게 됩니다. 

이 문제를 해결하기 위해 나온 것이 **버전 컨트롤 시스템(Version Control System)** 입니다. 줄여서 **VCS** 는 단어 그대로 **"프로젝트의 버전을 손쉽게 다룰 수 있게 해주는 시스템"** 입니다. VCS 에는 여러 종류가 있지만 이제 우리는 그 중에서 가장 많이 사용되는 VCS 가 **Git** 입니다. [**WICWIU**](https://github.com/WICWIU/WICWIU) 도 **Git** 을 사용하여 관리되고 있기 때문에 [**WICWIU**](https://github.com/WICWIU/WICWIU) 개발에 참여하기 위해서는 **Git** 을 잘 이해해야 합니다.

여기에서는 **Git** 으로 협업하며 [**WICWIU**](https://github.com/WICWIU/WICWIU) 를 개발하는 법을 가볍게 살펴보겠습니다.

!!! warning "잠깐!!"

    **Git** 에 대한 기초가 없으신분들은 먼저 [이곳](https://github.com/ccss17/ProgrammerBase/blob/master/git.md) 을 통하여(*추천*), 또는 다른 **Git** 학습 자료를 통하여

    1. **Git** 이 파일을 관리하는 `4` 가지 상태(**untracked 상태, modified 상태, staged 상태, committed 상태**)

    2. **Github** 으로 **Git** 원격 레포지토리 관리하는 방법

    3. `.gitignore` 파일 관리하기

    4. **Git Branching** 과 충돌해결하기

    5. **Pull Requests** 하기

    를 먼저 이해하고 오시길 바랍니다.

## Git 과 Github 로 WICWIU 협업하기

**Git** 과 **Github** 로 [**WICWIU**](https://github.com/WICWIU/WICWIU) 를 협업하는 것은 다음과 같은 구조로 이루어집니다. 여기에서는 **RNN** 을 만들기 위하여 `RNN` 브랜치에서 개발을 한다고 가정하겠습니다.

1. [**WICWIU**](https://github.com/WICWIU/WICWIU) 를 **fork** 한다.

2. **fork** 한 자신의 레포지토리를 딥러닝 학습 환경에 **clone** 한다.

3. `RNN` 브랜치를 만들고 개발을 한 후 테스트가 끝나면 **commit** 하고 자신의 레포지토리로 **push** 한다. 

4. [**WICWIU**](https://github.com/WICWIU/WICWIU) 로 **Pull Requests** 를 한다.
