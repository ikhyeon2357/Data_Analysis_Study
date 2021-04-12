### Boosting
1. [SVM 모델 개요](#1장-SVM-모델-개요)   


### 1장 Boosting
- Boosting 개요
  - 여러 개의 Learning모델을 순차적으로 구축하여 최종적으로 합침(앙상블)
  - Learning 모델은 매우 단순한 모델 사용
  - 순차적 -> 모델 구축 순서를 고려
  - 각 단계에서 새로운 base learner를 학습하여 이전 단계의 base learner의 단점 보완
  - 각 단계를 거치며 모델이 점차 강해짐 -> boosting

- Boosting 알고리즘 종류
  - Adaboost, GBM, XGboost, LGBM, Catboost

### 2장 Adaptive Boosting(Adaboost)
- AdaBoost
  - 각 단계에서 새로운 base learner를 학습하여 이전 단계의 base learner의 단점 보완
  - Training error가 큰 관측치의 선택 확률(가중치)을 높이고, Training error가 작은 관측치 선택 확률 낮춤
  - 앞 단계에서 조정된 확률을 기반으로 다음 단계 Training dataset을 구성
  - 최종 결과물은 각 모델의 성능지표를 가중치로 하여 결합(앙상블)

- Step
  - ![image](https://user-images.githubusercontent.com/43491168/114414910-3348e580-9bea-11eb-9353-9b5bca45c7e3.png)
  - Example
    - Step 1 : 
      - ![image](https://user-images.githubusercontent.com/43491168/114415288-8458d980-9bea-11eb-91ab-b225eedde4b2.png)
    - Step 2 :
      - ![image](https://user-images.githubusercontent.com/43491168/114415676-ddc10880-9bea-11eb-86ea-ff4b77b2a002.png)
    - Step 3 : 
      - ![image](https://user-images.githubusercontent.com/43491168/114415772-f6312300-9bea-11eb-8b7e-613902cac252.png)
    - Step 4(end) : 
      - ![image](https://user-images.githubusercontent.com/43491168/114415911-152fb500-9beb-11eb-9244-a1cec084d51b.png)

- Bagging vs Boosting
  - ![image](https://user-images.githubusercontent.com/43491168/114416218-6b045d00-9beb-11eb-96d7-1f18187a680a.png)


### 3장 Gradient Boosting Machines(GBM)
- GBM
  - Gradient boosting = Boosting with gradient decent
  - 첫번째 단계의 모델 tree 1을 통해 Y를 예측하고, Residual을 다시 두번째 단계 모델 tree2를 통해 예측하고, 여기서 발생한 모델 tree3로 예측
  - 점차 residual 작아 짐
  - Gradient boosting model = tree 1 + 2 + 3
  - ![image](https://user-images.githubusercontent.com/43491168/114416858-0f869f00-9bec-11eb-804c-180dcedc8799.png)

- Gradient
  - ![image](https://user-images.githubusercontent.com/43491168/114417139-4ceb2c80-9bec-11eb-9f04-387d8d74c43e.png)
  - ![image](https://user-images.githubusercontent.com/43491168/114417320-74da9000-9bec-11eb-9786-a9a99b0d0bb8.png)
  - ![image](https://user-images.githubusercontent.com/43491168/114417500-9c315d00-9bec-11eb-8faa-6a4bc25f2063.png)



