
# [C/C++] 문제풀이하면서 필요한 기초개념들 기록
## C++
### 최댓값/최솟값
```c
#include <algorithm>
max(int num1, int num2, ...);  //인자 중 최대값 반환. 변수 못넣음.
min(int num1, int num2, ...);  // 최소값
```
### 절댓값
```c
#include <cstdlib>  // int 형인 경우
#include <cmath.h>  // double, float
abs(int num);       // 절대값 반환 (absolute value)
```
### `\` 역슬래쉬 사용
 - `\t` : tab 효과
-  `\n`  : enter 효과(endl) **endl 보다 빠르다.*
-  `\'`, `\"` : 따옴표(', ") 표시
-  `\\`: \ 출력 (하나만 하면 출력X)
### 문자열 입력
```c
#include <iostream>
char str_input[10];
char k;
cin >> str_input;   // 공백, 줄바꿈 기준으로 입력받음
cin.get(k);         // 문자 입력받음
cin.getline(str_input, 10);
// 줄바꿈 기준으로 입력받음 ==> *공백도 문자로 간주!
// 파라미터:(문자열을 저장할 배열이름, 입력받을 최대 문자 개수 + 1) < C언어 문자열의 마지막엔 '\0'이 들어가기 때문!
```
string은 이렇게!
```c
#include <string>
string str_input;
getline(cin, str_input);  // 두번째 파라미터에 입력받은 스트링을 저장할 이름
```
### 제곱근 : x^y
```c
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
```
### 소수점 자리설정
```c
#include <iomanip>
cout << setprecision(3);   // 파라미터로 소수점 몇자리인지 정해줌
```
### 입출력 메모리 적게
```c
#include <stdio.h>
scanf("%d",&a);     // 입력
printf("%d",&a);    // 출력
```

### 삼항연산자
`조건문 ? <참일 때> : <거짓일 때> ;`

### puts
int puts(const char* str);<br>
str을 stdout에 쓴 뒤 개행문자도 자동으로 붙는다.<br>
fputs는 동일하지만 개행문자가 붙지 않는다.<br>
[리턴값] 성공적으로 쓰이면 음이 아닌 값, 오류발생시 EOF추력
```c
#include <cstdio>     // C++에서
#include <stdio.h>    // C에서
puts(<출력할 값>);    
```
삼항연산자와 같이 사용하기도 하는듯! 아래와 같은 느낌
```C
puts(t == 12345678 ? "ascending" : t == 87654321 ? "descending" : "mixed");
```
### 배열초기화
```c
int arr[10];
int arr[10] = {0, }; // 0으로 초기화
int arr[10] = {-1, }; // arr[0]=-1, 나머지 0으로 초기화
// bool 형식에서도 마찬가지로 false만 전체초기화 가능
// for문으로 하나씩 채워주면 다른 값 초기화가능
```
---
## C언어
### 숫자 입력
```c
#include <stdio.h>
getchar() // (문자입력) 한 글자씩 입력됨. 숫자 12면 1, 2 따로
scanf("%c", &x); // (char) 문자 입력 *숫자도 한글자씩
scanf("%d", &x); // (double) 숫자 입력
scanf("%s", &x); // (string) 문자열 입력
```
### 기타
char형으로 저장된 숫자에서 `-'0'` *(integer 48 을 빼는 것)* 을 해주면 int(아마도)형이 된다.