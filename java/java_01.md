# Basic01

## Varialbe 이란

수학에서는 변하는 수

컴퓨터에서는 메모리 공간, 그릇

값(Value)을 할당(assign) 후 사용

타입별로 크기가 달라집



## Type이란

1. Primitive Type(기본형)
   - 미리 정해진 크기 메모리 사이즈로 표현
   - 변수 자체에 값 저장
2. Reference Type(참조형)
   - 미리 정해질 수 없는 데이터의 표현
   - 변수에는 실제 값을 참조할 수 있는 주소만 저장
   - 별도의 공간(heap)



#### 변수 할당

```java
...
    // O
    final int i = 10;
	// blank 상태일 떄는 값을 할당 할 수 있음
	// final int i;
	System.out.println(i);


	//상수 값은 한번 정해지면 변경 할 수 없다
	//X
	i = 20;
	System.out.println(i);

...


```



#### 형 변환

변수의 타입을 다른 타입으로 변환하는 것

기본형은 기본형끼리, 참조형은 참조형끼리 형변환

boolean은 다른 기본 타입과 호환되지 않음

```java
...
    // 손실
{
    int i = 10;
    byte b = i; // X
    byte b = (byte)i; // O
}

{
    byte b = 10;
    int i = b;
}
...
```

#### 묵시적 vs 명시적 형 변환

- 형 변환 ex1

```java
// 묵시적 형 변환
byte b = 10;
int i = b;

// 명시적 형 변환
int i = 300;
byte b = (byte)i;
```



- 형 변환 ex2

```java
int k = 66;
char c = (char)k; //형변환
System.out.println(c); // B

char c = 'A';
k = c; // 형변환
System.out.println(k); // 65


```



#### 변수 할당

```java
string s1 = "Hello"; //X
String s2 = "Hello"; //O
String s3 = new String("Hello"); //O
char[] s4 = "Hello"; //X

```

## 연산자

최소 연산자의 타입은 **int**

```java
// 최소 연산자의 타입
byte b1 =10;
byte b2 = 20;
byte b3 = b1 + b2; //err 

// 타입은 일치하나 
// 연산 결과를 int 형으로 저장하려 하여 에러
int i1 = 10;
long l1 = 20;
int i2 = i1 + l1; // long타입으로 연산이 됨

```

#### 오버 플로우

```java
int i1 = Integer.MAX_VALUE;
int i2 = i1+1;

System.out.println(i2);

long l1 = i1+1; //err
long l2 = (long)(i1+1); // err
long l3 = (long)i1 + 1; // good

```

#### float vs double

``` java
// 실수 계산의 부정확성
float f1 = 2.0f;
float f2 = 1.1f;
float f3 = f1 - f2; //0.9

double d1 = 2.0;
double d2 = 1.1;
double d3 = d1 - d2; // 0.899999


System.out.println((int)(d1*100) - (int)(d2*100)/100.0);

BigDecimal b1 = new BigDecimal("2.0");
BigDecimal b2 = new BigDecimal("1.1");
System.out.println(b1.substract(b2)); // 0.9
```

<br>

<br>

## Random

#### Math

```java
Math.random();
// 0.0 <= ? <1.0
    
Math.random()*N;
// 0.0<= ? <N.0

(int)(Math.random() * N);
// 0 <= ? < N.0

(int)(Math.random() * N)+1;
// 1 <= ? < N
    
```

#### rand

```java
rand.nextInt(N);
// 0 <= ? <= N
```



## switch vs if

- 가능한 타입

```java
switch( _ )
// Type =  byte,short,char,int x;
    
if ( _ )
// Type = boolean
```

- Duplicate case

```java
char C = 'A';

switch (C){
    case 'A':
        break;
    case 'B':
        break;
    case 65 :
        break;
}
```

> A는 65 
>
> switch에서 형변환이 자연스럽게 이루어져서 문제가 발생

<br>

## 반복문

- base

```java
int N = 6;
int sum = 0;
double avg = 0;

Random rand = new Radom();

// 주사위를 100번 던진 결과의 합과 평균
```



- for

``` java
for (int i =0; i < 100; i++){
    sumt += rand.nextInt(N) +1;
}

avg = sum/100.0; //실수로
```

- while

```java
while(i<100){
    sum += rand.nextInt(N) +1 ;
    i++;
}
```

- do-while

```java
do{
    sum+=rand.nextInt(N)+1;
    i++;
}while(i<100);
```

