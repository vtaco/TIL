#  제한자

클래스, 변수, 메서드 선언부에 함께 사용되어 부가적인 의미 부여

-  접근 제한자
  - public
  - protected
  - default = package
  - private
- 그 외 제한자
  - static : 클래스 레벨의 요소 설정
  - final : 요소를 더 이상 수정할 수 없게함
  - abstract : 추상 메서드 및 추상 클래스 작성

<br>

<br>

## final

마지막, 더 이상 바뀔 수 없음



- class  : 상속 금지 -> 오버라이드 방지

  **이미 완벽한 클래스들**

- method : 오버 라이드 금지

- variable : 상수화

<br>

<br>

## 접근 제한자

```java
public class Parent {
	
	int defaultVar;
	public int publicVar;
	protected int protectVar;
	private int privVar;
	
	public void useMember() {
		this.defaultVar = 0;
		this.publicVar = 10;
		this.protectVar = 20;
		this.privVar = 30;
	}
}

public class Child extends Parent {
	
	public void useMember() {
		this.defaultVar = 1;
		this.publicVar = 11;
		this.protectVar = 21;
		
		//프라이빗이라 접근 불가
		//this.privVar = 31;
		
		//선언이 안되서 접근 불가
		//this.some = 41;
	}
}

public class Some {
	
	public void method() {
		Parent p = new Parent();
		p.defaultVar = 2;
		p.publicVar = 12;
		p.protectVar = 21;
		
		// p.priVar = 31;
	}

}

```

<br>

<br>

<br>

## 데이터 은닉과 보호(Encapsulation)

`Q. 누군가 외부에서 접근하여 정보를 마음대로 바꿀 수 있다?`

`A. Private로 막기`

> 공개되는 메서드를 통한 접근 통로 마련
>
> setter / getter

```java
class UserInfo {
	// 이름은 null 이 될 수 없음.
	private String name = "홍길동";
	
	private int account = 10000;

	
	// name 과 account에 부적절한 값이 할당되지 못하도록
	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAccount() {
		return account;
	}

	public void setAccount(int account) {
		this.account = account;
	}
	

}

public class UserInfoTest{
	public static void main(String[] args) {
		UserInfo info = new UserInfo();
		
		System.out.printf("사용자 정보:%s %d%n",info.getName(),info.getAccount());
		info.setName("이순신");
		info.setAccount(50000);
	}
}
```

<br>

<br>

#### 객체 생성 제어

**여러 개의 객체가 필요 없는 경우**

- 수정 가능한 멤버 변수가 없고 기능만 있는 경우
- stateless 한 객체

객체를 계속 생성/삭제 하는데 많은 비용이 들어서 재사용이 유리한 경우

<br>

<br>

#### Singleton 디자인 패턴

외부에서 생성자 접근 금지 -> 생성자의 접근 제한자를 private로 설정

내부에서 private에 접근 가능하므로 직접 객체 생성

외부에서 private  member에 접근 가능한 getter 생성

객체 없이 외부에서 접근할 수 있도록 getter와 변수에  static 추가



```java
public class Singleton {
	
	// 나만 만들 수 있음
	private static Singleton s = new Singleton();
	
	// 외부에서 만들 수 있따면 싱글톤 의미 없음	
	private Singleton() {}
	
	// 이걸 통해 써라
	
	public static Singleton getSingleton() {
		return s;
	}

}

public class SingletonTest {

	public static void main(String[] args) {
//		Singleton s1 = new Singleton();
//		
//		Singleton s2 = new Singleton();

		Singleton s1 = Singleton.getSingleton();
		Singleton s2 = Singleton.getSingleton();
		
		System.out.println(s1==s2);
	}

}


```

