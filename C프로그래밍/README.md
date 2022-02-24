# C프로그래밍

### 목차
- [1강. C 언어의 개요](#1강-C-언어의-개요)
  - [C 언어의 정의, 역사, 특징](#C-언어의-정의-역사-특징)
  - [프로그램의 작성 및 준비](#프로그램의-작성-및-준비)
  - [에러와 경고](#에러와-경고)
- [2강. 자료형과 선행처리기](#2강-자료형과-선행처리기)
  - [상수와 변수](#상수와-변수)
  - [자료형과 변수 선언](#자료형과-변수-선언)
  - [선행처리기](#선행처리기)

## 1강. C 언어의 개요
### C 언어의 정의, 역사, 특징
- **C**
  - **프로그래밍 언어(programming language)**
    - 사람과 컴파일러(compiler)가 이해할 수 있도록 약속된 형태의 언어  
      ![image](https://user-images.githubusercontent.com/61646760/155307992-e96bd7f5-90e0-465f-be8e-8eb8b8e204c4.png)
      - **컴파일러(compiler)** : 프로그래밍 언어로 작성된 프로그램을 컴퓨터가 이해할 수 있도록 기계어로 번역해 주는 번역기
      - **인터프리터(interpreter)** : 소스 프로그램을 한번에 기계어로 변환시키는 컴파일러와는 달리, 프로그램을 한 단계씩 기계어로 해석하여 실행하는 '언어처리 프로그램'
  - Denis Ritchie(1972년)
  - UNIX 운영체제 구현에 사용할 목적으로 개발
    - 컴퓨터 기종 간 호환성을 가진 고급 언어면서, 하드웨어를 제어할 수 있는 새로운 언어가 필요
  - 어셈블리 언어로 된 UNIX 운영체제가 거의 C 언어로 대체
- C 언어의 특징
  - 프로그램 이식성이 높다.
  - 저급 언어의 특성을 가진 고급 언어이다.
### 프로그램의 작성 및 준비
- C 프로그램의 완성 과정
  - **코딩(coding) 단계** : 주어진 문제에 대한 설계를 바탕으로 소스코드(source code)를 작성하여 <strong>소스파일(source file)</strong>을 생성하는 과정  
    ![image](https://user-images.githubusercontent.com/61646760/155307569-6d6dea6d-3f0e-4c3e-9f69-6906159e9f16.png)
  - **컴파일(compile) 단계** : 소스파일이 <strong>목적파일(object file)</strong>로 변환되는 과정  
    ![image](https://user-images.githubusercontent.com/61646760/155308472-0b699f83-13fc-4ac8-9fe8-1ce248e8af41.png)
  - **링킹(linking) 단계** : 목적파일을 <strong>실행파일(execution file)</strong>로 변환하는 과정  
    ![image](https://user-images.githubusercontent.com/61646760/155308600-cc131cd7-7747-48bc-87a6-40ddbacac4e1.png)
    - 여러 목적파일, 라이브러리를 링커(linker)를 통해 하나의 실행파일로 변환
    - 실제로는 컴파일 과정에서 linking까지 자동으로 이루어짐 
### 에러와 경고
- **에러(error)**
  - C 언어의 문법상 잘못된 경우 에러 메시지를 출력
    - 즉, C 언어의 문법에 맞지 않는 형식의 사용이나 반드시 필요한 지정이 빠진 경우 등에서 발생
  - 에러 메시지를 확인하여 반드시 수정하여야 한다.
- **경고(warning)**
  - 경고는 일단 컴파일은 가능한 경미한 실수를 했을 때 발생
  - 현재는 큰 문제가 없지만 이식성에 불리하다거나, C 언어 문법에서 권장하지 않는 방법으로 소스 프로그램을 작성했을 때도 발생
  - 경고를 무시하여도 실행파일을 생성하여 실행할 수 있는 경우가 많다.

## 2강. 자료형과 선행처리기
### 상수와 변수
- **자료형(data type)**
  - 프로그램에서 사용하는 자료의 형태
  - 상수와 변수로 구분하여 사용
- **상수(constant)**
  - 항상 고정된 값을 갖는 자료
    - 값이 한번 정해지면 프로그램 도중에 그 값을 변경할 수 없는 수
  - 정수형 상수
    - 10진수, 8진수, 16진수로 표현  
      ![image](https://user-images.githubusercontent.com/61646760/155313154-4adf0c6e-7d46-4238-822a-c1cf23bf0c28.png)
  - 실수형 상수
    - 부동소수점 형 상수
    - double형을 기본 자료형으로 사용  
      ![image](https://user-images.githubusercontent.com/61646760/155313638-4f2f78ef-47a9-469a-a0a0-b0ef45eb9c1b.png)
  - 문자형 상수
    - 단일 인용부호(`‘ ’`)로 묶여 있는 1개의 영문자나 숫자 문자
    - 내부적으로는 해당 문자의 ASCII 코드 값이 사용
      - `예) 'A'는 내부적으로 65(ASCII 코드 값)가 사용된다.`
    - **Escape 문자** : 키보드에 나타나 있지 않은 문자  
      ![image](https://user-images.githubusercontent.com/61646760/155313966-db2e4bd7-6c7e-475a-b6cf-2fb863b125bc.png)
      - `\n` : 개행
      - `\0` : ASCII 코드 값이 0인 문자 (null 문자)
  - 문자열 상수
    - 이중 인용부호(`“ ”`)로 묶여 있는 복수 개의 영문자나 숫자 문자
    - 기억 공간에 보관될 때는 문자열 끝에 null 문자(`\0`)가 (자동적으로) 추가
      - `예) 문자열 “SEOUL KOREA”의 기억 공간 보관 형태`  
        ![image](https://user-images.githubusercontent.com/61646760/155341835-77a865ba-052d-410c-a58d-c84d333fbc76.png)
- **변수(variable)**
  - 변할 수 있는 값
  - (프로그램에서) 변수는 프로그램 실행 도중 **변할 수 있는 값이 저장되는 기억 공간**을 의미
    - `예)` `i=10;`의 `i`는 변수(명)이고, `10`이란 값을 `i`라는 이름으로 정의된 기억 공간에 저장한다는 의미
    - 이러한 변수 속에 들어가는 값은 수시로 변경될 수 있다.
  - 따라서 변수는 **사용 전에 반드시 선언**하여 컴파일러가 기억 공간에서 **일정 공간을 확보**할 수 있도록 해야 함
    - `예) 변수의 사용`  
      ![image](https://user-images.githubusercontent.com/61646760/155344721-36cda294-5eb5-454d-89ad-004f7be5680d.png)
### 자료형과 변수 선언
- 변수 선언
  - 변수명과 변수가 가질 자료형을 지정하여 변수를 위한 기억 공간을 할당하는 것  
    ![image](https://user-images.githubusercontent.com/61646760/155559083-6fc52830-dc6f-4d82-ba6b-26468e841c09.png)
  - 변수 선언 시 고려 사항
    - 변수에 저장될 **값의 크기(범위)**
      - `예)` short int 자료형의 경우 -32768 ~ 32767까지의 범위를 가지므로, 다음이 성립한다.
        ![image](https://user-images.githubusercontent.com/61646760/155560757-f10a8794-398e-4c12-91b9-b1e588af5e37.png)
        - `num1`이 32768의 값을 가질 수 없으므로 `32768 + 1 = -32768`이 성립한다.
    - 변수의 **선언 위치**  
      ![image](https://user-images.githubusercontent.com/61646760/155559495-59ec743b-f206-4004-a1d9-a367966bed17.png)
    - 변수의 **초기화**  
      ![image](https://user-images.githubusercontent.com/61646760/155562155-fd186634-f6ba-471b-a11c-55fdfb26a12e.png)
      - 변수 `i`는 for문 내에서 1로 초기화됨
      - 변수 `sum`은 초기화되지 않음
- 자료형 종류  
  ![image](https://user-images.githubusercontent.com/61646760/155507571-84a5e331-29e8-4744-82e6-37a646fe1262.png)
  - 정수형  
    ![image](https://user-images.githubusercontent.com/61646760/155514312-f9b70bb7-8d47-4a71-808a-0ed4699be58c.png)
    - 운영체제에 따라 표현 범위가 다름
  - 실수형  
    ![image](https://user-images.githubusercontent.com/61646760/155514383-4bbcced3-5420-4971-80be-505a6e32580c.png)
    - 기본형은 double형
  - 문자형  
    ![image](https://user-images.githubusercontent.com/61646760/155514417-16d5acb9-25c6-4e14-8ed3-3a958130fda4.png)
    - ASCII 코드를 사용하여 처리
    - `예) 문자형의 사용`  
      ![image](https://user-images.githubusercontent.com/61646760/155515374-303bf80e-a87d-4b11-af79-238b0b8c5198.png)
      - `'A'`는 아스키 코드 값인 65로 사용되므로, char형 변수든 int형 변수든 어디에 할당돼도 동일한 값을 가짐
        - `%d`로 출력 시, `ch`를 출력해도 `in`을 출력해도 동일하게 65가 출력됨
        - `%c`로 출력 시, `ch`를 출력해도 `in`을 출력해도 동일하게 d가 출력됨
  - 열거형
    - 숫자 대신 단어를 사용
      - 정수형 상수에 이름을 붙여서 코드를 이해하기 쉽게 해줌
      - `예) enum Color {Yellow, Red, Blue, Black, Green`
        - 노랑은 0, 빨강은 1, 파랑은 2, 검정은 3, 초록은 4
    - 형식 : `enum 태그명 {열거자1, 열거자2, ...}`  
      ![image](https://user-images.githubusercontent.com/61646760/155514565-ff890302-4836-434b-bdf2-23c21e2ef3bc.png)
      - enumerate : 열거하다는 의미
      - 열거자1은 `0`, 열거자2는 `1` … 로 자동 할당됨
        - `{열거자1=2, …}`로 설정하면 `2`부터 자동 할당됨
    - `예) 열거형의 사용`  
      ![image](https://user-images.githubusercontent.com/61646760/155557546-c9ed286f-b52a-4110-930e-a0dcab7cb546.png)
### 선행처리기
