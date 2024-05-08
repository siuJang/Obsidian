---
tags:
  - data_structure
---
## Stack 개념
- LIFO :데이터 출입 통로가 하나
- TOP : 최상위 데이터 위치를 의미
- PUSH : 데이터를 추가하는 동작 데이터를 추가 할 때마다 TOP 변경
- POP : 데이터를 빼내는 동작 빼낼 때마다 TOP변경
- EX : 웹 뒤로가기, Undo(Ctrl+Z)
- 구현방법 : 노드를 이용한코딩, 파이썬 list를 활용한 코딩
## Stack에 필요한 메소드
- TOP 생성
- PUSH
- POP
- 데이터출력
- 스택크기출력
## 단순연결리스트 NODE
### push동작
- newNode생성
- newNode.next = self.top
- self.top = newNode
- 스택크기 증가
### POP동작
- TOP에 대한 임수변수 지정
- self.top = self.top.next
- 입
