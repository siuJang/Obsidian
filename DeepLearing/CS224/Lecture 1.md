## Human language and word meaning
원핫인코딩 -> 단어의 의미를 이해하기엔 제한적임
그래서 의미끼리 연관을 짓어보자고 생각해봄
Distributional semantics : 의미끼리 단어의 관계가 가깝다면 벡터 등에서 서로 가깝게 연결
우리는 각각의 단어에대해 단어벡터를 갖게 될것
**Word vectors**(단어벡터) : also called **word embeddings** or **word representations**
## How do we represent words?
### 1)WordNet
어떠한 단어의 유의어, 상하관계(분류 등)을 알수있음
limitation
유의어를 문맥마다 다르게쓰는게 있는데 구분하지못함
신조어 갱신 힘듬
### 2)discrete symbols
one-hot vectors로 표현함
차원 중 하나만 1이고 나머진 0이기 때문에 비효율적임
유사도를 반영할 수 있는 방법이 없음 why -> 보통 유사도를 구할 때는 내적을 통해 구하는데 자기 자신을 제외하고는 내적하면 0이기 때문에(orthogonal) 힘듬
### 3)Representing words by their context
context의 주위단어를 통해  단어를 유추함 
window size가 5라면 양옆에 5개의 단어로 유추
차원을 2차원에 축소시켜서 visualize하면 비슷한 단어끼리 집합된걸 확인 할 수 있음
### 4)Co-occurrence Matrices
좃구림
### 5)Word2vec
nueral network를 사용!
#### Skip-gram model
center word를 기준으로 (window size만큼)주변단어를 구하는 확률를 계산하는방법!
Likelihood수식(자료참고)
Negative log likelihood
->log랑 음수를 취해줌
->이점은 곱을 합으로 바꿔줌 arithmetic 
Softmax function