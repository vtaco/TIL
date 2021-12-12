# Django

## 1. 모델

단일한 데이터에 대한 정보를 가짐

모델을 통해 데이터베이스 **테이블**에 접근

### 모델 != 데이터베이스

<br>

<br>

#### 데이터베이스

- 스키마 : 데이터베이스 구조

  데이터 베이스의 구조와 제약 조건에 관련한 전반적인 명세를 기술한 것

 <br>

- 테이블

  모델을 사용해 조직된 데이터 요소들의 집합. (관계라고도 표현)

  1. 열(column) : 필드 속성
  2. 행(row) : 레코드/ 튜플
  3. 키(pk) 

<br>

**모델은 데이터를 구조화하고 조작하기 위한도구**

<Br>

<br>

<br>

## 2. ORM

호환되지 않는 유형의 시스템 간에(장고 <-> sql) 데이터를 변환하는 프로그래밍 기술

장점: sql을 알지 못해도 db 조작이 가능 // 객체지향적 접근으로 높은 생산성

단점 : 완전한 서비스 구현이 어려운 경우 

`But` 현대 웹 프레임워크의 요점은 웹 개발의 속도를 높이는 것

<br>

**디비를 객체로 조작하기 위해 ORM을 사용한다. **

<br>

<Br>

#### CharField

```python
CharField(max_length=None, **options)
```

길이 제한이 있는 문자열을 넣을 때 사용

CharField의 max_length는 **필수 인자**

필드의 최대 길이(문자), 데이터베이스 레벨과 Django의 유효성 검사

<br>

<br>

#### TextField

```python
TextField(**options)
```

글자의 수가 많을 때 사용

max_lengt 옵션 작성시 자동 양식 필드인 textarea 위젯에 반영은 되지만

모델과 데이터베이스 수준에는 적용되지 않음 --> max_length 사용은 CahrField에서 사용해야함

기능적으로는 동작하나 걸러내지 못함

<br>

<br>

#### DateTimeField

auto_now_add = True 시간 변경 반영 X

auto_now = True 수정될때 시간 반영 O

<br>

<br>

<br>

## 3. Migrations

![img](file:///C:/Users/woosj/AppData/Local/Temp/msohtmlclip1/01/clip_image002.jpg)

(일반적으로 바로 런서버했을 때 뜨는거)

<br>

### migrations == 장고가 모델에 생긴 변화를 DB에 반영하는 방법

<br>

<br>

#### makemigrations

모델을 변경한 것에 기반한 새로운 마이그레이션을 만들 때 사용

`class Article`을 db에서 사용 할 수 있는 설계도로 바꾸어서 디비로 보내야함

이 동작은 설계도를 만들었을뿐 사용하지 않음 **즉, 아직 db는 비어 있음**

```bash
python manage.py makemigrations
```

<br>

<br>

#### migrate

마이그레이션을 db에 반영하기위해 사용

설계도를 실제 디비에 반영하는 과정 디비 스키마가 동기화를 이룸

```bash
python manage.py migrate
```

<br>

<br>

#### sqlmigrate

마이그레이션에대한 sql 구문을 보기위해 사용

```bash
python manage.py sqlmigrate articles 0001
```

<br>

<br>

#### showmigrations

마이그레이션 파일들이 마이그레이트 됐는지 여부 확인 할 수 있음

<br>

<br>

## 4. DB API

디비를 조작하기 위한도구 (파이썬에선 객체로사용)

ex)Article.objects.all() ==> 모든 게시글 조회 구문

클래스네임. 매니저.쿼리셋 API

<br>

<br>

#### 매니저

중간에 다리 역할(objects)

장고 모델에 데이터베이스 쿼리 작업이 제공되는 인터페이스

어떤 모델 클래스를 만들건 오브젝트가 만드러짐

중요한건 뒤에 나오는 API

 

쿼리셋

데이버테이스로부터 전달받은 객체 목록

데이터베이스로부터 조회 필터 정렬