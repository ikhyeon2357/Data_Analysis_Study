### SVM 모델
1. [SVM 모델 개요](#1장-SVM-모델-개요)   


### 1장 SVM 모델 개요
- 개요
  - generalization performance for classification of high-dimensional data sets
  - solving a quadratic programming problem
  - trad-off between  the generalization ability and fitting to the training data.
  - SVM : 
    - trained so that the direct decision function maximizes the generalization ability
    - based on statistical learning theory

### 2장 Linear SVM for linearly separable cases
  - Hard Margin SVM
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
      - (w, b, alpha)가 Lagrangian dual problem의 최적해가 되기 위한 조건
        - ![image](https://user-images.githubusercontent.com/43491168/112715802-d7156e80-8f25-11eb-86cf-1526f5873372.png)

- Characteristics of the Solutions
  - ![image](https://user-images.githubusercontent.com/43491168/112715873-5014c600-8f26-11eb-86ad-886fdc43f271.png)
  - ![image](https://user-images.githubusercontent.com/43491168/112715935-bef21f00-8f26-11eb-805b-76bb90421b39.png)

- Classifying New Data Point
  - ![image](https://user-images.githubusercontent.com/43491168/112715964-ee089080-8f26-11eb-8a5f-4ed9d3ce9d1f.png)

### 3장 Linear SVM for linearly nonseparable case
  - Soft Margin SVM
  - Linear decision boundary를 이용하여 완벽하게 나누는 것이 불가능한 경우 -> Error 허용
    - ![image](https://user-images.githubusercontent.com/43491168/112716117-bc43f980-8f27-11eb-9ece-13260a2e1f42.png)

- Convex Optimization Formulation
  - ![image](https://user-images.githubusercontent.com/43491168/112716154-0200c200-8f28-11eb-87b1-305e6b3f5e4a.png)
  - ![image](https://user-images.githubusercontent.com/43491168/112716163-0fb64780-8f28-11eb-97d6-7bbea7586fe0.png)

- Lagrangian Formulation
  - ![image](https://user-images.githubusercontent.com/43491168/112716191-3a080500-8f28-11eb-8226-4694420ca7dd.png)
  - Lagrangian Primal
    - ![image](https://user-images.githubusercontent.com/43491168/112716222-67ed4980-8f28-11eb-9a63-d5e997e8e94b.png)
  - Lagrangian Dual
    - ![image](https://user-images.githubusercontent.com/43491168/112716244-82272780-8f28-11eb-9415-d8b3e3e8cbaf.png)
    - ![image](https://user-images.githubusercontent.com/43491168/112716253-98cd7e80-8f28-11eb-8900-a884764cf468.png)
    - Soft & Hard Margin SVM
      - ![image](https://user-images.githubusercontent.com/43491168/112716276-b569b680-8f28-11eb-86af-234797cbe15d.png)
    - ![image](https://user-images.githubusercontent.com/43491168/112716290-d3cfb200-8f28-11eb-848b-7a1afb26b456.png)

- Characteristics of the Solution
  - ![image](https://user-images.githubusercontent.com/43491168/112716342-25783c80-8f29-11eb-82a4-522264a25800.png)

### 4장 Kernel Methods for Nonlinear Classification
  - 비선형 SVM 구축
    - ![image](https://user-images.githubusercontent.com/43491168/112716386-725c1300-8f29-11eb-99c2-4bf9c9611fe5.png)

- Transforming Data
  - 고차원 데이터로 변환
    - ![image](https://user-images.githubusercontent.com/43491168/112716419-b94a0880-8f29-11eb-8cfe-d670954923fa.png)
    - Example : 
      - ![image](https://user-images.githubusercontent.com/43491168/112716429-ccf56f00-8f29-11eb-9d3b-7ea2d97b9273.png)

- Mapping Original Space to Kernel Space
  - ![image](https://user-images.githubusercontent.com/43491168/112716467-f910f000-8f29-11eb-8d8b-99e79d15656f.png)
  - Kernel Mapping
    - ![image](https://user-images.githubusercontent.com/43491168/112716504-278ecb00-8f2a-11eb-9762-84450ef44353.png)
    - Kernel Mapping - Example
      - ![image](https://user-images.githubusercontent.com/43491168/112716587-92400680-8f2a-11eb-9897-ae5bed7fe81b.png)
  
- Kernel Function
  - ![image](https://user-images.githubusercontent.com/43491168/112716625-c3b8d200-8f2a-11eb-8569-99fc3a9cea02.png)

### 5장 Example of Nonlinear SVM Using Kernel Function
- 문제
  - ![image](https://user-images.githubusercontent.com/43491168/112716663-07134080-8f2b-11eb-8d65-4613f8adebca.png)

















 
