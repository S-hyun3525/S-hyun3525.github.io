---

layout: post

title: "자료구조"

date: 2026-04-30 10:30:00 +0900

categories: blog study

tags : [자료구조, C] 

---


# Data_Structure
원형 큐




## 큐

**QUEUE**

 - 먼저 들어온 데이터가 먼저 나가는 자료구조
 - 선입선출(FIRST IN FIRST OUT : FIFO)
 - 예) 매표소 대기열, 계산대 순서

## Quete ADT
삽입과 삭제는 FIFO 순서를 따름.
삽입은 큐의 후단, 삭제는 전단에서 이루어짐


## 선형큐

## 원형큐
- 전단과 후단을 관리하기 위한 2개의 변수 필요
	- front : 첫번째 요소 하나 앞의 인덱스
	- rear:마지막 요소의 인덱스 
## 덱(deque)
- 덱(deque)은 double-ended queue 의 줄임말
- 큐의 전단(front) 후단(rear)에서 모두 삽입과 삭제가 가능한 큐
```
-객체: n개의 element형으로 구성된 요소들의 순서있는 모임
연산 : 
create()::= 덱을 생성
init(dq)::= 덱을 초기화
is_empty(dq)::= 덱이 공백상태인지를 검사
is_full(dq)::= 덱이 포화상태인지를 검사
add_front(dq, e)::= 덱의 앞에 요소를 추가
add_rear(dq, e)::= 덱의 뒤에 요소를 추가
delect
_front(dq, e)::= 덱의 앞에 요소를 반환 후 삭제
_rear(dq, e)::= 덱의 뒤에 요소를 반환 후 삭제
get_front(q)::= 덱의 앞에서 삭제하지 않고 앞 요소를 반환
get_rear(q)::= 덱의 뒤에서 삭제하지 않고 뒤 요소를 반환
```
### 예시 시각화
```           
              전단    후단     
add_front(A)  : [A][][]
add_rear(B)   : [A][B][]
add_front(C)  : [C][A][B]
add_rear(D)   : [C][A][B][D]
delect_front(): [A][B][D]
delect_rear() : [A][B][][] 
```

추가로 필요한 **delect_rear()**와 **add_front()**함수에는 원형 큐와는 다르게
**반대방향**의 회전이 필요: 음수가 되면 MAX_QUEUE_SIZE를 더해야함
> front <- (front-1  +  MAX_QUEUE_SIZE) %  MAX_QUEUE_SIZE;
> rear <-   (front-1  +  MAX_QUEUE_SIZE) %  MAX_QUEUE_SIZE;

### 추가 질문
Q : 데이터가 포화 상태 일 때 값이 추가가 된다면
A : 주소 값에 있는 값은 지워지고 입력된 값이 저장된다

