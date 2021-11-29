- https://davinci-ai.tistory.com/30
- https://www.youtube.com/watch?v=bX6GLbpw-A4 (Gradient Vanishing, Exploding(소실, 폭주))

# 순환 신경망(RNN)
- 순환 신경망(Recurrent Neural Network)은 은닉 계층 안에 하나 이상의 순환 계층을 갖는 신경망

### 1. RNN 기본 구조
  - 레이어의 출력을 다시 입력으로 받아서 사용하는 것으로서, 이전의 데이터가 함께 결과에 영향을 미침(되먹임 구조?)
  - RNN은 입력과 출력의 길이에 제한이 없다는 특징이 있습니다. 
  - 기본적으로 Fully connected 구조를 가지고 있습니다.
    ' 한 층(layer)의 모든 뉴런이 다음 층(layer)의 모든 뉴런과 연결된 상태
  - ![캡처_rnn_기본 구조](https://user-images.githubusercontent.com/43491168/143860078-709bd79c-1563-46a5-927f-e67b965208bd.PNG)

### 2. RNN Parameter
- units : RNN 신경망에 존재하는 뉴런의 개수
  - ![캡처_rnn_param_units](https://user-images.githubusercontent.com/43491168/143864947-5efc777f-eb97-4e0d-9434-c3125ea6c0d7.PNG)
- return_sequences : RNN 계산 과정에 있는 hidden state를 출력할 것인지에 대한 값을 의미
  - ![캡처_rnn_param_return_sequence](https://user-images.githubusercontent.com/43491168/143865151-daa30968-620f-4650-aad5-2660ded919f1.PNG)
  - False : 마지막 출력값 하나를 출력 / True : 모든 과정의 출력 값을 출력
  - 다층으로 이루어진 RNN 또는 one-to-many, many-to-many 출력을 위해서 사용
- return_state : cell_state를 출력할 것인지를 결정하는 값
  - LSTM 레이어에서 주로 사용
  - 반환된 은닉 상태는 후에 RNN layer 실행을 이어가거나, 다른 RNN을 초기화하는데 사용
- activation : 활성화 홤수(tanh, relu ...)

### 3. RNN 예시
- Simple RNN 구조
  - ![캡처](https://user-images.githubusercontent.com/43491168/143870479-866d9167-a983-4255-9599-acc97964141a.PNG)
- RNN Example : [0.0, 0.1, 0.2, 0.3]이라는 0.1씩 늘어나는 수열 학습
  - ![캡처](https://user-images.githubusercontent.com/43491168/143872615-4d2f2ac2-a6f0-4ad8-9316-8c62e90909f9.PNG)
  - Sample Code
```
model = tf.keras.Sequential([ tf.keras.layers.SimpleRNN(units=10
                                                        , return_sequences=False
                                                        # input_shape : 4 time-step마다 하나의 답이라서 [4,1]을 선언
                                                        , input_shape=[4,1])
                             , tf.keras.layers.Dense(1) ]) 

model.compile(optimizer='adam', loss='mse') 

history = model.fit(X, Y, epochs=100, verbose=0)
```

### 4. RNN 단점
- 장기 의존성(Long-Term Dependency)문제
  - 입력 데이터와 출력 데이터 사이의 길이가 멀어질수록 연관 관계가 줄어듬(데이터의 뒤쪽으로 갈수록, 앞쪽의 입력 데이터를 까먹게 된다.)
  - ![image](https://user-images.githubusercontent.com/43491168/143873316-3ae87490-e87c-42c2-a666-d167576050a3.png)
  - 장기의존성 문제를 해결하기 위해서 RNN의 변형 구조인 LSTM(Long Short Term Memory)가 나오게 되었슴.
- Gradient Vanishing(소실) / Gradient Exploding(폭주)
  - Vanishing : 역전파 과정에서 입력층으로 갈 수록 기울기(Gradient)가 점차적으로 작아지는 현상(입력층에 가까운 층들에서 가중치들이 업데이트가 제대로 되지 않음)
  - Exploding : 기울기가 점차 커지더니 가중치들이 비정상적으로 큰 값이 되면서 결국 발산(기울기 > 1?)

