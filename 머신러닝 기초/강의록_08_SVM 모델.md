### SVM 모델
1. [SVM 모델 개요](#1장-SVM-모델-개요)   

----------------
Support Vector Machines
svm 모델 개요


----------------

### 1장 SVM 모델 개요
- 개요
  - generalization performance for classification of high-dimensional data sets
  - solving a quadratic programming problem
  - trad-off between  the generalization ability and fitting to the training data.
  - SVM : 
    - trained so that the direct decision function maximizes the generalization ability
    - based on statistical learning theory

### 1장 SVM : Classification
- two class classification : 무한히 많은 hyperplane중 가장 "좋은" hyperlane을 찾는것
- Maximizing margin over the training set = minimizing generalization error = good prediction performance

- Geometric Margin
  - 각 class에서 가장 가까운 관측치 사이의 거리
  - w(기울기)로 표현 가능
  - hyperplane : w^Tx + b = 0
    - ![image](https://user-images.githubusercontent.com/43491168/112714280-0b386180-8f1d-11eb-940e-41b103ead6cb.png)
    - ![image](https://user-images.githubusercontent.com/43491168/112714477-d7117080-8f1d-11eb-8b64-6001cc975d14.png)
    - ![image](https://user-images.githubusercontent.com/43491168/112714525-fc9e7a00-8f1d-11eb-9330-9c11e03ba7ca.png)
    - ![image](https://user-images.githubusercontent.com/43491168/112714588-53a44f00-8f1e-11eb-812f-29c52b4bb9ed.png)
  - Lagrangian Formulation
    - ![image](https://user-images.githubusercontent.com/43491168/112714623-7d5d7600-8f1e-11eb-81d6-8235c2a02f53.png)
    - Lagrangian Primal
      - ![image](https://user-images.githubusercontent.com/43491168/112714673-b4338c00-8f1e-11eb-9df9-8897457aeee0.png)
      - ![image](https://user-images.githubusercontent.com/43491168/112714739-23a97b80-8f1f-11eb-925f-2f1a0d1da254.png)
      - ![image](https://user-images.githubusercontent.com/43491168/112714746-358b1e80-8f1f-11eb-9dbb-55cb346c31f8.png)
      - ![image](https://user-images.githubusercontent.com/43491168/112714752-4045b380-8f1f-11eb-9c2b-16843a9d293d.png)
    - Lagrangian Dual
      - ![image](https://user-images.githubusercontent.com/43491168/112714808-9286d480-8f1f-11eb-9480-f9bd76aa45f6.png)










 
