### 주성분 분석(PCA)
1. [주성분 분석 개요](#1장-주성분-분석-개요)   
2. [주성분 분석 수리적 배경](#2장-주성분 분석 수리적 배경)   


### 1장 주성분 분석 개요
- 변수의 수가 많아 시각적으로 표현하기 어렵고, 계산 복잡도 증가 -> 차원 축소

- 변수선택/추출을 통한 차원 축소
  - 변수선택 : 목적에 맞는 소수의 변수 선택
    - 장점 : 선택한 변수 해석 용이
    - 단점 : 변수간 상관관계 고려 어려움
  - 변수추출(extraction) : 변수 변환을 통해 새로운 변수 추출 
    - 장점 : 변수간 상관관계 고려, 일반적으로 변수를 많이 줄일 수 있음
    - 단점 : 추출된 변수의 해석 어려움
  - Example
    - Supervised feature selection : Information gain, Stepwise regression, LASSO, Genetic algorithm ...
    - Supervised feature extraction : Partial least squares(PLS)
    - Unsupervised feature selection : PCA loading
    - Unsupervised feature extraction : Principal component analysis(PCA), Wavelets transforms, Autoencoder

- Principal component analysis(PCA) 개요
  - 고차원 데이터를 효과적으로 분석하기 위한 대표적 분석 기법
  - p개의 변수를 상관관계가 없는 k개의 변수로 요약, 이때 요약된 변수는 기존 변수의 선형조합으로 생성
  - 원 데이터의 분산을 최대한 보존하는 새로운 축을 찾고, 그 축에 데이터를 사영(Projection)시키는 기법
  - Example(원 데이터의 정보(분산?)을 잘 보존) : 
    - ![image](https://user-images.githubusercontent.com/43491168/113579472-5100d280-965f-11eb-8627-cfecfde5237e.png)

  - Z is a linear combination of the original p variables in X
    - ![image](https://user-images.githubusercontent.com/43491168/113579755-b228a600-965f-11eb-8cfd-ceadfd7a8d0e.png)

  - 2차원 데이터를 각 축에 사영시킬 경우 좌측 기저가 우측 기저에 비해 손실되는 정보의 야(분산이 더 크다)이 적으므로 더 선호되는 기저이다.
    - ![image](https://user-images.githubusercontent.com/43491168/113580186-4abf2600-9660-11eb-856c-c0271d515b23.png)

### 2장 주성분 분석 수리적 배경
- 수리적 배경
  - ![image](https://user-images.githubusercontent.com/43491168/113580513-d46ef380-9660-11eb-8c46-2144471b21b3.png)\
    - X_bar : Mean vector, Cn : Covariance Matrix, R : correlation Matrix

  - Covariance
  
  - 사영(Projection)
    - ![image](https://user-images.githubusercontent.com/43491168/113580815-3596c700-9661-11eb-8839-b5b592f3558b.png)
  
  - 고유값 및 고유벡터
    - ![image](https://user-images.githubusercontent.com/43491168/113581050-90c8b980-9661-11eb-9e7c-1bc92d3bb235.png)

### 3장 PCA 알고리즘


### 4장 PCA 예제

- 몇 개의 주성분을 사용해야 할까?

### 5장 PCA 정리
- 요약
  - ![image](https://user-images.githubusercontent.com/43491168/113581998-d0dc6c00-9662-11eb-9372-5464645675b5.png)

- 한계점
  - 주성분 분석 특징
  - 한계점 1
  - 한계점 2

- 실제 예제
  - Image 분류
  - IRIS Data...?

- PCA : Loading plot
