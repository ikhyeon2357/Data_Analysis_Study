- https://davinci-ai.tistory.com/30
- https://www.youtube.com/watch?v=bX6GLbpw-A4

### 1. LSTM 기본 구조
-RNN에서 c라는 셀 상태(cell state)라는 변수가 추가적으로 공유
- 셀 상태가 함께 다음 레이어로 전달되면서, 기존의 상태를 보존하여 장기의존성 문제를 해결함.
  - ![캡처](https://user-images.githubusercontent.com/43491168/143898356-a9bd3b5d-9ccf-45b4-a093-f93a41d999a0.PNG)

### 2. cell state
- 기본 구조
  - ![캡처_lstm_구조](https://user-images.githubusercontent.com/43491168/143899907-367c02bc-befd-4369-b83e-312ca6d9bd2e.PNG)
  - c(state cell, memory cell) : Forget Gate, Input Gate, Output Gate
  - tanh: 기존의 RNN에서 사용되는 활성화 함수(relu 등 대체 가능)
  - sigmoid: 정보가 0과 1 사이에서 얼마나 통과할지를 결정하는 함수
- Forget Gate
  - 얼마나 잊어버릴지에 대한 가중치를 사용하여 잊어버리기로 정한 것을 실제로 잊는 게이트
  - 이전 state c에 forget gate 출력 값을 곱해서 state를 업데이트
  - ![Forget Cell](https://user-images.githubusercontent.com/43491168/143900416-a1c3181f-016f-46ca-9207-7c79cda288cb.PNG)
- Input Gate
  - sigmoid layer가 새로운 정보 중에 어떤 것을 cell state에 담을 것인지를 결정하는 게이트
  - 그다음으로 tanh layer에서 새로운 데이터의 후보 값을 만들어냄
  - 이것을 cell layer에 합쳐줌.
  - ![Input Cell](https://user-images.githubusercontent.com/43491168/143901107-ad9656c6-5e67-4e84-8261-e5a9bfcda0f5.PNG)
- Output Gate
  - 어떤 값을 출력할지를 결정하는 게이트
  - sigmoid layer : cell state의 어떤 부분을 출력할 지를 정
  - cell state를 tanh 하여 나온 -1과 1 사이의 값을 sigmoid 출력 값과 곱하여 최종 출력 값을 연산
  - ![Output Cell](https://user-images.githubusercontent.com/43491168/143901667-259e7fb4-1abe-46a5-a434-8ff513954900.PNG)

