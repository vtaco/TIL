# SQL ORM

## CRUD

### 1. CREATE

```python
User.object.create(
	컬럼 = 값,
    컬럼 = 값,
    컬럼 = 값,
	컬럼 = 값
)
```

<br>

<br>

<br>

### 2. READ

```sql
SELECT * FROM users;
```



```python
User.objects.all()
```

<br>

<br>

<br>

### 3. UPDATE

```sql
UPDATE 테이블 SET first_name = '철수' WHERE id=101;
```

```python
user = USER.object.get(pk=101)
user.first_name = '철수'
user.save()

```

<br>

<br>

<Br>

### 4. DELETE

```sql
DELETE FROM users WHERE id = 101
```



```python
User.objects,get(pk=101).delete()
```

<br>

<Br>

<br>

## ORM FUNCTION

#### 1. COUNT

```sql
SELECT COUNT(*) FROM users;
```

```python
User.objects.count()
```

<br>

<br>

<br>

#### 2. FILTER

```sql
SELECT first_name FROM users WHERE age=30
```

```python
User.objects.filter(age=30).values('first_name')
```

filter로 거른 값 중에서 first_name을 출력

<br>

<br>

<br>

#### 3. column\_\_gte,  \_\_gt, \_\_lte, \_\_lt

```sql
SELECT COUNT(*) FROM users WHERE age>=30;
```

```python
USER.objects.filter(age__lte=30).count()
```

<Br>

<br>

<br>

#### 4. AND

```sql
SELECT COUNT(*) FROM users WHERE age = 30 AND last_name='김';
```



```python
User.objects.filter(age=30, last_name='김').count()
```

<br>

<br>

<br>

#### 5. OR

```sql
SELECT COUNT(*) FROM users WHERE age = 30 OR last_name='김';
```

```python
from django.db.models import Q
User.objects.filter(Q(age=30) | Q(last_name='김'))
```

<br>

<br>

<br>

#### 6. Start

```sql
SELECT COUNT(*) FROM users WHERE phone LIKE '02-%';
```

```python
User.objects.filter(phone__startswith='02-').count()
```



<br>

<br>

<br>

#### 7. 정렬

```sql
SELECT * FROM users ORDER BY age DESC LIMIT 10;
```

```python
User.objects.order_by('-age')[:10]
```

**Default는 ASC -는 거꾸로해서 DESC!!**

<br>

```sql
SELECT * FROM users ORDER BY last_name DESC, first_name LIMIT 1 OFFSET 4;
```



```python
User.objects.order_by('-last_name', 'first_name')[4]
```

<br>

<br>

<br>

#### 8. Aggregation

AVG, MAX, MIN, SUM 동일

```sql
SELECT AVG(age) FROM users Where last_name='김'
```



```python
from django.db.models import Avg
User.objects.filter(last_name='김').aggregate(Avg('age'))
```



