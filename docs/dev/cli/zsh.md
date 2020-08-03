

# `bash` ➜ `zsh` - 더 빨라진 쉘

`zsh` 은 수많은 플러그인과 테마가 지원되는 쉘입니다. 이제 `bash` 쉘을 그만 쓰고 `zsh` 을 사용해보겠습니다.

`zsh` 은 `oh-my-zsh` 을 설치해야만 그 진가를 발휘하는데, 그 설치법은 [튜토리얼](https://github.com/ccss17/ProgrammerBase/blob/master/cli.md#dotfiles) 에 이미 설명했기 때문에 여기에서는 `zsh` 을 사용하면 얼마나 생산성이 향상되는지만 가볍게 알아보겠습니다.

## 테마

`zsh` 은 정말 수많은 테마를 갖고 있습니다.

!!! tip 

    [https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes) 에 들어가서 마음에 드는 테마가 있는지 볼 수 있어요. 

제가 보여드릴 `zsh` 테마는 다음과 같은 [alien-minimal](https://github.com/eendroroy/alien-minimal) 입니다.

[<img src="http://asciinema.org/a/264037.svg" width="50%" height="auto">](https://asciinema.org/a/264037)

## `zsh` 기본 기능

`zsh` 테마는 단순히 `bash` 쉘 프롬프트보다 더 멋있기 때문에 사용해야 하는 것도 있지만 수많은 기능들도 제공하기 때문에 사용해야 합니다. 그 수많은 기능 중 다음 두 가지 기능만 알아보겠습니다. 

!!! note ""

    다음과 같이 `git` 브랜치를 프롬프트에 보여준다. 

    <img src="https://user-images.githubusercontent.com/16812446/81711439-a748ae00-94ae-11ea-87b3-2d044af66c6a.png" width="70%" height="auto">

    위와 같이 프롬프트 우측에 `master` 가 `dev` 로 바뀌고 다시 `master`로 바뀌었습니다.

    이렇게 `git` 으로 레포지토리를 관리하다가 실험적인 기능을 테스트해야 해서 새로운 `branch` 인 `dev` 를 만들고 이주했을 때, `zsh` 의 프롬프트가 우측에 현재 상주하고 있는 `branch` 정보를 알려줍니다. 

    그래서 매번 `git branch` 를 입력하여 현재 상주하고 있는 `branch` 가 어떤 건지 확인할 필요가 없습니다.

    프로그램의 리턴값이 정상값 `0` 이 아닐경우 프롬프트에 보여준다. 

    <img src="https://user-images.githubusercontent.com/16812446/81711915-0e666280-94af-11ea-9da8-d30192e5e16e.png" width="50%" height="auto">

    위와 같이 `ls` 명령어를 입력하면 정상 종료 코드 `0` 가 반환되지만 존재하지 않는 명령어 `lss` 가 입력되면 비정상 종료 코드 `127` 이 반환됩니다. 

    `zsh` 프롬프트는 그러한 비정상 종료 코드를 보여주고 프로그램이 비정상적으로 종료되었을 때 프롬프트 색깔을 다른 색깔로 바꿔줍니다. 

## `tab-completion` 기능

이 기능은 명령어의 부분만 입력하고 <kbd>Tab</kbd> 을 눌렀을 때 `zsh` 이 알아서 명령어를 추천해주는 기능입니다. 

!!! note ""

    다음과 같이 `cd` 만 누르고 <kbd>Tab</kbd> 을 누르면 명령어를 추천을 해주고, `cd` 를 선택하고 다시 <kbd>Tab</kbd> 을 누르니까 이동할 레포지토리를 추천해줍니다. 우리가 해야 할 일은 단지 <kbd>Enter</kbd> 를 누르는 것 뿐이죠. 

    ![render1589349092346](https://user-images.githubusercontent.com/16812446/81776326-98531180-9529-11ea-871e-d3001579bfe2.gif)

    다음과 같이 특정 디렉토리만 입력하고 나서 <kbd>Tab</kbd> 을 누르면 하위 디렉토리를 추천해줍니다. 

    ![render1589349132365](https://user-images.githubusercontent.com/16812446/81776480-cf292780-9529-11ea-8ffd-4e457a71e6de.gif)

## `auto-completion` 기능

이 기능은 사용자가 길고 복잡한 경로를 이동해야 할때 그것을 특정할 수 있는 문자만 입력하고 <kbd>Tab</kbd> 을 누르면 자동으로 완성해주는 `zsh` 의 기능입니다. 

!!! note ""

    `/usr/lib/gcc/x86_64-linux-gnu/9.3.0` 의 경로로 이동해야 하는 경우라고 가정하겠습니다.

    ```shell
    $ cd /usr/lib/gcc/x86_64-linux-gnu/9.3.0
    ```

    하지만 이건 너무 길어서 짜증나서 견딜 수가 없습니다. 그러니까 다음 명령어만 입력하고 <kbd>Tab</kbd> 을 누릅니다. 

    ```shell
    $ cd /u/l/g/x/9
    ```

    그러면 다음과 같이 `zsh` 이 경로를 지가 알아서 완성시켜 줍니다. 

    ![](https://user-images.githubusercontent.com/16812446/81776742-51b1e700-952a-11ea-986d-4169235ff0ef.gif)

## `z` 명령어 

`z` 명령어는 사용자가 자주 이동하는 디렉토리 경로의 통계를 내어서 사용자가 이동하는 경로를 특정할 수 있는 짧은 경로만 입력해도 이동할 수 있게끔 해주는 **너무너무 편리** 한 `zsh` 플러그인입니다. 

단 `z` 명령어를 사용하기 위해서는 반드시 한 번 이상은 그 경로로 이동한 적이 있어야 합니다. 왜냐하면 `z` 이 사용자가 이동한 경로를 분석하고 통계를 낼 기회를 줘야하기 때문이죠.

!!! note ""

    방금 전에 `/usr/lib/gcc/x86_64-linux-gnu/9.3.0` 라는 경로로 이동했었으니까 이 경로를 아마도 `9` 이 특정할 수 있을 것 같으니까 다음 명령어를 실행해봅니다. 

    ```shell
    $ z 9
    ```

    실행 결과는 다음과 같습니다. 

    ![render1589349777003](https://user-images.githubusercontent.com/16812446/81776971-d997f100-952a-11ea-8b23-0995cbb69876.gif)

## `auto-suggestions` 기능

이 기능은 가장 최근에 실행한 명령어를 기억하여 사용자가 그 명령어와 비슷한 타자를 친다면 자동으로 완성된 명령어를 추천해주는 `zsh` 플러그인입니다. 이 기능은 긴 명령어를 반복해야 할 때 **너무 편합** 니다.

사용법도 매우 간단합니다. 명령어를 입력하다 보면 `auto-suggestions` 이 희미한 글씨로 완성된 명령어를 추천하는데 그것을 실행하길 원했다면 <kbd>&rarr;</kbd> 를 눌러서 명령어를 완성시키면 됩니다.

만약 `auto-suggestions` 이 추천한 명령어 전부를 원하지 않고 부분적인 것만 원한다면 <kbd>Ctrl</kbd>+<kbd>&rarr;</kbd> 를 누르면 됩니다. 

!!! note ""

    도커 컨테이너를 여러번 종료했다가 재시작했어야만 했다면 `docker start -ai b` 와 같은 명령어를 반복적으로 입력했야 합니다.

    하지만 다음과 같이 `auto-suggestions` 이 반복되는 명령어를 추천해주기 때문에 매번 입력할 필요 없이 `d` 만 누르고 <kbd>&rarr;</kbd> 를 누르면 됩니다.
  
    `docker start -ai b` 을 일일이 다 입력해야 하는 것과 비교해봅니다.
  
    ![render1589350187427](https://user-images.githubusercontent.com/16812446/81777473-dcdfac80-952b-11ea-9936-0cc6df268b47.gif)