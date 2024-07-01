![[cs231n_2017_lecture2.pdf]]
- 이미지는 숫자로 구성된 3d Array로 구성되어있
- 이미지 구성 예)300(height)x100(width)x3(rgb)

이미지 분석에 문제점들
- Viewpoint Variation(보는 시각)
- Illumination(조명)
- Deformation(독특한 형태)
- Occlusion(은폐, 은닉)
- Background clutter(배경과 구분x)
- Intraclass variation(같은 종)

이미지 분석의 기본적인 함수 형태
```python
def predict(image)
# ????
return class_label
```
문제점 -> 하드코딩 할만한 명확한 알고리즘이 없음
이미지에 엣지같은 패턴을 분석하여 이미지를 분석해내려는 시도가 있었지만 한계가 많았다 
-> 그래서 데이터에 기반한 이미지 분석법이 나옴

**Data-driven approach**
1. 이미지와 레이블의 데이터셋을 모은다
2. 이미지 classfier 를 학습시키고
3. 학습시킨 이미지 classfier를 평가함
```python
def train(train_images, train_labels):
#build a model for images -> labels..
return model

def predict(model, test_images):
#predict test_labels using the model..
return test_labels
```
## 첫번째 실습
First classifier : Nearest Neighbor Classifier
1. 학습 단계 : 각각의 이미지와 레이블을 기억시키게함
2. 예측 단계 : 테스트 이미지를 모든 트레이닝 이미지 하나하나와 모두 비교하고 가장 비슷한 트레이닝 이미지로 예측을 함
데이터셋 : CIFAR-10
10 labels
50000 training images(32x32)
10000 test images
How do we compare the imagers? => distance metric
L1 distance
$$ D_{L1}(\mathbf{p}, \mathbf{q}) = \sum_{i=1}^{n} |p_i - q_i| $$
```python
import numpy as np

class NearestNeighbor:
  def __init__(self):
    pass

  def train(self, X, y):
    """ X는 각 행이 하나의 예제를 나타내는 N x D 크기입니다. Y는 크기가 N인 1차원 배열입니다 """
    # X = N은 데이터 샘플의 수(60000) D는 각 샘플의 특징 수 이므로 CIFAR-10의 경우 각 이미지는 32x32 픽셀이고 3개의 채널을 가지므로 D = 32*32*3
    # Y 의 n은 데이터 샘플의 수이므로 60000개며 각 값을 이미지가 속하는 클래스(cifar-10의 경우) 0~9까지의 정수를 나타낸다.
    # the nearest neighbor classifier는 단순히 모든 데이터를 기억
    self.Xtr = X
    self.Ytr = y
  
  def predict(self, X):
    """ 여기서의 x는 테스트이미지 """
    num_test = X.shape[0]
    # lets make sure that the output type matches the input type
    Ypred = np.zeros(num_test, dtype = self.Ytr.dtype)

    # loop over all thest rows
    for i in range(num_test):
      # find the nearest training image to the current test image
      # using the L1 distance (sum of absolute value differences)
      distances = np.sum(np.abs(self.Xtr - X[i,:]), axis = 1)
      min_index = np.argmin(distances) # get the index with smallest distance
      Ypred[i] = self.Ytr[min_index] # predict the label of the nearest example

    return Ypred
```
=> 데이터셋이 늘어날수록 테스트연산이 늘어남

distance의 종류
- 유동적으로 선택해야 하기에 하이퍼 파라미터임
1.L1 distance
2.L2 distance

K-Nearest Neighbor
- k개의 가장 가까운 이미지를 k개들의 이미지가 다수결로 판단하는 것
- 일반적으로 그냥 nearest neighbor보다 성능이 좋음

nearest neighbor에 학습데이터를 넣으면?
=> 정답률은 100%가 됨 이미 있는 중
k-nearest neighbor에 학습데이터를 넣으면?
=> 첫번째 사진은 무조건 같은 사진이기에 정답이지만 2번째 비교군부터는 엉뚱한 답을 들고올수있기에 다수결로인해 순위가 바뀔수있다.

따라서 어떤 디스턴스, k가 몇일때 가장 적합할까?
=> 문제에 따라 모두 다름 따라서 실험해보고 퍼포먼스가 제일 잘나오는 하이퍼 파라미터를 선택해야함

그렇다면 실험할 때 testdata를 써야하나?
=> 그렇다면 실제로 테스트 할때 정답률이 비정상적으로 높을 수 있기에 하면안된다

따라서 **validation data**(트레이닝 데이터의 일부분)를 떼서 실험하는 것임
만약 트레이닝 데이터가 적다면?
=> **Cross-validation** 을 하면됨
사진보며이해 1234로 트레이닝하고 5로 테스트
2345로 트레이닝하고 1로 테스트 이런식으로 5번 반복하며 하이퍼파라미터값 찾기

k-nearest neighbor는 사용하면안된다
- 테스트에서 끔직한 performance를 보여줌
- 디스턴스 값이 같으면 같다고 인식하기에 다른이미지여도 디스턴스값이 같은경우 사진도 같다고 인식하는 문제점이 있음

##  Linear Classfication

