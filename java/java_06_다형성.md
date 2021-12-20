# 다형성 (Polymorphism)

하나의 객체가 많은 형(타입)을 가질 수 있는 성질

**상속 관계**에 있을 때 ***조상 클래스의 타입으로 자식 클래스 객체를 레퍼런스*** 할 수 있다.

<br>

##### 상속관계

Venom --> Hero --> Person --> Object

`Q1. ?`

`Hero only = new Hero();`



`Q2. ?`

`Person oersib = only;`



`Q3. ?`

`Object obj = only;`



`Q4. ?`

`Venom venom = only;`

<br>

<br>

## 다형성의 활용1

**배열** : 같은 타입의 데이터를 묶음

#### 다형성으로 다른 타입의 데이터 (Hero, Person)를 하나의 배열로 관리

```java
void Poly(){
    Person [] persons = new Person[10];
    Person[0] = new Person();
    Person[1] = new Hero();
}
```

##### Oject는 모든 클래스의 조상

```java
public ArrayList(int initialCapacity){
    ...
        this.elementData = new Oject[initialCapacity];
    ...
}
```

<br>

<br>

## 다형성의 활용 2

**매개 변수의 다형성**

무언가를 출력하고 싶다!!!

메서드가 호출되기 위해서는 메서드 이름과 파라미터가 맞아야함

```java
public void println(Object x){
    ...
}
```

<br>

<br>

## 다형성과 참조형 객체의 형 변환

메모리에 있는 것과 사용할 수 있는 것의 차이

| Class  | Method   | 참조 영역     |
| ------ | -------- | ------------- |
| Hero   | attack   | 히어로 영역   |
|        | fireWeb  | 히어로 영역   |
| Person | name     | 사람 영역     |
|        | run      | 사람 영역     |
| Object | equals   | 오브젝트 영역 |
|        | toString | 오브젝트 영역 |

#### 형 변환 명시적/묵시적 동일

```java
// 묵시적 형변환
Person person = new Person();
Object obj = person;

// 명시적 형변환
Person person = new Hero();
Hero hero = (Hero)person
```

<br>

<br>

#### 무늬만 형변환?

```java
// 부적절한 형변환
Person person = new Person();
Hero hero = (Hero) person;
hero.attack();
```

> person은 Person형으로 선언되어 메모리에 할당이 됨
>
> 그리고 명시적 형변환으로 person을 hero에 할당을 했지만
>
> 메모리에 올라갈때믄 Person 형으로 올라 갔기에
>
> attack(), fireWeb은 쓸 수가 없음

<br>

<br>

#### 클래스 타입 확인(instanceof)

```java
Preson preson = new Preson();

if (person instanceof Hero){
    Hero hero = (Hero)person;
}
```

<br>

<br>

### 정리

상속 관계에서 객체의 **멤버 변수가 중복**될 때

**참조 변수의 타입에 따라**연결이 달라짐

<br>

상속 관계에서 객체의 **메서드가 중복**될 때

무조건 **자식 클래스의 메서드가 호출**됨

