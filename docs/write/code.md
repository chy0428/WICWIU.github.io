
Makrdown 파일은 다음과 같이 효과적인 소스코드 포매팅 기능을 제공합니다. 

```c++
#include <iostream>
using namespace std; 

int fib(int n) { 
	if (n <= 1) 
		return n; 
	return fib(n-1) + fib(n-2); 
} 

int main () { 
	int n = 9; 
	cout << fib(n); 
	getchar(); 
	return 0; 
} 
```

Markdown 파일의 기초 문법을 알고 있었다면 당연한 내용일 것입니다. 하지만 **mkdocs** 의 **material** 테마에서 소스코드를 좀 더 효과적으로 꾸밀 수 있습니다.

## 라인 넘버 붙이기

소스코드를 시작하는 \`\`\` 에 `linenums="1"` 을 붙이면 라인 넘버가 생깁니다.

*Example*:

```` markdown
``` python linenums="1"
def Fibonacci(n): 
	if n<0: 
		print("Incorrect input") 
	elif n==0: 
		return 0
	elif n==1: 
		return 1
	else: 
		return Fibonacci(n-1)+Fibonacci(n-2) 
print(Fibonacci(9)) 
```
````

*Result*:

``` python linenums="1"
def Fibonacci(n): 
	if n<0: 
		print("Incorrect input") 
	elif n==0: 
		return 0
	elif n==1: 
		return 1
	else: 
		return Fibonacci(n-1)+Fibonacci(n-2) 
print(Fibonacci(9)) 
```

## 특정 코드 강조하기

소스코드를 시작하는 \`\`\` 에 `hl_lines="2 5"` 을 붙이면 두번째, 다섯번째 코드가 강조됩니다.

*Example*:

```` markdown
``` python linenums="1" hl_lines="2 5"
def Fibonacci(n): 
	if n<0: 
		print("Incorrect input") 
	elif n==0: 
		return 0
	elif n==1: 
		return 1
	else: 
		return Fibonacci(n-1)+Fibonacci(n-2) 
print(Fibonacci(9)) 
```
````

*Result*:

``` python linenums="1" hl_lines="2 5"
def Fibonacci(n): 
	if n<0: 
		print("Incorrect input") 
	elif n==0: 
		return 0
	elif n==1: 
		return 1
	else: 
		return Fibonacci(n-1)+Fibonacci(n-2) 
print(Fibonacci(9)) 
```