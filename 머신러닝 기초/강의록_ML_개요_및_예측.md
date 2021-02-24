1. 머신러닝 및 인공지능 개요
    * 핵심 용어
        - Algorithm : 문제를 해결하기 위한 방법들의 체계적인 모임
        - 단별량/다변량 데이터
        - 반응(종속)변수 = 예측(독립)변수 : Y = X
    
    * 데이터
        - Training / Testing Data
        - Training / Validation / Testing Data

   : 머신러닝 =>  F(x)에서 F(x)함수를 찾아가는 과정

   : 함수의 형태 : 선형/비선형, Tree 구조, 시경망 등...

   : 딩러닝 : 기존의 알고리즘에서 Data 양의 증가에 대한 성능의 한개가 있었음, 이를 딥러닝에서 한개를 넘어서게 됨

2. 수치, 범주예측
    : Regression / Classification : 반응변수의 종류에 따른 차이
3. 머신러닝 모델 학습 프로세스
    : X, Y 사이의 관계를 찾는 행위(Y = F(x1, x2, ......))
    
    * 파라미터 추정
        - Y = w1*X1 + w2*X2 + 오차(w = 파라미터)
        - 오차 = Y - F(x) : Loss function(손실함수)
        - Sigma(Yi - (w1X1i + w2X2i)^2 : Cost Function(비용함수)
        - Cost function을 최소로 하는 파라미터 탐색
    
    : 모델 결정 -> 파라미터 추정(Cost function을 최소화 하는 방향) 
