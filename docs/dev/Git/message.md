
# Commit 메시지와 Pull Requests 제목 규칙

**commit** 메시지와 **Pull Requests** 제목을 정할 때 일관된 규칙을 사용해야 협업할 때 좋습니다. [**WICWIU**](https://github.com/WICWIU/WICWIU) 는 다음과 같은 규칙을 사용합니다.

!!! note ""

    `Branch: Update {UPDATED-FILE-NAMEs} (DESCRIPTION)`

이 규칙으로 어떻게 **commit** 메시지와 **Pull Requests** 제목을 정할 수 있는지 예시를 살펴보겠습니다.

!!! example

    `RNN` 브랜치에서 `src/RNN.cpp` 에 `main()` 함수를 만들었다면

    `RNN: Update src/RNN.cpp (create main function)` 

    또는

    `RNN: Update src/RNN.cpp (main 함수 생성)` 

    이라는 **commit** 메시지와 **Pull Requests** 제목을 만들면 됩니다. 이때 설명(`DESCRIPTION`) 은 협업하는 사람이 이해해야 하기 때문에 자세하고 명료할수록 좋습니다.
