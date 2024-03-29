- Ex : Food, Weather(https://www.youtube.com/watch?v=UNmqTiOnRfg)
- RNN : 순환 신경망(Recurrent Neural Network)은 은닉 계층 안에 하나 이상의 순환 계층을 갖는 신경망을 의미

### 1. Neural Network
- NN 기본 형태
  - ![캡처](https://user-images.githubusercontent.com/43491168/143809355-c5c50355-ca91-45c7-88a3-47ae5ed4f45a.PNG)

### 2. Simple (Receurrent) Neural Network
  - [1, 0, 0] / [0, 1, 0] / [0, 0, 1]
  - ![캡처](https://user-images.githubusercontent.com/43491168/143809639-c800a8ed-8942-421c-9944-20c8b40dab24.PNG)

### 3. Receurrent Neural Network : 1. + 2.
- 예시 : Cooking Schedule
  -  ![캡처](https://user-images.githubusercontent.com/43491168/143809822-c623b63f-addb-4bd6-9561-9ed69914ac67.PNG)
- RNN(NN 구조)
  - 전체
  - ![캡처](https://user-images.githubusercontent.com/43491168/143816996-9f60acfc-b26e-4c59-bfbb-678d7d8c466d.PNG)
  - (1) Food : Same(동일 값), Next Day(다음 음식)
  - ![캡처_food](https://user-images.githubusercontent.com/43491168/143817062-a7d2f195-3c72-45d2-b773-8daad565f618.PNG)
  - (2) Weather : Same, Next dayu = 비활성, 활성?
  - ![캡처_Weater](https://user-images.githubusercontent.com/43491168/143817352-d40430af-58e8-4ad4-88f0-e30271838a65.PNG)
  - (3) Add : Food + Weather(행렬 합계)
  - ![캡처_Add](https://user-images.githubusercontent.com/43491168/143817440-587d8207-6d83-4ac2-b411-c6302ddadb1d.PNG)
  - (4) Merge : 2 -> 1, else -> 0
  - ![캡처_Merge](https://user-images.githubusercontent.com/43491168/143817512-fe7f8066-b9bd-402e-9033-299b2abdc9a6.PNG)

- RNN 구조
  - 결과값(y, Food)이 다음 값에 영향을 주는 형태 = 순환 신경망
  - ![캡처_Fin](https://user-images.githubusercontent.com/43491168/143817721-875ae673-f032-4b37-9fb4-dfcdd2c85a5e.PNG)

### 4. 기타
- 활용 : 
  - Stock Prediction
  - Sequence Generation
  - Text Generation
  - Voice Recognition 
