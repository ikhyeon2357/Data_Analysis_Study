- https://www.youtube.com/watch?v=mxGCEWOxfe8&list=PLVNY1HnUlO26qqZznHVWAqjS1fWw0zqnT&index=13

### 1. Tranformer(Attention is all we need)
- 기존 Encoder, Decoder를 발전시킨 딥러닝 모델(속도, 성능 개선)
  - 장점 : RNN을 사용하지 않음, Paralleization
- RNN based encoder decoder with attention
  - 기존 "RNN based encoder decoder"에 attention 방법론을 통해 개선 하였으나 여전히 RNN cell을 순차적으로 계산하기 때문에 느리다는 문제가 있다.
  - 따라서 attention만으로 입력 데이터에서 중요한 정보들을 찾아내서 단어들을 인코딩 => Attention is all you need
  - 기존 Encoder Decoder에서 RNN을 제거함.

- (1) Positional encoding
  - 각 단어의 위치 정보 추가(초기 임베딩된 단어 벡터와 함께 합산하여 초기 입력을 사용)
  - RNN 방식과 다르게 입력값을 하나의 매트릭스로 주기 때문에 순서가 뒤죽박죽 될 수 있음.
  - ![캡처](https://user-images.githubusercontent.com/43491168/152117322-71275d99-21fa-4217-bff1-6f21f99d1940.PNG)

- (2) Self Attention 연산
  - ![캡처](https://user-images.githubusercontent.com/43491168/152120065-1b28c56a-2e0c-426c-8462-1ad881cb0df3.PNG)
    - (1) Query : 영향을 받는 단어를 나타내는 벡터
    - (2) Key : 영향을 주는 단어를 나타내는 벡터
    - (3) Value : 영향에 대한 가중치 벡터
  - ![캡처](https://user-images.githubusercontent.com/43491168/152120504-d58a87d0-b195-4894-a036-73dc7a0ba0ba.PNG)
    - Score가 높을 수록 단어간 연관성이 높다
    - Softmax : Score를 0~1사이로 변환
    - 독립적인 단어 "I"가 아닌, 문장 속의 단어 "I"가 가진 의미를 나타내는 벡터로 표현
  - Multi Head Attention : 여러개의 Attention Layer를 병렬로 처리함(8개)
    - ![캡처](https://user-images.githubusercontent.com/43491168/152120752-80e790af-53d5-48f7-a56a-77eeadf98cb7.PNG)

- (3) Encoder
- ![캡처](https://user-images.githubusercontent.com/43491168/152121480-58825be5-7999-4ec9-ab53-e7838d6e3eae.PNG)
  - Residual Connection followed by layer normalization
    - 역전파 과정에서 Positional encoding이 손실 될 수 있어 Redidual Connection을 더해줌
    - ![캡처](https://user-images.githubusercontent.com/43491168/152121551-cecc35fe-50c5-428e-830a-25e94242fec5.PNG)
  - Transformer has 6 encoder layers
    - ![캡처](https://user-images.githubusercontent.com/43491168/152121709-c4d72a40-a4df-407a-9a12-73a8d3361f00.PNG)
    
- (4) Decoder
  - Transformer has 6 decoder layers
  - ![캡처](https://user-images.githubusercontent.com/43491168/152122496-ec39090d-0800-4d58-b6cc-b63d82a1ccfe.PNG)
  - ![image](https://user-images.githubusercontent.com/43491168/152122553-0bd0ede4-7213-4061-baf8-de88e1294b97.png)
    - Masked Multi head Attention : 아직 출력되지 않은 미래의 단어에 attention 됨을 방지
    - Multi head Attention : decoder에 현재 상태를 Query로 encoder에 질문 하고, 그 출력값을 key, value로 decoder에 적합한 다음 단어로 출력
    - Feed Forward : 최종값을 벡터로 출력
  - 벡터를 실제 단어로 출력
    - ![캡처](https://user-images.githubusercontent.com/43491168/152125047-7f2418cf-4f13-40b3-bd96-fb462e74d239.PNG)
      - Linear Layer : Softmax에 들어갈 logit을 생성
      - Softmax Layer : 가장 높은 값(확률)을 가지는 단어가 출력 단어
        - Label Smoothing : "0, 1"이 아닌 "0에 가까운 값, 1에 가까운 값"으로 변화(학습 데이터에 치중 됨을 방지, '감사합니다' == '고맙습니다')
  
