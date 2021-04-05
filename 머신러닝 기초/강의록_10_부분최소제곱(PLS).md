### 부분최소제곱
1. [부분최소제곱법(Partial Least Squares, PLS) 개요](#1장-부분최소제곱법(Partial-Least-Squares,-PLS)-개요)   
2. [PLS 변수 추출 방법](#2장-PLS-변수-추출-방법)   
3. [PLS 예제](#3장-PLS-예제)   
4. [PLS 확장 모델](#4장-PLS-확장-모델)   

### 1장 부분최소제곱법(Partial Least Squares, PLS) 개요
- PCA, PLS 차이점
  - ![image](https://user-images.githubusercontent.com/43491168/113600917-a5b24680-967b-11eb-87eb-241d79c0788b.png)

- 개요
  - PLS는 Y와의 공분산이 높은 k 개의 선형조합 변수를 추축하는 방식
  - PLS 용어는 선형조합으로 추출된 변수가 설명하지 못하는 부분에(데이터 일부분) 지속적으로 최소제곱법을 사용하는 것에서 유래
  - 주요 목적
    - 회귀 및 분류 모델 구축
    - 데이터 차원 축소
  - 추출된 변수가 PCA에서는 반영하지 못했던 Y와의 상관관계를 반영하는 특징
  - 적은 수의 추출된 변수로 효율적인 모델 구축 가능

- PLS
  - ![image](https://user-images.githubusercontent.com/43491168/113601364-2f621400-967c-11eb-91d4-c046cf07dbc0.png)

### 2장 PLS 변수 추출 방법
- 가중치 w
  - ![image](https://user-images.githubusercontent.com/43491168/113601609-87007f80-967c-11eb-8238-fc3c37b2b70c.png)
  - ![image](https://user-images.githubusercontent.com/43491168/113601783-bdd69580-967c-11eb-9b8a-0fbc4e87da9a.png)

- PLS NIPALS Algorithm
  - ![image](https://user-images.githubusercontent.com/43491168/113602019-0db55c80-967d-11eb-83a1-c5bb78092479.png)
  - ![image](https://user-images.githubusercontent.com/43491168/113602351-76043e00-967d-11eb-97ce-2cba413e3ddc.png)
  - ![image](https://user-images.githubusercontent.com/43491168/113602428-8e745880-967d-11eb-8d53-3188985d5618.png)
  - ![image](https://user-images.githubusercontent.com/43491168/113602663-d72c1180-967d-11eb-8e7a-d8416c898726.png)
  - ![image](https://user-images.githubusercontent.com/43491168/113602759-fa56c100-967d-11eb-80c3-61f6927174ce.png)

### 3장 PLS 예제
- PLS  예제

- 추출 변수의 수 결정

### 4장 PLS 확장 모델
- 출력변수 Y가 여러 개일 때의 PLS

- 출력변수 Y가 범주형일 때의 PLS(PLS-DA : Discrimination Analysis)



