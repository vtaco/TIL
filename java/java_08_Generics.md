# Generics

다양한 타입의 객체를 다루는 메서드, 컬렉션 클래스에서 **컴파일 시에 타입 체크**

클래스 또는 인터페이스 선언 시 `<T>`에 타입 파라미터 표시

```java
public class Class<T>{}
public interface Interface<T>{}
```

**특별한 의미의 알파벳보다 단순히 임의의 참조형 타입을 말함**

```java
class NormalBox{
    private Object some;
    
    public Object getSome(){
        return some;
    }
    
    public void setSome()
}
```

