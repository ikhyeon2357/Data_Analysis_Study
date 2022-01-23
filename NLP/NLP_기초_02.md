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

### 2. WMD(Word mover's distance)
- 문서 유사도 계산 방법
- Word2Vec을 사용하여 단어 간의 Euclidean distance 계산
- Ex :
  - "King brave man", "queen beatiful woman"
  - (1) Word2Vec 계산 후 "prince fearless guy"와 가장 가까운 단어 선택
  - ![캡처](https://user-images.githubusercontent.com/43491168/150666582-97b14b92-d4d9-4429-bb89-46a0e5501887.PNG)

- 문서 유사도 계산 예제
  - (1) 불용어 제거 후 Nomalized Bag of Words(0값은 실제 사용 안함)
    - D0 : The President greats the press in Chicago --> President greats press Chicago : [0.25, 0.25, 0.25, 0.25, 0, 0...]
    - D1 : Obama speaks to the media in Illinois     --> Obama speaks media Illinois : [...0, 0.25, 0.25, 0.25, 0.25, 0 ...]
    - D2 : The band gave a concert in Japan          --> band gave concert Japan : [...0, 0.25, 0.25, 0.25, 0.25, 0 ...]
    - D3 : Obama speaks in Illinois                  --> Obama speaks Illinois : [...0, 0.33, 0.33, 0.33, 0 ...]
  - (2) 거리 계산(동일 단어 수)
    - 유클리드 거리 * 단어 함율량(0.25)
    - D0와 거리 합이 D2보다 D1이 더 작음 = 더 유사함.
    - ![캡처](https://user-images.githubusercontent.com/43491168/150667574-53cd06ad-8944-42c9-9a5b-d6202f7f0538.PNG)
  - (2) 거리 계산(단어의 수가 다른 경우)
    - 남은 함유량(0.08 = 0.33 - 0.25)만큼 다음 단어로 분해
    - ![캡처](https://user-images.githubusercontent.com/43491168/150667688-b8740ff2-d999-4837-a395-c3873a9a6cd3.PNG)

- 장/단점
  - 매우 높은 성능(정확도?)을 보이나 속도가 매우 느림
  - 비슷한 성능, 속도 개선 : Relaxed WMD(RWMD)

### 3. 딥러닝 기계번역 : 시퀀스 투 시퀀스 + 어텐션 모델
- 시퀀스 투 시퀀스
- 어텐션 모델
- Teacher forcing
