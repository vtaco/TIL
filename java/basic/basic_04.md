# 자바 제어문

if / if-else

조건에 따른 단순 분기 처리

if -else if // switch

조건에 따른 다중 분기 처리

<br>

## 조건 제어문

### if 문

```java
if(Expression){
    Statement1;
} else if(Expression2) {
	Statement2;    
} else {
    Statement3;
}

```

<br>

### switch 문

```java
switch (Expression){
    case value1:
        Statement1;
        break;
    case value2:
        Statement2;
        break;
	default :
        Statement3;
        break;
}
```

<br>

<br>

## 반복 제어문

for /while

조건에 따른 특정 문장이 수행되지 않을 수 있음

do-while

무조건 한 번 이상 수행됨

### for문

```java
for(초기식; 조건식; 증감식){
    Statement1;
}
```

<br>

### while 문

```java
while(조건식)
{
    Statement1;
}
```



<br>

### do-while문

```java
do {
    Statement1;
} while(조건식);
```



<br>

<br>

## 이동 제어문

break

해당하는 블록을 종료



continue

반복문에서 현재 단계의 수행을 생략하고 다음 단계를 진행



return

메서드의 수행을 종료하고 호출된 것으로 이동



