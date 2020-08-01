
신경망을 **Python** 으로 코딩한 것과 **C++** 로 코딩한 것을 비교하고 싶은 상황이나 내용을 비교하고 싶은 상황에 컨텐츠 탭이 필요합니다.

## 컨텐츠 탭 만들기

`===` 로 탭을 구분하고 큰 따옴표에 탭 제목을 삽입하면 간단하게 컨텐츠 탭을 만들 수 있습니다.

*Example*:

````markdown
=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
````

*Result*:

=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
