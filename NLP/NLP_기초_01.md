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
  - 직선 거리 측정
  - ![캡처](https://user-images.githubusercontent.com/43491168/149616841-7246eab2-a03e-4d15-b78d-bdf775bc3c78.PNG)
- Cosine Similarity
  - 벡터 간;(////s://user-images.githubusercontent.com/43491168/149616885-cbcae3b8-4737-48c2-a24f-b5b27c6d4bf6.PNG)

### 5. TF-IDF 문서 유사도 측정
- Case 1 : Bag of Words를 이용한 코사인 유사동 측정
- Case 2 : TF-IDF를 이용한 코사인 유사도 측정
- 장/단점
  - 예문
    - d1 : the best Italian restaurant enjoy the best pasta
    - d2 : American restaurant enjoy the best hamburger
    - d3 : Korean restraurant enjoy the best bibimbap
    - d4 : the best the best American restraurant
  - Bag of words
    - bat of words 벡터화
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647324-d98e040f-76ad-4ee4-b0a2-54ed46c71402.PNG)
    - 코사인 유사도 결과
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647358-68f8480a-c338-4ab2-afb9-ad7fee2bef38.PNG)
    - "the best"로 인해 d1의 유사도가 가장 높으나, d1 보다는 d2가 실제 더 유사한 문장으로 판단됨(bag of words의 단점)
  - TF-IDF
    - TF-IDF 벡터화
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647393-50a4275d-ca2d-4125-a838-5c91306bd3b3.PNG)
    - 코사인 유사도 계산
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647403-213d4fb0-ac42-4bf3-9b5a-e4fa297aa95e.PNG)
  - 장점 : 
    - 구현이 쉽다
    - 중요한 단어에 점수는 유지
    - 빈도는 높지만, 여러 문서에 존제할 경우 점수를 낮춰준다.
  - 단점 :
    - 단어 간의 관계는 표현하지 못한다
    - 따라서, 문서의 토픽을 알기 어려움
    - 따라서, 같은 뜻의 다른 단어, 유사한 의미를 가지는 단어에 약하다.
    - 다음 단점을 극복하기 위해 LSA(Latent Sementic Analysis), Word Embeddings(Word2Vec, Glove), ConceptNet

### 잠재의미분석(LSA - Latent Semantic Analysis)
- 단어 간의 관계를 표현하지 못하는 TF-IDF를 보안한 토픽 기반의 유사도 계산 방법
- 예시 : 미국 음시과 일본 음식(TF-IDF 에서는 음식간은 관계를 알 수 없음)
  - 미국 음식 : ['pizza', 'pizza hamburger cookie', 'hamburger'], 일본 음식 : ['raman', 'sushi', 'ramen sushi']
    - 단어는 행, 문장은 열로 표현한 word-document matrix
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647773-3d19a30c-0a0f-4579-b4e7-c286c1f4b272.PNG)
    - word-document matrix -> SVD matrix decomposition
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647845-a40f9989-5b83-4332-919d-2b204bb3fc0a.PNG)
    - 차원 축소(미국, 일본 음식 = 2개 차원, 문장(d1~6)에 대한 특이값 분해(nxn))
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647881-a20ad0f8-4a6d-4950-bc64-d35707b00fa0.PNG)
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647889-867e8b25-b9ce-4234-80c8-e670ec90a926.PNG)
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647906-b446688f-b995-4a7e-8f9e-f6638d6d7f49.PNG)
    - 결과
      - d1~3 유사(미국 음식), d4~6 유사(일본 음식)
      - d2가 d1, 3보다 멀지만(빈도 수 때문) 코사인 유사도에서 거리는 상관 없음.(d6 동일)
      - ![캡처](https://user-images.githubusercontent.com/43491168/149647925-71cad640-4ccc-4ee1-9eb5-9707e1c6bd01.PNG)






