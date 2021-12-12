# SQL

RDBS의 **데이터 관리**를 위해 설계된 **특수 목적 프로그래밍 언어**

<bR>

<br>

## DDL

#### 1. CREATE

```sqlite
CREATE TABLE tablename(
	id INTEGER PRIMARY KEY,
    name TEXT
);
```

<br>

<Br>

#### 2. DELETE

```sqlite
DROP TABLE tablename;
```

<br>

<br>

cf) .tables --> 테이블 종류 확인

​	.schema tablename --> 테이블 schema 확인

<Br>

<Br>

#### 3. ALTER

- 테이블 이름을 바꾸는 경우

  ```sql
  ALTER TABLE 기존이름 RENAME TO 새로운이름;
  ```

  <br>

- column을 수정하는 경우

  ```sql
  ALTER TABLE 테이블 ADD COLUMN 컬럼이름 컬럼타입
  ```

  ### NOT NULL 주의

  not null을 그냥 넣는 다면 실패한다

  **테이블에 있던 기존레코드들에는 새로 추가할 필드에 대한 정보가 없다**

  그렇기 때문에 NOT NULL 형태의 컬럼은 추가하면 안된다

  단, 필요한 경우 디폴트 값을 함께 입력해주어야한다

  ```sql
  ALTER TABLE 테이블 ADD COLUMN 컬럼이름 컬럼타입 NOT NULL DEFAULT 'DEFAULT_VALUES';
  ```

  

  

<br>

<br>

<br>

## DML

#### 1. CREATE

**INSERT**

```sql
INSERT INTO 테이블 이름 (컬럼, 컬럼, 컬럼,) VALUES (값,값,값,), (값,값,값),...;
```

**INSERT는 특정 테이블에 레코드를 삽입**

**모든 열에 데이터가 있는 경우 column을 명시하지 않아도 됨**

<br>

SQLite는 따로 **PRIMARY KEY 속성의 컬럼을 작성하지 않으면** 값이 자동으로 증가하는 PK 옵션을 가진 **rowid 컬럼** 이 있다

cf) 꼭 필요한 정보라면 공백으로 바꾸면 안된다 ***NOT NULL 속성***

<br>

<br>

#### 2. READ

* **SELECT**

  테이블에서 데이터를 조회

  ```sql
  SELECT 컬럼, 컬럼, ... FROM 테이블;
  ```

  

<br>

- **LIMIT**  with **OFFSET**

  조회하는 개수 지정 with 행이 시작할 지점정하기

  ```sql
  SELECT 컬럼 FROM 테이블 LIMIT 숫자 OFFSET 행의 숫자;
  ```

  

  <br>

- **WHERE**

  반환되는 행을 특정 조건으로 검색

  ```sql
  SELECT 컬럼, 컬럼, FROM 테이블 WHERE 조건;
  ```

  

  <br>

- **DISTINCT**

  중복 제거

  ```sql
  SELECT DISTINCT 컬럼(기준) FROM 테이블;
  ```

<br>

<br>

#### 3. DELETE

```sql
DELETE FROM 테이블 WHERE 조건
```

### 중복 불가능한 값인 rowid를 기준으로 삭제

SQLite 기본적으로 id 재사용

id INTEGER PRIMARY KEY AUTOINCREMENT 를 CREATE할 떄 사용하면 자동으로 증가하고 ID를 재사용하지 않는다.

<br>

<br>

#### 4. UPDATE

행수정

**중복 불가능한 값인 rowid를 기준으로 수정**

```sql
UPDATE 테이블 SET 컬럼 = 값, 컬럼 = 값,... WHERE 조건;
```

<br>

<br>

#### + WHERE

```sql
SELECT age,last_name FROM 테이블 WHERE age>=30 AND last_name='김';
```



<br>

<Br>

<br>

## SQL Function

- COUNT
- AVG
- SUM
- MIN
- MAX

```sql
SELECT FUNTCION(숫자) FROM 테이블
```

<br>

<br>

<br>

## LIKE

패턴 일치를 기반으로 테이블을 조회

| wildcards | 설명                                |
| --------- | ----------------------------------- |
| %         | 0개 이상 (있을 수도 없을 수도) 문자 |
| _         | 임의의 단일 (반드시 1개)            |

```sql
SELECT * FROM 테이블 WHERE 컬럼 LIKE '와일드 카드 패턴'
```



ex)

```sql
SELECT * FROM users WHERE age LIKE '1_';
SELECT * FROM users WHERE age LIKE '02-%';
SELECT * FROM users WHERE age LIKE '%준';
SELECT * FROM users WHERE age LIKE '%-5114-%';

```

<br>

<Br>

<br>

## ORDER BY

조회 결과를 절령

- ASC - 오름차순(default)
- DESC - 내림차순

```sql
SELECT * FROM users ORDER BY age ASC LIMIT 10;
```

<br>

<br>

<br>

## GROUP BY

행 집합에서 요약 행 집합을 만든다

```sql
SELECT last_name, COUNT(*) as name_count FROM users GROUP BY last_name;
```

<br>

<br>

<Br>



