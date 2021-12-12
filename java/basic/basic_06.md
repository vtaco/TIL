# 클래스의 구조

## 클래스

접근 권한 : public, protected, private, (defatule)

활용 방법 : final, abstract,....

> final : 자식 클래스를 가질 수 없는 클래스
>
> abstract : 객체 생성이 불가능한 추상클래스



<br>

## 변수

| 구분      | Modifier  | 설명                                                         |
| --------- | --------- | ------------------------------------------------------------ |
| 접근권한  | public    | 모든 클래스 접근이 가능                                      |
|           | protected | 동일 패키지에 속하는 클래스와 하위 클래스 관계까지 접근 가능 |
|           | private   | 변수가 선언된 클래스 내에서만 접근 가능                      |
| 활용 방법 | final     | 변수를 상수로 이용하는 경우                                  |
|           | static    | 클래스에 소속된 클래스 변수를 의미                           |

<br>

#### 접근 제한자

클래스, 변수, 메서드에 접근할 수 있는 권한을 나타내기 위해 사용

| 종류      | 클래스 | 하위 클래스 | 동일 패키지 | 모든클래스 |
| --------- | ------ | ----------- | ----------- | ---------- |
| private   | O      | X           | X           | X          |
| (defult)  | O      | X           | O           | X          |
| protected | O      | O           | O           | X          |
| public    | O      | O           | O           | X          |
|           |        |             |             |            |

접근 관련 modifier를 통해 정보 은닉을 구현할 수 있음

```java
class Care{
    private int serialNum;
    protected String name;
    int speed;
}

public class CarTest{
    public static void main(String[] args){
        Car Yellow = new Car():
        Yellow.name = 'Yellow';
        Yellow.speed = 300;
        // Yellow.serialnumber = 3060;
    }
}
```

<br>

#### 정보 은닉

캡슐화 (변수 + 메서드) 로 하나의 클래스로 묶음

==> 접근 제한자를 사용

==>>정보 은닉 (공개 + 비공개)

<br>

<br>



## 메서드

일종의 함수로서 클래스가 제공할 로직들을 정의

```java
// 접근제한자 반환형 메서드명 매개변수
public int sum (int num1, int num2){
    int sum = 0;
    sum = num1 + num2;
    return sum;
}
```

반환 값이 없다면 void를 선언

<br>

#### 접근 제한자

| 구분      | modifier                 | 설명                                                         |
| --------- | ------------------------ | ------------------------------------------------------------ |
| 접근권한  | public,protected,private | 동일                                                         |
| 활용 방법 | final                    | 오버라이딩이 불가능한 메서드를 정의                          |
|           | static                   | 클래스에 소속된 클래스 메서드를 의미, 클래스 생성 시 만들어짐 |
|           | abstract                 | 추상 메서드를 의미하며, 하위 클래스에 의해 구현              |
|           | synchronized             | Thread의 동기화를 위한 메서드                                |

<br>

#### 정보은닉

멤버 변수들은 private로 선언

public으로 지정한 메서드를 통해 사용