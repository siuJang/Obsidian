## DAtaset
RNN + Attention < Transformal
- NLP task에서 훨씬 효율적이다
- 장기의존성 문제 해결(Seq2Seq 뿐만아니라 CNN Task에서도 포함)
```필요묘듈 (pytorch보다 tensorflow 사용)
import logging

import time

import numpy as np

import matplotlib.pyplot as plt

import tensorflow_datasets as tfds

import tensorflow as tf

import tensorflow_text

```
## 데이터셋(Portuguese-English translation dataset)
- 포르투갈어 -> 영어로 기계번역하는 Task
- 52000개의 정답값으로 대응대는 포르투갈어 단어, 1200개의 문법 weight, 1800개의 테스트 데이터셋을 포함
- UTF-8로 인베딩

## Tokenizer(토큰화 과정)
- 일단 인덱스로 각 단어 토큰화
- For example, the word `'searchability'` is decomposed into `'search'` and `'##ability'`, and the word `'serendipity'` into `'s'`, `'##ere'`, `'##nd'`, `'##ip'` and `'##ity'`.
- start, end 토큰도 잊지말기


