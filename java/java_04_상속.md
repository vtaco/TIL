# 상속(Inheritance)

**기존 클래스의 자산을 자식 클래스에서 재사용하기 위한 것**

`is a`

`extends` 키워드 사용

```java
public class Person {

	String name;
	
	void eat() {
		System.out.println("냠냠");
	}
	
	void run() {
		System.out.println("인간형 달리기");
	}
}


public class Hero extends Person {
	
	boolean isHeroMode;
	
	void attack() {
		System.out.println("어택");
	}
}

```

<br>

<br>

## Object

**모든 클래스의 조상 클래스**

별도의 extends 선언이 없는 클래스들은 extends Object 가 생략됨

<br>

<br>

## 단일 상속

다중 상속의 경우 여러 클래스의 기능을 물려받을 수 있으나 관계가 매우 복잡해짐

**자바는 단일 상속만 지원**

`interface`와 포함 관계`(has a)`로 단점을 극복

<br>

<br>

#### 포함 관계

상속 이외에 클래스를 재활용 하는 방법

2개 이상의 클래스에서 특성을 가져올 때 **하나는 상속, 나머지는 멤버 변수로 처리**

```java
public class Spider {
	
	void fireWeb() {
		System.out.println("거미줄 발싸!");
	}

}

// 상속은 Person
public class Hero extends Person {
	
	boolean isHeroMode;

    // 포함은 Spider
	Spider spider = new Spider();
	
	void attack() {
		System.out.println("어택");
	}
	
	
	void fireWeb() {
		if(isHeroMode) {
			spider.fireWeb();
		} else {
			System.out.println("사람은 도망치세요");
		}
	}
}
```

<br><br>

### 상속 is a : SpiderMan is a Person

### 포함 has a : SpiderMan has a Spider

<br>

<br>

#### 메서드 오버라이딩(Overriding)

**over write** 로 이해하면 외우기 쉬움

조상 클래스에 정의된 메서드를 자식 클래스에 적합하게 수정하는 것

```java
public class Person{
    void jump(){
        System.out.println("인간형 점프");
    }
}

public class Spider{
    void jump(){
        System.out.println("거미형 점프");
    }
}

public class Hero extends Person{
    Spider spider = new Spider();
    bollean isHeroMode;
    
    // 오버라이딩
    void jump(){

        if (isHeroMode){
            spider.jump();
        } else{
            System.out.println("오버라이딩된 인간형 점프")
        }
    }
    
}
```

- 오버라이딩의 조건
  - 메서드 이름이 같아야한다
  - 매개 변수의 개수, 타입, 순서가 같아야한다
  - 리턴 타입이 같아야한다
  - 접근 제한자는 부모 보다 범위가 넓거나 같아야 한다
  - 조상보다 더 큰 예외를 던질 수 없다

<br>

<br>

#### 메서드 오버 로드(Over load)

추가 적재

```java
public class Person {

	void run() {
		System.out.println("달려라");
	}
	
	void run(int distance) {
		System.out.println(distance + "m만큼 달려라!!");
	}
}
```

<br>

<br>

## Annotaion

주석

컴파일러, JVM, 프레임워크 등이 보는 주석

```java
@Deprecated
// 컴파일러에게 해당 메서드가 deprecated (권장하지 않음)

@Override
// 컴파일러에게 해당 메서드는 Override한 메서드임

@SuppressWarnings
// 컴파일러에게 사소한 warning의 경우 신경 쓰지 말라고 알려줌
```

<br>

<br>

## super 키워드

this 를 통해 멤버에 접근했듯이 super를 통해 조상 클래스 멤버 접근



this()로 해당 클래스의 다른 생성자를 호출하듯 super()는 조상 클래스의 생성자 호출