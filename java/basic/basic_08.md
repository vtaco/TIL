# 오버로딩과 매개변수

## 메서드 오버로딩

**클래스 안에 동일한 이름의 변수를 사용할 수 없음**

but 메서드는 가능함

<br>

매개변수의 개수와 타입을 통해 실행될 메서드를 구분할 수 있기 때문

**하나의 클래스에 동일한 이름의 메서드가 여러 개 중복 정의 되는 것**

```java
public class Employee {
    String name;
    int age;
    
    void setEmployee(String name, int age){
        this.name = name;
        this.age = age;
    }
    void setEmployee(String name){
        this.name = name
    }
}
```

`Q. 메서드 오버로딩이 필요한 이유`

`A. 매개변수로 들어오는 데이터 타입이 종류가 여러개 일 수 있음`

> 모든 데이터 타입별로 printXXX()메서드를 각각 정의하는 것은
>
> 많은 출력 메서드를 필요로 하며 호출하는 코드에서 많은 수정이 발생함
>
> 이를 해결할 수 있음

###### 주의

리턴 타입이 다른 것은 오버로딩 X

매개변수 이름만 다른 것은 오버로딩 X

순서가 다른 것은 오버로딩 O

형변환이 되는 것 오버로딩 O

<br>

`Q. 생성자 오버로딩을 지원하는 이유`

`A.  필요한 변수들만 적절히 초기화하기 위해서`

<br>

<br>

#### 생성자에서  this() 메서드

```java
public class Employee {
    int employeeNo;
    String anem;
    int age;
    
    public Employee(){
        this(0,'a',0);
    }
    
    public Employee(int employeeNo, String name){
        this.employeeNo = employeeNo;
        this.name = name;
    }
    
    public Employee(int employeeNo, String name, int age){
        this(employeeNo,name);
        this.age = age;
    }
}
```



<br>

<br>

<br>

## 매개변수

메서드가 호출 해서 객체간 메시지가 전달될 때 사용



#### 1. 값에 의한 호출(Call by value)

1. 매서드를 호출할 때 실 매개변수 값이 넘어감
2. 호출되는 메서드의 인자에 복사함
3. 실 매개변수 값은 영향을 받지 않음

<br>

#### 2. 주소에 의한 호출

참조하는 객체의 주소 값이 **복사**되어 전달됨