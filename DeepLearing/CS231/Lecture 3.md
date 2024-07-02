## Loss값을 구하는 2가지 방법
### SVM 
수식은 ppt 참조
0이나 틀린레이블점수 - 맞은레이블 점수 +1 의 값들의 합으로 레이블 별 loss를 구한 뒤 각 레이블들의 loss값 합들을 로스값 수로 나누면 총 loss값이 도출된다.
각 레이블의 loss값의 합이아닌 평균으로 구하면 어떻겟냐?
=> 큰 의미는 없다
각레이블을 구할때 제곱을 해버린다면?
=> 이렇게 하는경우도 있지만 제곱을 한다면 none linear하기때문에 차이가있다
loss값중 될수잇는 최저값가 최고값은?
=> 최저값은 0이고 최고값은 무한대가 될수있다
일반화를 하면 레이블의개수-1이 레이블의 loss값이 된다 이걸 활용하면 학습이 시작이 제대로된 값이 도출되는지 확인할 수 있다.
```python
def L_i_vectorized(x,y,W):
	scores = W.dot(x)
	margins = np.maximum(0, scores - scores[y] + 1)
	margins[y] = 0
	loss_i = np.sum(margins)
	return loss_i
```
위 식의로 loss 값이 0이 나오는 W값이 과연 유니크할까?
=> 아니다 w값이 유니크하지않고 중보될수있다
따라서 **weight Regularization**이 필요하다
데이터로스는  학습용데이터에 최대한 w를 일반화하는것이고 레귤러제이션 항에선 w를 테스트셋에 최대한 일반화시키며 서로 싸우는 느낌이다
#### Weight Regularization
자주쓰는 wr 
- L2 regularization(가장많이쓰임)
weight를 최대한 spread out해서 모든 input feature를 고려하게 만듬
- L1 regularization
- Elastic net(L1+L2)
- Max norm regularization
- Dropout
### Softmax Classifier
- class를 log화한 확률

Softmax VS SVM
- softmax를 더 많이 사용함
- svm은 loss값이 불변함
- softmax는 모든 인자를 고려하기에 loss값이 바뀜
- 