- https://www.youtube.com/watch?v=dKYFfUtij_U&list=PLVNY1HnUlO26qqZznHVWAqjS1fWw0zqnT

### 1. Word2Vec
- Text를 숫자로 Encoding하는 방법(ex : on hot encoding(단어간 유사도를 알 수 없는 단점이 있음.))
- Embeding 종류중 하나
  - Embeding : 

- 예제
  - skipgram 방법으로 변환
    - Sample Data : "king brave man", "queen beautiful woman"
    - ![캡처](https://user-images.githubusercontent.com/43491168/149969138-4f19c405-4673-4041-b339-134ef051b07b.PNG)
  - Word2Vec Train
    - 변환된 데이터의 word를 Input Data, neighbor를 Target으로 두고 신경망 학습
    - 학습된 신경망의 hidden layer의 w1, w2값이 Word2Vec 값이 됨
    - ![캡처](https://user-images.githubusercontent.com/43491168/149969312-45b3c555-4f59-4960-8b2e-1a60e3eb820d.PNG)
    - ![캡처](https://user-images.githubusercontent.com/43491168/149969862-ddb9bb55-d2e5-47ff-86da-e53ccfb889d9.PNG)
  - 결과
    - ![캡처](https://user-images.githubusercontent.com/43491168/149970016-b5feeeec-3aea-4879-846a-87a6ebace5dd.PNG)
  - Python 예제 코드
    - "Study_ZTC_01/NLP/word2vec_tensorflow.ipynb" 참고

### 2. WMD
- Word mover's distance, 문서 유사도 계산
- Word2Vec을 사용하여 Euclidean distance 계산
- Word Embedding 방법?
- 한문장에서 단어의 이웃들에 의해 계산됨

### 3. 딥러닝 기계번역 : 시퀀스 투 시퀀스 + 어텐션 모델
- 시퀀스 투 시퀀스
- 어텐션 모델
- Teacher forcing
