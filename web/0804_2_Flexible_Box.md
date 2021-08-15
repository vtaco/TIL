# CSS Flexible Box Layout

오랫동안 CSS Layout을 작성할 수 있는 도구는 float 및 positioning 뿐이었음

제한적인 한계가 있음

flexbox

1. **아이템 간 공간 배분**

2. **강력한 정렬 기능**

   을 제공하기 위한 **1차원 레이아웃 모델로 설계(상하 좌우)

<br>

<br>

## A. 요소

- flex container (부모 요소) : 레이아웃의 기본적인 모델

  <br>

- flex item (자식 요소) : 컨테이너의 컨텐츠

  <br>

  <br>

## B. 축

각각 x축 y축 중 무엇이 메인축이고 교차축인지는 사용자가 결정하는 것

- main axis(메인축)
- cross axis(교차축)

**부모를 캐치해서 부모가 정렬을 시킨다!!**

<br>

<br>

<속성>

display : flex 크기 고정 // inlineflex 안에 내부 컨텐츠 만큼 요소 차지

 

flex-direction 메인축 방향설정

 

justify-content 메인축 방향 정렬

 

align-item, align-self, aligt-contet 교차축 방향설정

 

flex-wrap, flex-flow,flex~~

===============================================================

flex-direction 

\-    row --> 

\-	row-revers <--

\-    column 아래 column-reverse 위

flex-wrap 강제로 한 줄에 배치되게 할 것 인지에 대한 여부

 

justify 메인축 

 

align 교차축 

\-    stretch :늘어남 기본값(그외에 것들은 각자 본연의 크기만큼)

 

align-self는 각 자식 요소에 구현함 다른 건 부모요소

================================================================

content 여러줄

items 한줄

self flex item 개별요소

 

================================================================

order 스타트 순서 (default)

grow 비율이 아니다! 메인축에서 남은 공간을 쪼개서 나누어준다

flex는 확실히 외워주기

around 

양쪽 붙고 공백 공백

around : 아이템의 좌우 공백이 각각 같아짐(중간에는 공백 중복이 생겨서 컨텐츠 사이 공백이 더커짐)

evenly : 그냥 전체 공백이 같음

glow : 순서 정하기

warp : 공백 뿜빠이