## Human language and word meaning
원핫인코딩 -> 단어의 의미를 이해하기엔 제한적임
그래서 의미끼리 연관을 짓어보자고 생각해봄
Distributional semantics : 의미끼리 단어의 관계가 가깝다면 벡터 등에서 서로 가깝게 연결
우리는 각각의 단어에대해 단어벡터를 갖게 될것
**Word vectors**(단어벡터) : also called **word embeddings** or **word representations**
## Word2vec: Overview
Word2vec : framework for learning **word vectors**
중심단어를 C 그 밖 문맥단어를 O라 부르기로 함
C를 선택하고 O에게 확률을 부여하는 방식으로 작동
### objective function
L()