```java
public class FirstApp{ //클래스의 시작
    public static void main(String args[]){ // 메서드 영역의 시작
        System.out.println("Hello World!");
    }
}
```



식별자

**관례상** 클래스 이름은 대문자로, 메서드 이름은 소문자, 변수는 소문자, 상수는 대문자로 시작 



## 자바 데이터 타임과 변수

```java
int age; // 변수 선언 데이터 타입 변수명 
age = 29; // 변수 초기화
    
int age2 = 28; // 동시 선언 초기화
```

| 표현형태  | 데이터 타입 | 정의                                |
| --------- | ----------- | ----------------------------------- |
| 논리값    | boolean     | true or false                       |
| 단일 문자 | char        | ex) 'a'                             |
| 정수      | byte        | 부호가 있는 정수(8bit)              |
|           | short       | 부호가 있는 정수(16bit)             |
|           | int         | 부호가 있는 정수(32bit) **default** |
|           | long        | 부호가 있는 정수(64bit)             |
| 실수      | float       | 부호가 있는 정수(32bit)             |
|           | double      | 부호가 있는 정수(64bit) **default** |

범위 초과 시, 연산 결과로 초과 시 오류

<br>

<br>

#### 변수 선언

한 가지 유형의 데이터만을 저장

기본형(Primitive Type)과 참조형(Reference Type)이 존재함

<br>

#### 전역 변수

여러 메서드에서 공통으로 사용 가능



#### 지역 변수

해당 변수가 선언된 메서드 내에서만 사용 가능



### 형 변환

1. 묵시적 형변환(Promotion) : 작은 데이터 타입 -> 큰 데이터 타입, 데이터 손실의 우려가 없으므로 자동 캐스팅

   byte -> short(char) -> int -> long -> float -> double

   ```java
   int age = 25;
   double avgAge = age;
   ```

   

   

2. 명시적 형변환(Demotion) : 큰 데이터 타입 -> 작은 데이터 타입, 데이터 손실의 우려로 명시적으로 캐스팅

   ```java
   double avgAge = 24.56;
   int age = (int)avgAge
   ```

   