# [WIL] JAVA 독학 1주차 | ch01 ~ ch05

구분: WIL
날짜: 2022/07/25
진행: IN
포스팅: Notion

👩🏻‍💻독학 1주차

📅기간 : 7월 13일 ~ 7월 17일

📚진행상황 : java ch01 자바의 구조 ~ ch05 참조자료형

공부했던 내용 중 중요하다고 생각되는 부분들과

헷갈려서 두고두고 기억해둬야할 부분들 및 참고 예제코드를 기재하였다.

기본 개념도 중요하다고 생각한다.

헷갈릴때마다 확인하고 추가되는 내용이 있으면 추가하도록 하자.

2022-07-13

## 1. 자바의 구조

### 자바의 특징

플랫폼 독립성/객체지향언어/함수형코딩지원/분산처리지원/멀티쓰레드 지원

플랫폼 독립성은 자바 가상머신으로 인한 특징이다.

.exe → window 용 // java는 JVM 를 사용하여 어느 OS에서도 가능

자바 프로그램 개발환경에 필요한 요소

: 자바개발도구JDK > 자바개발환경JRE > 자바가상머신JVM

### Process

자바 프로젝트 폴더 생성/실행 

→ 패키지 생성

     src 폴더 생성:소스파일 저장,bin 폴더 생성:바이트코드 저장

→ 자바소스파일 생성 (.java) 

→ 컴파일 후 바이트코드(.class) 생성

    자바는 객체지향 언어이기때문에 소스파일명과 클래스명이 같아야 함 

→ 자바가상머신에서 메모리 할당 

→ 메서드 영역에 class 로딩 후 class내 main() 실행

 

### 자바의 메모리구조

| 클래스/메소드/정적/상수 영역 | 스택 영역 | 힙 영역 |
| --- | --- | --- |

클래스/메소드/정적/상수 영역 : class, method, static ~, final 저장

스택 영역 : 모든 지역변수가 저장됨

힙 영역 : 참조변수가 바라보는 실제 데이터가 저장됨, 객체가 저장됨

## 2. 자료형

### 변수와 자료형

- 변수

: 사용하기 전 반드시 선언해야 함

- 자료형의 종류
    - 기본 자료형 : boolean, byte, short, int, long, float, double, char
        
        모두 소문자로 구성됨, **스택메모리에 위치**하며 **실제 데이터도 스택메모리에  저장**됨
        
    - 참조 자료형 : 개발자가 직접 정의할 수 있어 무한함
        
        대문자로 시작함, 참조자료형도 스택메모리에 위치하지만 **실제 데이터는 힙메모리에 저장**되므로 스택메모리에는 실제데이터가 저장된 힙메모리의 주소가 저장됨 
        

 👉🏻소문자 a 문자로 저장되는 값 5가지

10진수 : 97

2진수 : **0b**01100001

8진수 : **0**141

16진수 : **0x**61

유니코드 : **\u00**61

2022-07-14

## 3. 연산자

### 종류 및 연산 방법

- 증감 연산자 ++, —
    - 전위형
    
    ```java
    int b=++a;
    ```
    
    명령이 2개인 것과 같다.
    
    1) a → a+1 
    
    2) a → b
    
    - 후위형
    
    ```java
    int b=a++;
    ```
    
    1) a → b
    
    2) a → a+1
    
    전위형/후위형에 따라 연산의 순서가 달라지므로 결과도 달라질 수 있음.
    
- 쉬프트 연산자 <<,>>
    
    << : 왼쪽으로 비트를 밀어냄 2의 배수만큼 커짐 ( * 2의 n배)
    
    양수/음수 모두 동일하게 적용됨
    
    >> : 오른쪽으로 비트를 밀어냄 2의 배수만큼 작아짐  ( / 2의 n배)
    
    음수일때는 값의 +1을 해준다.
    
- 논리쉬프트 연선자 >>>
    
    단순 자리이동하는 기능
    
    각 비트별 의미/기능이 있을 경우, 비트연산자와 함께 각 비트별 값을 확인할 수있음 ( 0과 1로 이루어져있기 때문에 가능)
    

2022-07-15 ~ 16

이론과 실습예제를 따라할때는 쉬웠는데 막상 연습문제를 풀어보니

확실히 많이 헷갈리는 파트라서 생각하는 시간이 가장 많이 걸린 챕터였다.

## 4. 제어문과 제어 키워드

### 제어문

: 프로그램의 실행순서를 바꾸는 것

- 선택제어문
    - if, if/else
    
    if 조건문이 true 일 때 {} 안의 내용 실행하고 탈출
    
    else if 첫 if 문이 false 이면 넘어와서 조건문 확인
    
    else 위 의 경우가 모두 아니면 탈출
    
    ```java
    if (조건문) {
    } else if(조건문){
    } else {
    }
    ```
    
    - switch
        - 점프할 위치변수 자리에는 정수/문자/문자열만 가능하며
        
        if문처럼 연산구문이 올수 없다
        
        - if문과는 다르게 탈출이 없어 점프한 부분부터 순차실행됨
        
        → break과 함께 사용하면 if 처럼 유사하게 탈출 가능
        
        - default 는 필수 구문임
        
        ```java
        switch(점프할 위치변수){
        	case(위치변수) :
        		실행문;
        	default :
        		실행문;
        ```
        
- 반복제어문
    - for
        - for문의 조건식이 true가 나오는동안은 계속 실행구문이 반복됨
        - false 인 경우 조건식에서 종료함
        - 조건식이 생략된 경우, 무한 반복됨
    
    ```java
    for(초기식; 조건식; 증감식){
    	실행구문 }
    ```
    
    - while
        - for 문과의 차이 : 초기식과 증감식이 외부에 있음/생략가능, 조건식 생략안됨
        - for문과 공통점 : 종료시점은 조건식
        - 조건식이 true인 동안 진행 → 반복횟수를 정하지 않고 특정 조건까지 반복하고자 할 때 씀 (예: 더한 합계가 100보다 커질때까지 반복)
        
        ```java
        초기식;
        while(조건식){
        	실행구문;
        	증감식;
        }
        ```
        
    
    👉🏻 for문과 동일한 while 문을 작성
    
    ```java
    for(int i=10; i>0; i-=2){
    	System.out.println(i);
    }
    ```
    
    ```java
    int i=10;
    while (i>0){
    		System.out.println(i);
    		i-=2;
    }
    ```
    
    - do-while
        - while문과 조건식 검사/반복실행 순서의 차이
        - 초기 실행구문이 최초 1회 실행 필수
        - 조건식이 true 이면 다시 do 실행, 아니면 탈출
    
    ```java
    초기식;
    do{
    	실행구문;
    	증감식;
    } while (조건식);
    ```
    

### 제어키워드

- break
    
    속해있는 구문을 제외하고 가장 가까운 중괄호 탈출
    
    ```java
    for(int i=0; i<10; i++){
    	for(int j=0; j<10; j++){
    		if(j==3){ //j가 3일때
    			i=100; // i에 100을 저장하고
    			break; // 중괄호 탈출
    		} //break을 만나면 속해 있는 이 중괄호가 아닌
    		System.out.println(i+","+j);
    	} // <- 이 중괄호를 탈출하여 상위 for문 실행
    }
    ```
    
- continue
    
    닫힌 중괄호(}) 의 역할을 함 → 특정 구문을 실행하지 않고 건너뛸때 사용
    
     
    
    ```java
    for(int i=0; i<5;i++){
    	for(int j=0;j<5;j++){
    		if(j==3){
    			continue;
    		}
    		System.out.println(i+","+j);
    	}//continue를 만나면 출력을 건너뛰고 이 중괄호를 나와서 j를 증가 시킴
    }
    
    ```
    

👉🏻 다음과 같이 출력되도록 if/break/continue 사용하여 for 문 작성

> 출력결과 : 0 2 4 6 8 10
> 

```java
for (int i=0; ; i++){
			if(i%2==1){ //홀수는 if를 빠져나가 for문을 다시 실행해
				continue;
			}

			if(i>10){ // i가 10보다 커지면 for문을 나가
				break;
			}
			System.out.println(i);
}
```

2022-07-17

## 5. 참조자료형

### 배열

같은 자료형을 묶어서 저장하는 형태

배열의 선언/객체 생성 

1. 배열 선언 : int a[] a 배열에는 int 자료형만 가능
2. 힙 메모리에 배열객체 생성 : int a[]=new int[3]; // int 정수 3개 배열 생성
3. 객체에 값 입력 : a[0]=1; a[1]=2; a[2]=3;

👉🏻 int a[]=new int[]{1,2,3}

배열의 원소 출력하기

1) 배열의 길이 .length 이용하여 출력

```java
int[]a = new int [100]

for(int i=0; i<a.length;i++){ // 배열의 길이만큼 반복

System.out.println(a[i]);

}
```

2) for-each 사용

for(원소 자료형의 변수명 : 집합객체)

```java
for(int k:a){
	System.out.println(k);
}
```

** 2차원 배열

int a[][]=new int[2][3];

메모리는 2차원 데이터를 바로 저장할 수 없음

→ 2차원 배열은 1차원 배열을 원소로 한 배열

int [][] a=new int[][]{{1,2,3},{4,5,6}}

a[0][0]=1; a[0][1]=2; a[0][2]=3; 👉🏻 a[0]=new int[]{1,2,3}

a[1][0]=4; a[1][0]=5; a[1][2]=6; 👉🏻 a[1]=new int[]{4,5,6}

### String

: 자바가 제공하는 클래스중 문자열을 저장함

 특징

- 문자열 내용을 변경하면 자바가상머신은 새로운 문자열을 포함한 객체를 생성에 사용하고 기존 객체는 버린다.
- 문자열 리터럴을 바로 입력해 객체를 생성할 때, 같은 문자열 끼리 객체를 공유 → 메모리의 효율성

String 객체의 + 연산

- 문자열+ 문자열

 String str1=”안녕”+”하세요”+”!”; 👉🏻객체 3개(안녕/하세요/!)

⇒ 안녕하세요+! 👉🏻 객체 1개(안녕하세요)

⇒ 안녕하세요! 👉🏻 객체 1개(안녕하세요!)

총 5개의 객체를 생성