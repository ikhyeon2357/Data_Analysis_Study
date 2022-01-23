- https://www.youtube.com/watch?v=mxGCEWOxfe8&list=PLVNY1HnUlO26qqZznHVWAqjS1fWw0zqnT&index=13

### 1. Tranformer(Attention is all we need)
- 기존 Encoder, Decoder를 발전시킨 딥러닝 모델(속도, 성능 개선)
  - RNN을 사용하지 않음, Paralleization
- RNN based encoder decoder with attention
  - 기존 "RNN based encoder decoder"에 attention 방법론을 통해 개선 하였으나 여전히 RNN cell을 순차적으로 계산하기 때문에 느리다는 문제가 있다.
  - 따라서 attention만으로 입력 데이터에서 중요한 정보들을 찾아내서 단어들을 인코딩 => Attention is all you need
  - 기존 Encoder Decoder에서 RNN을 제거함.
- (1) Positional encoding
- (2) Self Attention 연산
- Why Multi Head Attention
- (3) Encoder
- (4) Decoder
