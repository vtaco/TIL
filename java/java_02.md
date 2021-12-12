# Basic02

## 배열

**동일한 타입의 데이터 여러 개**를 하나의 **연속된 메모리 공간에서 관리**하는 것

요소에 접근하는 속도가 빠르고 크기를 변경 할 수 없음

<br>

#### 배열 만들기

타입 [] 변수명;

타입 변수명 []

**가급적 타입 바로 뒤에 붙여서 배열 형임을 알기 쉽게 표시**

- 생성

  new keyword와 함께 배열의 데이터 타입 및 크기 지정

  ```java
  int [] points = new int [3];
  //new int [3]; int 타입의 자료 3개를 저장할 수 있는 배열을 메모리에 생성
  // int [] points 는 메모리에 있는 배열을 가리키는 참조형 타입 변수
  
  ```

- 사용

  ```java
  points[0] = 1;
  points[1] = 'A'; // 묵시적 형 변환
  points[2] = 1.5; // double 할당 불가
  ```

- 축약

  ```java
  int [] b = {1,3,5,6,8};
  int [] c = new int[] {1,3,5,6,8};
  
  // err
  int [] points;
  points = {1,3,5,6,8};
  
  // good
  int [] points;
  points = new int []{1,3,5,6,8};
  ```

<br>

#### for-each with Array

가독성이 개선된 반복문으로, 배열 및 Collection 에서 사용

index 대신 직접 요소에 접근하는 변수를 제공

naturally ready only

```java
int intArray [] = {1,3,5,7,9};

for (int x : intArray){
    System.out.println(x);
}
```

**인덱스를 사용하지 않아도 되지만 인덱스를 사용할 수 없다!**

<br>

#### 배열 복사

```java
int [] scores = {90,80,100};
//err
scores[3] = 95;

//good
int [] scores2 = new int[4];
System.arraycopy(scores,0,scores2,0,scores.length);
scores2[3] = 95;

// other
scores = Array.copyOf(scores,5);
```

###### Array.copyOf()

기존 배열을 복사해서 5개짜리 새로운 배열을 만듬

scores가 보는 번지

0x100 번지 : [90,80,100] --> copyOf 후 가비지 컬렉터가 처리

0x200 번지 : [90,80,100,0,0];

<br>

#### Array is Immutable

최초 메모리 할당 이후 변경할 수 없음

**배열이 저장된 메모리를 변경할 수 없다는 것**

**배열을 가르키는 포인터는 변경할 수 있다!!**

<br>

#### System.Arraycopy

```java
public static void arraycopy (Object srt, // 출발지
                              int srcPos, // 출발지 소스의 포지션 ex)[0]번째 인덱스
                              Object dest, // 목적지
                              int destPos, // 목적지 소스의 포지션
                              int length // 길이
                             )
```

#### Max Min

```java
public class maxmin {

	public static void main(String[] args) {
		int[] intArray = { 3, 27, 13, 8, 235, 7, 22, 9, 435, 31, 54};
		
		int min = 999;
		int max = -999;
		
		for(int num: intArray) {
			if(num>max) {
				max = num;
			}
			
			if(num<min) {
				min = num;
			}
			
		}
		
		// other
		int min2 = Integer.MAX_VALUE;
		int max2 = Integer.MIN_VALUE;
		for (int num : intArray) {
			min2 = Math.min(min2, num);
			max2 = Math.max(max2, num);
		}
		
		
		System.out.printf("min : %d, max : %d\n", min,max);
		System.out.printf("min2 : %d, max2 : %d", min2,max2);

	}

}

```

<br>

#### Count

```java
import java.util.Arrays;

public class count {

	public static void main(String[] args) {
		// 카운트
		int [] intArray = {3, 7, 2, 5, 7, 7, 9, 2, 8, 1, 1, 5, 3};
		int [] used = new int[10];
		
		for(int num : intArray) {
			used[num]++;
		}
		
		System.out.println(Arrays.toString(used));
		
		// 1~20 부터 사용되지 않은 수
		int [] intArray2 = {1,3,4,7,8,10,12,15,16,17,18};
		int [] used2 = new int[21];
		
		for(int num : intArray2) {
			used2[num]++;
		}
		
		for(int i=1; i<used.length;i++) {
			if(used[i]==0) {
				System.out.print(i+" ");
			}
		}
		
		
	}

}

```

<br><br>

## 2차원 배열

int [][] [][] \[][] intArray = new int \[4][3];

할당도 가능

#### 만들기

```java
// 1,2차 선언 / 1차 생성
int [][] intArray = new int[4][]; //2차원 배열을 만들지만 길이는 지정하지 않음

// 2차 생성
intArray[1] = new int[2];
intArray[0] = new int[4];
intArray[2] = {1,2,3}; //err
```

#### 접근

```java
import java.util.Arrays;

public class array2 {

	public static void main(String[] args) {
		char[][] chars = { {'a', 'b'} , {'c','d'} };
		
		for(char[] carray:chars) {
			for(char c : carray) {
				System.out.print(c);
			}
			System.out.println();
		}
		
		System.out.println(Arrays.toString(chars));
		System.out.println(Arrays.deepToString(chars));

	}

}

```

