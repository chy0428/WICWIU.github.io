# `tmux` 로 터미널 편하게 사용하기

지금까지 함께 살펴보았던 CLI 프로그램들로 **Linux** 시스템에서도 편하고 빠르게 개발을 할 수 있습니다. 하지만 거의 모든 개발 상황에서 터미널 창 하나는 부족합니다. 이때 `tmux` 가 필요합니다.

`tmux` 사용법도 [튜토리얼](https://github.com/ccss17/ProgrammerBase/blob/master/tmux.md) 에 자세히 써놓았기 때문에 여기에서는 `tmux` 를 사용하면, 또 커스터마이징하면 얼마나 생산성이 향상되는지만 살펴보겠습니다.

## 더 빨라진 `tmux`!

`tmux` 업그레이드는 사실 실제적인 업그레이드가 아니라 `tmux` 의 설정을 커스터마이징할 수 있는 `~/.tmux.conf` 파일에 사용자가 더 편하게 사용할 수 있도록 설정을 조작하는 것입니다. 그렇기 때문에 여기에서는 제가 설정한 `~/.tmux.conf` 파일을 중심으로 `tmux` 를 사용하기가 얼마나 편해졌는지 살펴보겠습니다. 

## 더 빨라진 alias

먼저 `tmux` 라는 명령어를 매번 치는 것은 너무 비효율적입니다. 무려 `4` 번이나 키보드를 쳐야하기 때문이죠. 그래서 `~/.zsh_aliases` 에 

```shell
alias t=tmux
```

를 추가하여 `t` 만 눌러도 `tmux` 가 켜지도록 합니다. 

!!! note

    `bash` 쉘 유저는 `~/.bashrc` 파일에 추가하면 됩니다.

이제 다음 명령어로 `tmux` 를 켰다가 끌 수 있습니다.

!!! example

    ```shell
    $ t
    $ q
    ```

    ![CSpyoIvAGI](https://user-images.githubusercontent.com/16812446/81962812-41dff300-964f-11ea-99db-8cf7727f849e.gif)

## 더 이뻐진 테마 

`tmux` 의 오리지널 테마는 너무 안이쁘네요. 그래서 좀 더 가독성도 높아지고 보기에도 좋고 시간도 알 수 있도록 다음과 같은 설정으로 테마를 고칩니다.

```shell
set -g status-bg default
set -g status-fg colour137
set -g status-style dim
set -g status-left '#[fg=colour51,bg=colour0,bold] %R '
# set -g status-right '#[fg=colour51,bg=colour0,bold] #(uname -r) '
set -g status-right '#[fg=colour51,bg=colour0,bold] #(osname) '
set -g status-right-length 100
setw -g window-status-current-style bg=colour14,fg=colour00,bold
setw -g window-status-current-format ' #I#[fg=colour0] #[fg=colour0]#W#[fg=colour0] '
setw -g window-status-style fg=colour49,none,bg=colour00
setw -g window-status-format '#I #W '
setw -g window-status-bell-style fg=colour255,bold,bg=colour1
set -g message-style fg=colour232,bold,bg=colour16
```

이 설정들을 `~/.tmux.conf` 에 넣으면 됩니다.

!!! example

    다음은 테마를 설정하기 전의 오리지널 `tmux` 의 테마입니다. 상태바가 아래쪽에 있고, 새 화면을 만들었지만 한 눈에 들어오지가 않습니다. 오른쪽에 시간도 표시되는데 역시 한 눈에 들어오지 않네요. 

    <img src="https://user-images.githubusercontent.com/16812446/82010318-ba28d180-96ac-11ea-833a-e2a7d65ef1c6.png" width="70%" height="auto">

    하지만 다음과 같이 테마를 바꿔서 가독성을 확연히 높혔습니다. 상태바가 위로 올라갔고, 왼쪽에는 시간이 간략하지만 눈에 확 들어오게 보입니다. 

    <img src="https://user-images.githubusercontent.com/16812446/82010331-c319a300-96ac-11ea-9fc8-12505574f461.png" width="70%" height="auto">

    그리고 `0` 번째 화면에는 `zsh` 이 켜져있고, `1` 번째 화면에는 `vim` 이 켜져있는데 현재 상주하고 있는 화면에 하이라이팅이 되서 가독성이 매우 높아집니다. 오른쪽에는 운영체제의 이름도 나타납니다.

## 더 빨라진 메타 키

| 기능 | 기존 단축키 | 새로운 단축키 |
|:---:|:---:|:---:|
| **Meta** 키 | <kbd>Ctrl</kbd>+<kbd>b</kbd>  |<kbd>Ctrl</kbd>+<kbd>a</kbd>  |

`tmux` 는 **Meta** 키 를 사용하여 명령어들을 정의하기 때문에 <kbd>Ctrl</kbd>+<kbd>b</kbd> 를 입력했어야 했습니다. 하지만 <kbd>Ctrl</kbd> 와 <kbd>b</kbd> 는 거리가 너무 멀어서 손이 아픕니다. 그래서 `~/.tmux.conf` 에 

```shell
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix
```

를 추가하여 거리가 가까운 <kbd>Ctrl</kbd>+<kbd>a</kbd> 로 **Meta** 키를 재설정합니다. 여러분의 도커 컨테이너에는 이미 설정 되어있으니 걱정하지 마세요.

!!! info

    앞으로 살펴볼 `tmux` 업그레이드들도 위와 같은 설정 파일을 조작하는 것으로 이루어졌지만, 일일이 어떤 설정으로 `tmux` 가 업그레이드되었는지 상세히 설명하지는 않겠습니다. 

    `.tmux.conf` 를 보시려면 [:octicons-file-code-24: .tmux.conf](https://github.com/ccss17/dotfiles-cli/blob/master/.tmux.conf) 를 확인해주세요.

## 더 빨라진 터미널 분할 

| 기능 | 기존 단축키 |새로운 단축키 |
|:---:|:---:|:---:|
| 터미널 수직 분할 | <kbd>Meta</kbd>+<kbd>%</kbd>  |<kbd>Meta</kbd>+<kbd>⧵</kbd>  |
| 터미널 수평 분할 | <kbd>Meta</kbd>+<kbd>"</kbd>  |<kbd>Meta</kbd>+<kbd>-</kbd>  |
| 다음 터미널으로 이동 | <kbd>Meta</kbd>+<kbd>o</kbd>  | <kbd>Alt</kbd>+<kbd>o</kbd> |
| (숫자) 터미널으로 이동 | <kbd>Meta</kbd>+<kbd>q</kbd> + (숫자)  |

`tmux` 에서 터미널을 수평으로 분할하려면 기존의 명령어 <kbd>Meta</kbd>+ <kbd>"</kbd> 를 입력해야 하는데 이건 외우기가 너무 어렵습니다. 그래서 외우기 쉽도록 수평으로 나눈다는 의미에서 <kbd>Meta</kbd>+ <kbd>-</kbd> 로 직관적으로 바꿉니다. 

또한 터미널을 수직으로 분할하려면 기존의 명령어 <kbd>Meta</kbd>+ <kbd>%</kbd> 를 입력해야 하는데 이것 역시 외우기가 너무 어렵습니다. 그래서 외우기 쉽도록 수직으로 나눈다는 의미에서 백슬래쉬로 바꿔서 <kbd>Meta</kbd>+ <kbd>⧵</kbd> 로 직관적인 단축키를 설정합니다. 

그리고 다음 터미널로 이동하는 단축키 <kbd>Meta</kbd>+<kbd>o</kbd> 는 실제로 (<kbd>Ctrl</kbd>+<kbd>a</kbd>) + <kbd>o</kbd> 인데, 다음 터미널로 이동하는 작업은 매우 많이 일어나므로 키를 `3` 번이나 눌러야 하는 것은 너무 비효율적이어서 참을 수가 없습니다. 그래서 <kbd>Alt</kbd>+<kbd>o</kbd> 로 바꿉니다. 

!!! example

    다음과 같이 터미널을 수직, 수평으로 여러번 분할해보고 <kbd>Alt</kbd> 를 계속 누른 채로 <kbd>o</kbd> 를 눌러서 터미널을 이동해보세요. 

    ![mMkWtsbnpw](https://user-images.githubusercontent.com/16812446/81961730-bca80e80-964d-11ea-935f-e6e5f5699b12.gif)

    터미널 이동이 정말 빨라졌습니다. 

## 더 빨라진 화면 생성 

| 기능 | 기존 단축키 | 새로운 단축키 |
|:---:|:---:|:---:|
| 새로운 화면 생성 | <kbd>Meta</kbd>+<kbd>c</kbd>  | <kbd>Alt</kbd>+<kbd>c</kbd>|
| 다음 화면으로 이동 | <kbd>Meta</kbd>+<kbd>n</kbd>  |<kbd>Alt</kbd>+<kbd>n</kbd>|
| 이전 화면으로 이동 | <kbd>Meta</kbd>+<kbd>p</kbd>  |<kbd>Alt</kbd>+<kbd>p</kbd>|

새로운 화면을 생성하고 화면을 넘기는 일도 편하게 하기 위하여 <kbd>Meta</kbd> 키 대신 <kbd>Alt</kbd> 를 사용합시다. 메타키를 <kbd>Alt</kbd> 키로 바꾸는 것만으로 얼마나 작업이 빨라지는지 보세요. 

!!! example

    다음과 같이 <kbd>Alt</kbd> 를 계속 누른채로 <kbd>c</kbd> 를 연타해서 화면을 더욱 빠르게 만들 수 있습니다. 그리고 여러 화면을 마찬가지로 <kbd>Alt</kbd> 를 계속 누른채로 <kbd>n</kbd> 또는 <kbd>p</kbd> 를 누르면서 이동해보세요. 

    ![q4pP5K9WGF](https://user-images.githubusercontent.com/16812446/81962006-14467a00-964e-11ea-9743-eeca5b7b271d.gif)

## 더 빨라진 터미널 이동

| 기능 | 기존 단축키 | 새로운 단축키 |
|:---:|:---:|:---:|
| 왼쪽 터미널으로 이동 | (기억이 안남..)  | <kbd>Alt</kbd>+<kbd>h</kbd>|
| 오른쪽 터미널으로 이동 | (기억이 안남..)  | <kbd>Alt</kbd>+<kbd>l</kbd>|
| 위쪽 터미널으로 이동 | (기억이 안남..)  | <kbd>Alt</kbd>+<kbd>k</kbd>|
| 아래쪽 터미널으로 이동 | (기억이 안남..)  | <kbd>Alt</kbd>+<kbd>j</kbd>|

터미널 이동을 <kbd>Alt</kbd>+<kbd>o</kbd> 로 매우 빠르게 할 수 있게 되었지만서도 터미널이 여러개로 나뉘었을 때 <kbd>Alt</kbd>+<kbd>o</kbd> 로 다음 터미널로밖에 이동할 수 없다면, 정확히 원하는 터미널로 이동할 수 없습니다. 이런 경우를 위하여 `tmux` 는 정확히 왼쪽, 오른쪽, 위쪽, 아래쪽 터미널로 이동할 수 있는 명령어를 제공합니다. 

하지만 그건 너무 복잡했었고 그게 뭐였는지 솔직히 까먹었습니다. 그 대신 `vim` 에서의 커서 이동키였던 <kbd>h</kbd>, <kbd>l</kbd>, <kbd>k</kbd>, <kbd>j</kbd> 에서 착안하여 터미널 이동을 매우 쉽게 할 수 있습니다. 

!!! example

    다음과 같이 터미널을 여러개로 분할하고 <kbd>Alt</kbd> 를 누른채로 <kbd>h</kbd>, <kbd>l</kbd>, <kbd>k</kbd>, <kbd>j</kbd> 를 누르면서 터미널을 이동해보세요. 

    ![YvxI7GtfRb](https://user-images.githubusercontent.com/16812446/81962572-e0b81f80-964e-11ea-8340-006084f302da.gif)

## 더 빨라진 터미널 크기 조절

| 기능 | 기존 단축키 | 새로운 단축키 |
|:---:|:---:|:---:|
| 터미널 크기를 왼쪽으로 방향으로 조절 | (너무 복잡함) | <kbd>Alt</kbd>+<kbd>&larr;</kbd>|
| 터미널 크기를 오른쪽으로 방향으로 조절 | (너무 복잡함) | <kbd>Alt</kbd>+<kbd>&rarr;</kbd>|
| 터미널 크기를 위쪽으로 방향으로 조절 | (너무 복잡함) | <kbd>Alt</kbd>+<kbd>&uarr;</kbd>|
| 터미널 크기를 아래쪽으로 방향으로 조절 | (너무 복잡함) | <kbd>Alt</kbd>+<kbd>&darr;</kbd>|

**더 빨라진** 터미널 크기 조절이라고 해봐야 터미널 크기 조절하는 방법을 배우지도 않았는데 라고 생각할 수도 있겠지만, 터미널 크기 조절하는 방법이 외울 수 없을 만큼 너무 복잡한 것이어서 안썼습니다. 과거의 제가 터미널 크기를 너무너무 쉽게 조절할 수 있도록 위와 같이 설정해놓았습니다. 

!!! example

    다음과 같이 터미널 단축키 <kbd>Alt</kbd> 를 계속 누른 채로 <kbd>&rarr;</kbd>, <kbd>&larr;</kbd>, <kbd>&uarr;</kbd>, <kbd>&darr;</kbd> 을 눌러서 터미널 크기를 너무나도 쉽게 조절해보세요. 

    ![mpiJ2Gh3hi](https://user-images.githubusercontent.com/16812446/81962685-06452900-964f-11ea-8da0-e7363eb2dd4a.gif)

# `tmux` 사용 예시

다음은 `tmux` 를 통하여 `nvtop` 과 `gotop` 으로 **GPU** 상황과 **CPU, RAM** 상황을 모니터링하면서 딥러닝을 돌리고 있는 모습입니다.

![](https://user-images.githubusercontent.com/16812446/89183484-44a90f00-d5d2-11ea-91f2-9cd1c189b387.png)

<div align="center">
<figcaption><i>nvtop 과 gotop 으로 시스템 모니터링 하면서 딥러닝하는 모습</i></figcaption>
</div>