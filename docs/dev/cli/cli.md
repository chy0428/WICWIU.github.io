[**WICWIU**](https://github.com/WICWIU/WICWIU) 는 아직 **Linux** 시스템에서 실행되도록 개발되었기 때문에 [**WICWIU**](https://github.com/WICWIU/WICWIU) 를 **Linux** 시스템에서 개발하면서 디버깅을 해야 합니다. 

보통 자신의 컴퓨터가 **Linux** 가 아닐 뿐더러 강력한 **GPU** 환경도 구축되어 있지 않기 때문에 기계학습 전용 서버에서 [**WICWIU**](https://github.com/WICWIU/WICWIU) 를 개발하고 디버깅을 하게 됩니다. 

이때 필요한 것이 효과적인 **CLI(Command Line Interface)** 프로그램들입니다. 기존에 사용하던 `bash` 쉘, `ls` 명령어, `cat` 명령어, `find` 명령어, `top` 명령어, `man` 명령어, `python` 명령어 등은 사실 너무 오래전에 제작된 프로그램들이라 사용하기에 매우 불편합니다. 이것들을 새로운 **CLI** 프로그램들로 업그레이드하여 사용하기 매우 편하게 바꾸어 보겠습니다.

!!! note

    아래의 내용은 제가 [고스트 신입을 가르치기 위해 제작한 튜토리얼](https://github.com/ccss17/ProgrammerBase/blob/master/cli.md)을 [**WICWIU**](https://github.com/WICWIU/WICWIU) 개발자들에게 적합하도록 편집하여 재작성한 것입니다.

    특히 `nvtop` 은 [튜토리얼](https://github.com/ccss17/ProgrammerBase/blob/master/cli.md) 에는 없지만 [**WICWIU**](https://github.com/WICWIU/WICWIU) 개발자에게는 필요하기에 새롭게 추가하였습니다.

    아래의 내용의 CLI 프로그램 설치법은 원본 [튜토리얼](https://github.com/ccss17/ProgrammerBase/blob/master/cli.md) 을 참고해주세요. 여기에서는 CLI 유틸리티를 업그레이드하면 어떻게 생산성이 향상되는지 비교만 해보겠습니다.

## `alias`

먼저 다음과 같이 `alias` 를 지정하면 명령어 입력 시간을 획기적으로 줄일 수 있습니다.

|`alias`|`command`|
|:---|:---|
|`t`|`tmux`|
|`v`|`vim`|
|`c`|`clear`|
|`cs`|`cd ..`|
|`ls`|`lsd --icon never`|
|`cl`|`clear;ls`|
|`l`|`ls`|
|`la`|`ls -a`|
|`ll`|`ls -la`|
|`lt`|`ls --tree`|
|`g`|`git`|
|`q`|`exit`|

!!! info

    `alias t=tmux` 명령어로 `alias` 를 지정할 수 있습니다. 하지만 이것을 매번 로그인할 때마다 입력하기 귀찮기 때문에 `zsh` 쉘 사용 유저라면 `.zshrc` 또는 `.zsh_aliases` 에

    ```shell
    alias t=tmux
    alias v=vim
    alias c=clear
    alias cs='cd ..'
    alias ls='lsd --icon never'
    alias cl='clear;ls'
    alias l='ls'
    alias la='ls -a'
    alias ll='ls -la'
    alias lt='ls --tree'
    alias g='git'
    alias q='exix'
    ```

    을 입력해두면 됩니다. `bash` 쉘 사용 유저라면 `.bashrc` 또는 `.bash_aliases` 에 입력하면 되는 것입니다.

# 더 빨라진 git

`git` 은 지원하는 지능이 하도 많다보니 내부적으로 `alias` 를 지원합니다. 가령 `git commit -m` 이라는 명령어를 매번 입력하기가 너무 귀찮아서 견딜 수가 없으니까 다음 명령어를 입력하여 `alias` 를 지정할 수 있습니다. 

```shell
$ g config --global alias.cm "commit -m"
```

!!! info 

    `alias` 에서 `alias g=git` 으로 `git` 의 에일리어스 `g` 를 설정했었기 때문에 `git` 이 아닌 `g` 만 입력해도 됩니다. 

그러면 이제부터 우리는 `git commit -m` 이 아니라 `g cm` 만 입력해도 되는 것입니다. 저의 [:octicons-file-code-24: `dotfiles` 레포지토리](https://github.com/ccss17/dotfiles-cli) 의 [:octicons-file-code-24: .tmux.conf](https://github.com/ccss17/dotfiles-cli/blob/master/.gitconfig) 에는 이런 `git` 의 `alias` 들이 이미 설정되었습니다. 

이 파일을 `~/.gitconfig` 에 위치시키기만 하면 `git alias` 들이 단번에 설정됩니다.

`git` 의 `alias` 가 매우 많이 설정되어 있지만 그중에서 주요한 `alias` 들은 다음과 같습니다. 

|`alias`|원래 명령어|완성된 명령어|의미|
|:---|:---|:---|:---|
|`i`|`init`|`g i`|`git` 레포지토리 관리를 시작하도록 한다.|
|`s`|`status`|`g s`|레포지토리 상태를 본다.|
|`sb`|`status -s -b`|`g sb`|레포지토리 상태를 간략하게 본다.|
|`cm`|`commit -m`|`g cm "<MESSAGE>"`|커밋을 한다.|
|`a`|`add --all`|`g a`|추가되거나 변경된 파일을 스테이징 한다.|
|`l`|`log --oneline`|`g l`|`git` 의 커밋 기록을 한줄씩 출력한다.|
|`lg`|`log --oneline --graph --decorate`|`g lg`|`git` 의 커밋 기록을 그래프로 출력한다.|
|`rao`|`remote add origin`|`g rao <REMOTE>`|원격 레포지토리를 추가한다.|
|`cl`|`clone`|`g cl <URL>`|원격 레포지토리를 복제해 온다.|
|`psom`|`push origin master`|`g psom`|원격 레포지토리로 푸쉬한다.|
|`plom`|`pull origin master`|`g plom`|원격 레포지토리를 가져온다.|
|`b`|`branch`|`g b <BRANCH>`|브랜치를 생성한다.|
|`bd`|`branch -d`|`g bd <BRANCH>`|브랜치를 삭제한다.|
|`m`|`merge`|`g m`|작업이 완료된 브랜치를 병합한다.|
|`o`|`checkout`|`g o <BRANCH>`|브랜치로 이동한다.|
|`ob`|`checkout -b`|`g ob <BRANCH>`|브랜치를 생성함과 동시에 이동한다.|

이로써 `git` 으로 레포지토리를 관리하는 레퍼토리인 다음의 명령어들을 획기적으로 단축시킬 수 있습니다.

```shell
$ mkdir git-test
$ cd git-test
$ git init
$ touch test.txt
$ git status
$ git add test.txt
$ git status
$ git commit -m "my first commit"
$ git status
$ echo "My test memo" > test.txt
$ cat test.txt
My test memo
$ git add .
$ git commit -m "My memo file"
$ git log
$ git remote add origin https://github.com/<USER>/git-test
$ git push -u origin master
$ cd  
$ git clone https://github.com/<USER>/git-test git-test-remote
$ cd git-test-remote
$ echo "very important message" > test.txt
$ git add .
$ git commit -m "very important file.."
$ git push origin master
$ cd ~/git-test
$ cat test.txt
$ git pull origin master
$ cat test.txt
```

위와 같은 명령어를 `alias` 로 단축해서 다시 입력해보 명령어가 정말 빠르게 입력됩니다. 

```shell
$ cd
$ mkdir alias-test
$ cd alias-test
$ g i
$ touch test.txt
$ g s
$ g a
$ g s
$ g cm "init"
$ g s
$ echo "My test memo" > test.txt
$ bat test.txt
$ g a
$ g cm "memo"
$ g l
$ g rao https://github.com/<USER>/alias-test
$ g psom
$ cd  
$ g cl https://github.com/<USER>/alias-test alias-test-remote
$ cd alias-test-remote
$ echo "message" > test.txt
$ g a
$ g cm "important file"
$ g psom
$ cd ~/alias-test
$ bat test.txt
$ g plom
$ bat test.txt
```

이로써 다음과 같이 `213` 타를 쳐야 했던 것을 `79` 타만 칠 수 있도록 대폭 절약을 해보았습니다.

|원래 명령어|`alias` 명령어|
|:---|:---|
|`git init`|`g i`|
|`git status`|`g s`|
|`git add`|`g a`|
|`git status`|`g s`|
|`git commit -m`|`g cm `|
|`git status`|`g s`|
|`git add .`|`g a`|
|`git commit -m`|`g cm`|
|`git log`|`g l`|
|`git remote add`|`g rao`|
|`git push -u origin master`|`g psom`|
|`git clone`|`g cl`|
|`git add .`|`g a`|
|`git commit`|`g cm`|
|`git push origin master`|`g psom`|
|`git pull origin master`|`g plom`|
|**총합 `213` 개**|**총합 `79` 개**|

이러한 `git` 레포지토리 관리 패턴은 코딩을 할 때마다 반복되는데, 이 패턴을 개발자로 살아가면서 적게 잡아서 **10000** 번 반복한다고 한다면, 여러분은 **10000 * 213 = 2백 13만** 번 칠 것을 **10000 * 79 = 79만** 만쳤습니다. 

즉, 똑같은 일을 하는데 **134만** 번의 타자를 안 친것입니다!

# CLI 업그레이드

## `ls` ➜ `lsd`

**[`lsd`](https://github.com/Peltoche/lsd)** 는 구식인 `ls` 명령어를 최신식으로 대체한 프로그램입니다. `ls` 와 `lsd` 를 비교해보겠습니다.

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/81694909-dd7d3200-949c-11ea-902b-d0d11c496f44.png" width="50%" height="auto">
</div>

`lsd` 는 컬러풀하게 출력결과를 보여줘서 가독성이 훨씬 올려줍니다. 

!!! info

    `lsd --icon never` 에서 `--icon never` 옵션은 아이콘을 출력하지 않는 옵션입니다. 이는 순수 CLI 환경에서 필요한 옵션이기 때문에 만약 GUI 환경(**macOS** 이나 리눅스 데스크탑 환경)에서 아이콘을 설치하고 `--icon never` 옵션을 제거하고 `lsd` 를 실행하면 다음과 같이 아이콘도 함께 출력되어 가독성이 훨씬 올라가는 것을 알 수 있습니다. 

    <div align="center">
    <img src="https://user-images.githubusercontent.com/16812446/81695205-45cc1380-949d-11ea-96e9-21f0f3c56dca.png" width="50%" height="auto">
    </div>

## `cat` ➜ `bat`

**[`bat`](https://github.com/Peltoche/lsd)** 는 구식인 `cat` 명령어를 최신식으로 대체한 프로그램입니다. 그럼 `cat` 와 `bat` 를 비교해봅시다. 

`cat` 이 다음과 같이 밋밋하게 출력되는 반면,

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/81692467-672b0080-9499-11ea-9b6e-7a8c72773467.png" width="40%" height="auto">
</div>


`bat` 이 다음과 같이 컬러풀하게 출력됩니다. 

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/81692558-8c1f7380-9499-11ea-9ef7-c3ed402a14f8.png" width="40%" height="auto">
</div>

!!! tip

    `bat` 은 `more` 이나 `less` 처럼 <kbd>e</kbd> 와 <kbd>y</kbd> 를 누르면 위아래로 움직일 수 있고 <kbd>Spacebar</kbd> 와 <kbd>u</kbd> 를 누르면 페이지 단위로 위아래로 이동할 수 있으며 `vim` 처럼 `/` 로 특정 문자열을 검색할 수 있고 `q` 로 종료할 수 있습니다. 

## `find` ➜ `fd`

**[`fd`](https://github.com/sharkdp/fd)** 는 구식인 `find` 명령어를 최신식으로 대체한 프로그램입니다. `fd` 는 `find` 보다 **5배** 정도 빠르고 좀 더 유저들이 사용하기 편하도록 인터페이스가 대폭 개선된 모던한 프로그램입니다. 

`fd` 는 `find` 와 상세하게 비교하기보다 다음의 사용예를 가볍게 한번 살펴보는 것으로 마무리하겠습니다. 

<figure>
  <img src="https://raw.githubusercontent.com/sharkdp/fd/master/doc/screencast.svg?sanitize=true" width="70%" />
  <figcaption><i>이미지 출처 : https://github.com/sharkdp/fd</i></figcaption>
</figure>

`fd` 의 상세한 설명을 알고 싶다면 공식 레포지토리 [https://github.com/sharkdp/fd](https://github.com/sharkdp/fd) 를 참고해주세요.

## `top` ➜ `htop` ➜ `gotop`

`top` 명령어는 시스템의 리소스 상태(RAM, CPU 등) 을 출력해주는 좋은 프로그램입니다. 기존의 `top` 은 다음과 같이 약간은 밋밋하게 시스템의 상태를 출력해주었습니다.

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/82143677-8f8f7200-9880-11ea-9f4e-7cbf6ed05b69.gif" width="50%" height="auto">
</div>

하지만 [`htop`](https://github.com/hishamhm/htop) 은 다음과 같이 색깔도 칠하고 메모리와 CPU 상태를 핸드폰 배터리 바처럼 보여줍니다. 

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/82143686-a3d36f00-9880-11ea-8b4c-941f6b640b1e.gif" width="50%" height="auto">
</div>

마지막으로 [`gotop`](https://github.com/cjbassi/gotop) 은 다음과 같이 완벽한 그래프로 시스템의 상태를 직관적으로 출력해줍니다.

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/82143720-f3b23600-9880-11ea-9f1b-7a24784cf541.gif" width="70%" height="auto">
</div>

!!! note

    시스템 상태를 출력해줄 수 있는 유틸리티는 개인적인 선호에 따라 좋고 나쁨이 결정되므로 확실히 어떤 게 좋다라고 말할 수 없습니다. 따라서 그냥 개인적으로 더 나은 것 같은 CLI 를 사용하면 됩니다. 

    전 개인적으로 `gotop` 이 직관적이고 좋더라구요. 

## `man` ➜ `tldr` 

`man` 은 명령어의 사용법을 출력하는 매우 좋은 프로그램입니다. 하지만 `man` 의 한 가지 단점은 그 사용법이 너무 방대하고 장황하다는 것입니다. 그래서 프로그램의 핵심 사용법을 쉽고 빠르게 알고 싶은 사용자들은 그 방대한 사용법에서 자신이 원하는 핵심 사용법을 이리저리 찾고 있어야만 했습니다. 

하지만 [`tldr`](https://github.com/tldr-pages/tldr) 은 `man` 처럼 방대한 사용법을 보여주는 것이 아니라 매우 간단한 핵심 사용법만을 알려줍니다. `tldr` 은 사용자들의 주도로 만들어져서 개발자들이 경험적으로 **"이게 가장 핵심적인 사용법이다!"** 라는 사용법만 간단하게 출력합니다.

`man` 으로 `tar` 명령어의 설명을 보고 싶다면 다음 명령어를 입력하면 됩니다.

```shell
$ man tar
```

그러면 다음과 같이 `tar` 의 **모든 사용법** 이 출력됩니다. 

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/82149528-ecdfef00-9891-11ea-8f14-4d98291fb144.png" width="70%" height="auto">
</div>

이런... 하지만 `man` 으로 `tar` 를 보니 설명이 매우 방대하고 매우 연역적으로, 그러니까 약간은 추상적으로 설명되어 있습니다. 그렇다면 이제 `tldr` 로 `tar` 의 사용법을 보겠습니다. 

```shell
$ tldr tar
```

그러면 다음과 같이 개발자들이 자주 사용하는 `tar` 의 핵심 기능들이 약간 귀납적으로, 즉 상당히 구체적으로 설명된 사용법이 출력됩니다. 

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/82149895-5829c100-9892-11ea-9147-b97e122a265c.png" width="70%" height="auto">
</div>

## `python` ➜ `bpython`

이번에는 파이썬 인터프리터 `python` 에 코드 하이라이팅과 자동완성 기능 등의 편리한 기능이 추가된 `bpython` 입니다.

기존의 파이썬 인터프리터는 다음과 같이 실행됬었습니다.

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/84473704-7b466580-acc4-11ea-99b0-c8b69d923f3c.gif" width="70%" height="auto">
</div>

하지만 `bpython` 을 사용하면 다음과 같이 코드 하이라이팅, 자동 완성, 함수 추천 기능, 자동 인덴트 등의 기능을 사용할 수 있습니다. 

<div align="center">
<img src="https://user-images.githubusercontent.com/16812446/84473719-84373700-acc4-11ea-91a8-d0985210e9ce.gif" width="70%" height="auto">
</div>

희미한 글씨로 자동 완성 추천 기능이 발동되면 방향키 <kbd>&rarr;</kbd> 를 눌러서 자동완성을 시켜보세요.

## `nvidia-smi` ➜ `nvtop`

[**WICWIU**](https://github.com/WICWIU/WICWIU) 를 개발하고 디버깅하기 위해서는 현재 **GPU** 상황을 모니터링해야 합니다. **GPU** 가 너무 덜 쓰이고 있는지, 아니면 너무 과하게 쓰여지고 있는지 확인해야 하고 다른 누군가 쓰고 있는 **GPU** 를 사용하지 않아야 하기 때문입니다. 

이때 보통은 `nvidia-smi` 프로그램을 사용하여 **GPU** 상황을 모니터링합니다. 하지만 `nvida-smi` 는 **GPU** 상황을 한 번 출력하고 끝나버리기 때문에 다음과 같이 `watch` 프로그램과 함께 사용됩니다.

```shell
$ watch -n 1 nvida-smi      # 1초에 한번 nvidia-smi 를 실행한다.
```

<div align="center">
<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89182713-27277580-d5d1-11ea-8dee-c323b20d180b.png" width="80%" />
  <figcaption><i>nvida-smi 실행 결과</i></figcaption>
</figure>
</div>

하지만 `nvtop` 은 **GPU** 상태를 그래프 형태로 나타내줄 뿐만 아니라 어떤 유저가 **GPU** 를 사용하는 프로세스를 실행했는지도 나타내줍니다.

```shell
$ nvtop
```

<div align="center">
<figure>
  <img src="https://user-images.githubusercontent.com/16812446/89182986-88e7df80-d5d1-11ea-864c-b939360bb417.png" width="150%" />
  <figcaption><i>nvida-smi 실행 결과</i></figcaption>
</figure>
</div>

## `nvtop` 설치

!!! note

    `nvtop` 프로그램의 설치법은 [튜토리얼](https://github.com/ccss17/ProgrammerBase/blob/master/cli.md) 에 나와있지 않기 때문에 여기에서 설명해드립니다.

`nvtop` 프로그램의 설치는 [이곳](https://github.com/Syllo/nvtop#distribution-specific-installation-process) 에 들어가서 시스템에 맞는 설치법을 따르면 됩니다.