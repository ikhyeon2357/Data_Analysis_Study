- DRNN(oR Stacke RNN)
- BERT
- Q : LSTM에서 각 cell에서 sigmoid와 tanh 조합 이유


- RNN에서 활성화함수로 tanh를 주로 사용하는 이유
  - 시간축을 depth로 error signal을 전파하는 BPTT(Back-Propagation-Through-Time) 방식으로 학습하는데, 이때 sigmoid보다 tanh의 gradient(기울기)가 커서(stiff) 기울기 소실을 완화하기 위하여 사용
  - 음수값도 중요하기 때문에 ReLU가 아닌 tanh를 쓴다. 
