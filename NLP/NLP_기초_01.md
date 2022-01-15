-
-

### 1. Bag of Words
- 단어 순서에 관계 없이 단어들의 출현 빈도(frequency)에만 집중하는 텍스트 데이터의 수치화 표현 방법
  - ![캡처](https://user-images.githubusercontent.com/43491168/149614682-37475a72-bf09-4976-9b9f-86d3240d96a4.PNG)
- 활용
  - 문장의 유사도 측정
  - 머신러닝 모델의 입력값으로 사용 가능
- 단점
  - Sparsity : 전체 단어를 기준으로 차원이 매우 크다
  - 출현 빈도가 높아 짐에 따라 영향도가 커짐
  - 단어의 순서 무시(문맥 무시)
  - 하습되지 않은 데이터에 대한 문제
  - 
### 2. n-gram
- 연속적인 n개의 토큰(word, character)으로 구성된 것
  - EX) 1-gram(unigram) : 
    - word level : [fine, thank, you]
    - character level : [f, i, n, e, , t, h, a, n, k, , y, o, u]
  - EX) 2-gram(bigram) : 
    - word level : [fine thank, thank you]
    - character level : [fi, in, ne, e , t, th, ha, an, nk, k , y, yo, ou]
  - EX) 3-gram(trigram) : 
    - word level : [fine thank you]
    - character level : [fin, ine, ne , e t, th, tha, han, ank, nk , k y, yo, you]
- Why n-gram : 
  - 단어의 순서를 무시하는 bag of words의 단점을 보완
  - 다음 단어 예측, 오타 확인
- Bag of Words VS n-gram
  - 예문 : machine learning is fun and is not boring
  - Bag of Words 에서는 "not"의 위치를 알 수 없기 때문에 문장이 크게 달라짐
  - bag of bigram 에서는 "..., 'and is', 'is not', 'not boring', ..." 단어의 순서를 표현 가능

### 3. TF-IDF(Term Frequency-Inverse Document Frequency, 단어 빈도-역 문서 빈도)
- 문서 유사도 측정에 사용
- 단어 빈도만으로 예측학기 어려운 부분을 보완(ex 을/를 과 같은 조사는 대부분 높은 빈도로 발생하지만, 문서의 주제 추측하기는 어려움.)
- TF : 특정 문서에 단어가 등장한 빈도수
  - ![캡처](https://user-images.githubusercontent.com/43491168/149616329-57c95740-02c1-494b-aa09-065a7f197534.PNG)
  - 단점 : "a"와 같은 불용어의 경우 빈도는 높지만 연관성을 표현할 수 없다.
- IDF : 단어가 등장한 문서의 수에 역수(공식 : log(n/(1+f(n))), n : 단어 비도, f(n) : 단어가 등장한 문서 수)
  - ![캡처](https://user-images.githubusercontent.com/43491168/149616661-d8eab4c4-5faa-4d12-a9ea-d792d8d900e4.PNG)
- TF-IDF : ![캡처](https://user-images.githubusercontent.com/43491168/149616714-bd669061-d920-460a-8512-37eb8b487e1e.PNG)
  - 문장 a, b 각각 car, friend라는 단어가 중요함을 확인가능
  - TF-IDF Score기준 두 문장은 관계없음.

### 4. 유사도 측정 방법
- Euclidean Distance Similarity
  - ![캡처](https://user-images.githubusercontent.com/43491168/149616841-7246eab2-a03e-4d15-b78d-bdf775bc3c78.PNG)
- Cosine Similarity





