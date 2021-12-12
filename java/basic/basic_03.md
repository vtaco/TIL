# 자바 연산자 및 배열

## 자바 연산자

### 산술 연산자

| 연산자 | 사용법 | 비고 |
| ------ | ------ | ---- |
| ++     | ++값   | 단항 |
|        | 값++   |      |
| --     | --값   |      |
|        | 값--   |      |
| +      | a + b  | 이항 |
| -      | a - b  |      |
| *      | a * b  |      |
| /      | a / b  |      |
| %      | a % b  |      |

<br>

### 비교 연산자

맞으면 true 반환

| 연산자     | 사용법                                           |
| ---------- | ------------------------------------------------ |
| >          | a > b                                            |
| >=         | a >= b                                           |
| <          | a < b                                            |
| <=         | a <= b                                           |
| ==         | a == b                                           |
| !=         | a != b                                           |
| instanceof | a instanceof b (a가 b 데이터 타입의 객체인 경우) |

<br>

### 논리 연산자

| 연산자 | 사용법   | 설명                           |
| ------ | -------- | ------------------------------ |
| &      | a & b    | 모두 true일 때                 |
| &&     | a && b   | 모두 true 일 때(빠른 연산)     |
| \|     | a \| b   | 하나라도 true일 때             |
| \|\|   | a \|\| b | 하나라도 true일 때 (빠른 연산) |
| !      | !a       | true, false간 변경             |

<br>

#### 비트 연산자

&

|

^

~

\>>

\>>>

<<

<br>

### 삼항 연산자

변수 = 조건 ? a : b

```java
int score = 78;
boolean passYn;
passYn = (score > 80) ? true : false;
```



<br>

<br>

## 자바의 배열

메모리 낭비, 시간 낭비를 줄이기 위해

**같은 타입의 데이터들의 모임**

```java
String greeting; // String 자료형의 greeting 변수 선언
gretting = new String("Hello, Java!"); // 변수 값 할당
```

greeting 에는 메모리 주소 값이 들어간다

메모리 주소 값은 String인 Hello, java!가 위치해 있는 곳을 의미한다

<br>

#### 일차원 배열

```java
//배열 선언
//데이터 타입 배열 변수명[];
int scoreList[];
//or
//데이터 타입[] 배열 변수명;
int[] scoreList;

// 배열 생성
// 배열 변수명 = new 데이터타입[배열의 길이]
scoreList = new int[100];

// 배열 선언 + 생성
int scoreList[] = new int[100];
int[] scoreList = new int[100];

// 배열 선언 + 생성 + 초기화
int[] scoreList = {1, 2, 3, 4, 5};
scoreList = new int[]{1, 2, 3, 4, 5};
```



배열이름.length로 배열의 길이를 알 수 있음

<br>

#### 이차원 배열

```java
// 배열 선언
// 데이터 타입 배열 변수명 [][]
int scoreList [][];

// 데이터 타입[][] 배열변수명
int[][] scoreList;

// 데이터 타입[] 배열 변수명[]
int[] scoreList[];

// 배열 생성
//배열 변수명 = new 데이터 타입[배열의 배열 길이][배열 길이];

```

<br>

<br>



#### 명령형 매개변수

```java
public class CommandLineArgTest{
    public static void main(String args[]){
        
    }
}
```

1. main()

   자바 app에 필수적으로 있어야 하는 특수한 메서드

   자바 app이 실행될 때 자동으로 실행됨

   


   main()은 `String args[]`을 받는다

   >문자열의 배열을 매개변수로 받아
   >
   >프로그램 실행 시 필요한 정보를 프로그램에 전달함