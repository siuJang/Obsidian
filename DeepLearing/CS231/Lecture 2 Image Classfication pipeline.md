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