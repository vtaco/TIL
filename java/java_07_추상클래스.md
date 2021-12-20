# 추상클래스

- Vehicle.java

  ```java
  public class Vehicle {
  	private int curX, curY;
  	
  	public void reportPosition() {
  		System.out.printf("현재 위치: (%d %d)%n",curX,curY);
  	}
  	
  	public void addFuel() {
  		System.out.println("탈것은 주유");
  	}
  }
  ```

- DiesselSUV.java

  ```java
  public class DieselSUV extends Vehicle {
  
  	@Override
  	public void addFuel() {
  		System.out.println("주유소 급유");
  	}
  	
  }
  
  ```

- ElectricCar.java

  ```java
  public class ElectricCar extends Vehicle{
  	
  	@Override
  	public void addFuel() {
  		System.out.println("급속 충전 급유");
  	}
  	
  }
  
  ```

- VehicleTest.java

  ```java
  public class VechicleTest {
  
  	public static void main(String[] args) {
  
  		Vehicle [] vehicles = {
  				new ElectricCar(),
  				new DieselSUV()
  		};
  		
  		for(Vehicle v: vehicles) {
  			// v를 추상화하지 않으면 v로 사용하지 못함
  			v.addFuel();
  			v.reportPosition();
  		}
  	}
  
  }
  ```

디젤, 전기차 모두 연료를 필요하므로 addFuel은 공통 모듈

**하지만 Vehicle class 자체는 addFuel 메서드를 사용하지 않음**

그렇다고 addFuel 함수를 삭제하고 각각의 차 클래스에서 새롭게 정의한다면

**VehicleTest에서 `v.addFuel()`함수를 사용하지 못함!!**

`Q. 그럼 어떻게 해결해야할까?`

`A. 추상화!!` abstract

```java
abstract class Vehicle {
	private int curX, curY;
	
	public void reportPosition() {
		System.out.printf("현재 위치: (%d %d)%n",curX,curY);
	}
	
	public abstract void addFuel();
}

```

<br>

<br>

## Abstract

상속 전용의 클래스

클래스에 구현부가 없는 메서드가 있으므로 **객체를 생성할 수없음**

하지만 상위 클래스 타입으로써 자식을 참조할 수는 있다.

<br>

```java
// abstract 클래스는 객체를 생성할 수 없다.
Vehicle v = new Vehicle();

// 자식을 참조하는 것은 문제 없음
vehicle v = new DiselSUV();
```

조상 클래스에서 상속 받은 abstract 메서드를 재정의 하지 않는 경우

클래스 내부에 abstract 메서드가 있는 상황이므로 자식 클래스는  abstract 클래스로 선언되어야 함

<br>

#### 추상클래스를 사용하는 이유

**구현의 강제를 통해 프로그래의 안정성 향상**

interface에 있는 메서드 중 구현할 수 있는 메서드를 구현해 개발의 편의 지원

