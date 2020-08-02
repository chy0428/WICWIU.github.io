
# fork 한 레포지토리 업데이트하기

[**WICWIU**](https://github.com/WICWIU/WICWIU) 를 자신의 레포지토리를 **fork** 해왔는데 함께 협업하는 사람의 **Pull Requests** 가 [**WICWIU**](https://github.com/WICWIU/WICWIU) 로 병합되면 자신의 **fork** 레포지토리를 업데이트할 필요가 있습니다.

`RNN` 브랜치에서 작업을 하다가 같이 협업하는 사람의 **Pull Requests** 가 원본 [**WICWIU**](https://github.com/WICWIU/WICWIU) 레포지토리의 `RNN` 브랜치로 **merge** 되었다고 하겠습니다. 이 경우 다음과 같이 자신의 **fork** 레포지토리를 업데이트할 수 있습니다. 

!!! note

    **fork** 한 레포지토리이기 때문에 `origin` 이 **https://github.com/WICWIU/WICWIU** 가 아니라 **https://github.com/{USER_NAME}/WICWIU** 으로 되어 있습니다.

1. 원본 [**WICWIU**](https://github.com/WICWIU/WICWIU) 레포지토리를 `upstream` 이라는 `remote` 로 등록한다.

    !!! tip "EXECUTE:"

        `git remote add upstream https://github.com/WICWIU/WICWIU`

2. `upstream`(원본 [**WICWIU**](https://github.com/WICWIU/WICWIU)) 으로부터 업데이트된 데이터들을 `fetch` 해온다.

    !!! tip "EXECUTE:"

        `git fetch upstream`

3. `RNN` 브랜치를 업데이트 할 것이기 때문에 `RNN` 브랜치로 이동한다.

    !!! tip "EXECUTE:"

        `git checkout RNN`

4. `upstream`(원본 [**WICWIU**](https://github.com/WICWIU/WICWIU)) 으로부터 `RNN` 브랜치를 업데이트한다.

    !!! tip "EXECUTE:"

        `git merge upstream/RNN`
    
    !!! warning

        **fork**  레포지토리를 수정하지 않았다면 **Git** 은 **fast-forward** 를 진행하지만 레포지토리를 수정했다면 **merge conflict** 가 발생할 수도 있습니다. 병합 충돌 해결법은 [이곳](https://github.com/ccss17/ProgrammerBase/blob/master/git.md#git-branching)을 참고하거나 다른 **Git** 학습 자료를 참고해주세요.

5. 자신의 **fork** 레포지토리로 **push** 한다.

    !!! tip "EXECUTE:"

        `git push origin RNN`
    