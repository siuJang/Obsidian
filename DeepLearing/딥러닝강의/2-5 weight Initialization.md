(선요약 : 랜덤하게 0 근처로 잡자!)
## Lecun
- uniform() 평평한 구조 사용
- W∼N(0,1/n1​)
(둘이 평균, 분산 똑같음)
## Kaiming(ReLU 사용하는 신경망)
W∼N(0,2/nin​)
## Xavier(분산이 Kaiming 방식보다 작아 sigmoid/tanh 사용하는 신경망에 적)
W∼N(0,2/nin​+nout​​)
## 만약 전부 0으로 초기화 한다면? 1로 초기화 한다면?