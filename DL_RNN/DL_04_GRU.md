- https://www.youtube.com/watch?v=KLtMNGjICrk
- https://yjjo.tistory.com/18
- https://davinci-ai.tistory.com/30 (별로인듯...)

### 1. GRU(Gated Recurrent Units)

- LSTM 비교
- ![캡처](https://user-images.githubusercontent.com/43491168/144735452-8dcc427f-3ed7-4c32-9afa-423ba06f47fd.PNG)
  - LSTM의 cell state 업음
  - 활성 함수 5개 -> 3개

### 2. GRU 구조
- Reset Gate
  - ![캡처](https://user-images.githubusercontent.com/43491168/144735504-f7bb897d-632d-45b8-836f-c93332b48980.PNG)
  - 과거의 정보를 얼마나 잊을지
  - 직전 시점의 은닉층의 값(H)과 현시점의 정보(X)에 가중치를 곱하여 계산

- Update Gate
  - ![캡처](https://user-images.githubusercontent.com/43491168/144735641-8dcd782f-8ee5-4589-83ce-672a89962b5b.PNG)
  - 과거(H)와 현재(X)의 정보중 어떤 정보를 더 많이 업데이트 할지 결정
  - LSTM의 input gate, forget gate를 합쳐놓은 느낌
    - U(t) : 현시점 정보의 양
    - 1-U(t) : 진전 시점의 정보\

- Candidate
  - ![캡처](https://user-images.githubusercontent.com/43491168/144736369-e715cb81-cd9f-4323-b274-b0059a98beb3.PNG)
  - 다음 시점으로 전달해줄 데이터 H를 만들기 위한 현시점 데이터 선정 단계
  - 현시점 데이터(X), 직전 시점(H), 직전 시점에서 일부 리셋된 데이터(R)로 생성
  - * : Pointwise operation : 점단위 연산(행렬의 각 point별 연산?)

- Output
  - ![캡처](https://user-images.githubusercontent.com/43491168/144736502-f5919d28-9f8b-4cfe-b440-7c24ff000281.PNG)
  - (1) (1-U)*H : 직전 값에서 얼만 잊을지
  - (2) U*H :  현 시점에서 얼마나 가져갈지
  - (1) + (2) : GRU 층의 출력 값

### 3. Summary
- ![image](https://user-images.githubusercontent.com/43491168/144736596-c8448237-4d73-4b89-a82a-8305f7775655.png)
