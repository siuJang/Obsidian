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

