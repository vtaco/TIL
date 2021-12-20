# 인터페이스

서로 다른 두 시스템, 장치, 소프트웨어 따위를 서로 이어주는 부분

최고 수준의 추상화 단계 : 모든 메서드가 **abstract 형태**

<br>

모든 멤버변수는 public static final (생략 가능)

모든 메서드는 public abstract (생략 가능)



```java
public interface MyInterface{
    public static final int MEMBER1 = 10;
    int MEMBER2 = 10;
    
    public abstract void method1(int param);
    void method2(int param);
}
```

<br>

## 인터페이스 상속

extends로 상속이 가능하며 **다중 상속**이 가능함

```java
public interface Fightable {
	public abstract void fire();
}

public interface Transformable {
	void changeShqpe(boolean isHeroMode);
}


public interface Heroable extends Fightable, Transformable {
	void upgrade();
}

```



<br>

<br>

## 인터페이스 구현과 객체 참조

`implements`키워드를 사용해서 interface 구현

`implements`한 클래스는

- 모든 abstract 메서드를 override해서 구현하거나
- 구현하지 않을 경우 abstract 클래스로 표시

```java
public class Person {
	public void eat() {
		System.out.println("먹자");
	}
}

	
	@Override
	public void upgrade() {
		System.out.println("레벨 업");
	}

	@Override
	public void fire() {
		System.out.println("발사");
		
	}

	@Override
	public void changeShqpe(boolean isHeroMode) {
		System.out.println("변신");
		
	}
}

```

조상 클래스 뿐 아니라 조상 인터페이스에도 적용

<br>

<br>

## 인터페이스의 필요성

#### 구현의 강제로 표준화 처리(`abstract`)

인터페이스를 통한 간접적인 클래스 사용으로 손쉬운 모듈 교체 지원

// 레이저 프린트 vs 도트 프린트

<br>

#### 서로 상속의 관계가 없는 클래스들에게 인터페이스를 통한 관게 부여로 다형성 확장

// 충전 기능

<br>

#### 독립적인 프로그래밍으로 개발 기간 단축

<br>

<br>

## Default 메서드

인터페이스에 선언 된 구현부가 있는 메서드

```java
interface DefaultMethodInterface{
    void abstractMethod();
    
    default void dfeaultMethod(){
        System.out.println('이것은 기본 메서드');
    }
}
```

#### 필요성

- 기존에 interface 기반으로 동작하는 라이브러리의 interface에 추가해야 하는 기능이 발생
- 기존 방식으로라면 모든 구현체들이 추가되는 메서드를 override 해야 함
- default 메서드는 abstract가 아니므로 반드시 구현해야할 필요가 없음
