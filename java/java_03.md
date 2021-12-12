# 객체지향

현실의 객체가 갖는 속성과 기능은 **추상화(abstraction)** 되어 클래스에 정의된다.

클래스는 **구체화** 되어 **프로그램의 객체(instance, object)**가 된다.

<br>

## 사람을 프로그램의 객체로 만드는 과정

| 이름 | 나이 | 배고픔 | 행동           |
| ---- | ---- | ------ | -------------- |
| 철수 | 29   | X      | 먹는다,일한다  |
| 영희 | 27   | O      | 먹는다, 일한다 |

이름, 나이, 배고픔 -->  상태,속성 = 변수, 필드

먹는다, 일한다 --> 기능, 행위 = 메서드, 함수

**프로그래밍**

**추상화**

| 클래스      | Person           |
| ----------- | ---------------- |
| 멤버 변수   | String name      |
|             | int age          |
|             | boolean isHungry |
| 멤버 메서드 | void eat()       |
|             | void work()      |

**구체화**

|              | Person p = new Person(); |
| ------------ | ------------------------ |
| p.name =     | "철수";                  |
| p.age =      | 29;                      |
| p.isHungry = | false;                   |
| p.eat();     |                          |
| p.work();    |                          |

<br>

## Class Vs Object

#### 클래스

설계도, 틀

객체를 정의해 놓은 것

객체를 생성할 때 사용

**데이터 타입**

<br>

#### 객체

클래스를 구체화 한 것

실제로 동작하는 것

**메모리에 생성된 데이터**

- 

```java
public class Person {
	// 멤버 변수
	String name;
	boolean isHungry;
	int age;
	
	// 메서드
	void eat() {
		System.out.println("냠냠");
		isHungry = false;
		
	}
	
	void work() {
		System.out.println("일일");
		isHungry = true;
	}
	
}

```



- main

```java

public class PersonTest {

	public static void main(String[] args) {
		Person p1 = new Person();
		p1.name = "홍길동";
		p1.isHungry = true;
		
		p1.eat();
		System.out.println(p1.name +" : " + p1.isHungry);
		
		p1.work();
		System.out.println(p1.name +" : " + p1.isHungry);
		
	}

}

```

#### 객체 생성과 메모리

- class area

  클래스 원형 로딩

  - 필드 정보
  - 메서드 정보
  - 타입 정보
  - 상수 풀

- method stack

  메서드들의 실행 공간

  - **thread 별**로 별도 관리
  - 메서드 호출 순서대로 쌓이는 구조
  - 메서드 프레임에 로컬변수도 쌓이는 구조
  - 로컬변수는 선언된 영역을 벗어나면 삭제

- heap

  **객체를 저장**하기 위한 영역

  - **thread에 의해 공유**
  - 생성된 객체는 프로그래머가 삭제할 수 없고 GC만이 제어 가능

<br>

<br>

## 메서드

현실의 객체가 하는 **동작을 프로그래밍화**

어떤 작업을 수행하는 명령문의 집합

반복적으로 사용되는 코드의 중복을 방지하고 양을 줄여 유지 보수가 용이

```java
제한자 리턴타입 메서드이름(타입 변수명 , 타입 변수명, ...){
    행동
}
```

어떤 값을 입력 받아서 => 파라미터

작업을 진행하고 => 실행

결과를 돌려줌 => 리턴값

<br>

#### 리턴타입

아무것도 리턴하지 않을 경우 void

결과를 받을 때 묵시적 형 변환 적용

<br>

#### Varialbe arguments

메서드 선언 시 몇 개의 인자가 들어올지 예상할 수 없을 경우

배열 타입을 선언할 수 있으나 -> 메서드 호출 전 배열을 생성, 초기화 해야 하는 번거로움

...을 이용해 파라미터를 선언

```java
public static void main(String[] args){
    Variable v = new Variable();
    v.VariableArgs(1,2,3,);
    v.VariableArgs(1,2,3,4,5);
    v.VariableArgs(1,2);
}

public void v.VariableArgs(int... params){
    int sum = 0;
    for(int i:params){
        sum+=i;
    }
    System.out.println(sum);
}
```

