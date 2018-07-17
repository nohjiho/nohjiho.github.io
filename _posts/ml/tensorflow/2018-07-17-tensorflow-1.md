---
layout: post
title: "텐서플로우 알고리즘 종류"
comment: true
---

#텐서플로우 알고리즘 종류

## 지도학습(Supervised Learning)

**1. 의사 결정 트리(Decision Trees)** : 의사 결정 트리는 의사 결정 지원 도구로, 우연한 이벤트 결과, 리소스 비용 및 유틸리티를 포함하여 트리와 같은 그래프 또는 의사 결정 모델 및 가능한 결과를 사용합니다. 비즈니스 의사 결정의 관점에서, 의사 결정 트리는 대부분의 시간에 올바른 결정을 내릴 확률을 평가하기 위해 질문해야 하는 예/아니오 질문의 최소 수입니다. 방법으로 논리적인 결론에 도달하기 위해 구조화되고 체계적인 방식으로 문제에 접근 할 수 있습니다.

**2. 나이브베이즈 분류(Naive Bayes Classification)** : 나이브베이즈 분류자(Naive Bayes classifier)는 특징들 사이에 강력한(순진한) 독립 가정을 가진 Bayes의 정리를 적용한 간단한 확률 분류자의 패밀리입니다. P(A|B)는 사후확률(posterior probability ), P(B|A)는 우도(likelihood), P(B)는 사전예측확률입니다. 실제 사례의 일부는 다음과 같습니다.
- 전자 메일을 스팸 또는 스팸이 아닌 것으로 표시
-  기술, 정치 또는 스포츠에 관한 뉴스 기사 분류
-  긍정적인 감정을 나타내는 텍스트나 부정적인 감정을 확인
-  얼굴 인식 소프트웨어

**3. 보통 최소 자승 회귀(Ordinary Least Squares Regression, OLS회귀)** : 통계를 알고 있다면 아마도 이전에 선형회귀(linear regression)를 들어 본 적이 있을 것입니다. 최소 자승(Least squares)은 선형회귀를 수행하는 방법입니다. 선형회귀는 점 집합을 통해 직선을 피팅하는 작업으로 생각할 수 있습니다. 이 작업을 수행 할 수 있는 여러 가지 전략이 있습니다. "보통 최소 자승" 전략은 다음과 같이 진행됩니다. - 선을 그릴 수 있고 각 데이터 점에 대해 점과 선 사이의 수직 거리를 측정 한 다음 이를 더할 수 있습니다; 딱 맞는 선은 이 거리의 합이 가능한 만큼 작을 것입니다. 선은 데이터를 맞추는데 사용하는 모델의 종류를 나타내며, 최소 자승은 최소화하는 오류 메트릭의 종류를 나타냅니다.

**4. 로지스틱 회귀(Logistic Regression)** : 로지스틱 회귀는 많은 설명변수(explanatory variable, 회귀분석에서는 독립변수)가 있거나 이항결과(binomial outcome)를 모델링하는 강력한 통계 방법입니다. 누적 로지스틱 분포(cumulative logistic distribution)라는 로지스틱 함수를 사용하여 확률을 추정하여 범주형 종속 변수(dependent variable)와 하나 이상의 독립 변수(independent variable) 간의 관계를 측정합니다.일반적으로 회귀분석은 다음과 같은 실제 응용 프로그램에서 사용할 수 있습니다.
* 신용 점수
* 마케팅 캠페인의 성공률 측정
* 특정 제품의 매출 예측율
* 특정 날에 지진이 발생할 확율

**5. 서포트 벡터 머신(Support Vector Machines, SVM)** : SVM은 바이너리 분류 알고리즘(binary classification algorithm)입니다. N차원 장소에서 2가지 유형의 점 집합이 주어지면 SVM은 (N-1) 차원의 초평면(hyperplane)을 생성하여, 이 점들을 두 그룹으로 분리합니다. 종이에 선형적으로 분리 가능한 2가지 유형의 포인트가 있다고 가정하면 SVM은 이 점들을 2가지 유형으로 분리하고 모든 점들로부터 가능한 멀리 위치하는 직선을 발견 할 것 입니다. 규모면에서 SVM을 사용하여 해결된 가장 큰 문제는 디스플레이 광고, 사람의 이미지 분해 인식, 이미지 기반 성별 탐지, 대규모 이미지 분류 등입니다.

**6. 앙상블 방법(Ensemble Methods)** : 앙상블 방법은 일련의 분류 기준을 구성한 알고리즘을 학습 한 후 예측에 대한 가중 투표(weighted vote)를 통해 새로운 데이터 포인트를 분류합니다. 원래의 앙상블 방법은 베이지안 평균 (Bayesian averaging)이지만 최근의 알고리즘에는 오류 수정 출력 코딩(error-correcting output coding), 배깅(bagging) 및 부스팅(boosting)이 포함됩니다. 그렇다면 앙상블 방법은 어떻게 작동하며 왜 개별 모델보다 우수할까요?
* 편의(bias, 실제값에 대한 추정값의 오차)를 평균화 : 당신이 민주주의를 중요시하는 투표와 공화당이 기울인 투표를 함께 평균한다면 어느 쪽이든 기대지 않는 평균의 것을 얻을 것입니다.
* 분산(variance)을 감소 : 일련의 모델에 대한 총체적 의견은 모델 중 하나의 단일 의견보다 덜 시끄럽습니다. 금융 분야에서이를 다양 화 (diversification)라고합니다. 많은 주식을 혼합 한 포트폴리오는 주식 중 하나만을 사용하는 것보다 훨씬 가변적입니다. 이것이 모델이 더 적은 데이터 포인트가 아닌 더 많은 데이터 포인트로 개선되는 이유입니다.
* 오버피팅(Overfit) 감소 : 오버핏이 없는 개별 모델이 있고 각 모델의 예측을 간단한 방법 (평균, 가중 평균, 로지스틱 회귀)으로 결합하는 경우에는 오버피팅이 발생할 여지가 없습니다.

## 비지도 학습(Unsupervised Learning)

**1. 클러스터링 알고리즘(Clustering Algorithms)** : 비지도 학습 알고리즘 중 가장 많이 사용하는 알고리즘이라고 한다. 클러스터링은 동일한 그룹(클러스터)의 개체가 다른 그룹의 개체보다 서로 비슷하도록 개체 집합을 그룹화하는 작업입니다 . 모든 클러스터링 알고리즘은 여러 가지가 있으며 이중 몇 개를 소개합니다.
* 중심 기반 알고리즘 (Centroid-based algorithms)
* 연결 기반 알고리즘 Connectivity-based algorithms)
* 밀도 기반 알고리즘 (Density-based algorithms)
* 확률적 (Probabilistic)
* 차원축소 (Dimensionality Reduction)
* 신경망 / 딥러닝 (Neural networks / Deep Learning)

**2. 주성분 분석(Principal Component Analysis, PCA)** : PCA는 직교 변환(orthogonal transformation)을 사용하여 상관 관계가 있는 변수의 관측치 집합을 주성분(principal components) 이라는 선형적으로 상관없는 변수 집합으로 변환하는 통계적 절차입니다. 
PCA는압축, 쉬운 학습, 시각화를 위한 데이터 단순화에 일부 응용됩니다. PCA로 진행할지 여부를 선택하기 위해서 도메인 지식이 매우 중요합니다. 데이터에 오류가 많은 경우 (PCA의 모든 구성 요소에는 상당한 편차가 있음)에는 적합하지 않습니다.

**3. 특이값 분해 (Singular Value Decomposition, SVD)** : 선형 대수학(linear algebra)에서 SVD는 실제 복잡한 행렬의 인수분해(factorization)입니다. 주어진 m * n 행렬 M에 대해 M = UΣV와 같은 분해(decomposition)가 존재합니다. 
여기서 U와 V는 단위행렬(unitary matrices)이고 Σ는 대각행렬(diagonal matrix) 입니다. PCA는 실제로 SVD의 간단한 응용입니다. 
컴퓨터 비전에서 최초의 얼굴 인식 알고리즘은 얼굴을 "고유체(Eigenface)"의 선형 조합(linear combination)으로 표현하고, 차원축소(dimensionality reduction)를 수행 한 다음 간단한 방법으로 얼굴을 신원과 일치시키기 위해 PCA 및 SVD를 사용했었습니다. 
현대적인 방법은 훨씬 정교하지만 많은 사람들이 여전히 유사한 기술에 의존합니다.

**4. 독립 성분 분석 (Independent Component Analysis, ICA)** : ICA는 무작위 변수(random variables), 측정값(measurements) 또는 신호(signals) 세트의 기초가 되는 숨겨진 요인을 밝혀 내기 위한 통계 기법입니다. 
ICA는 일반적으로 샘플의 대규모 데이터베이스로 제공되는 관측된 다변량 데이터(observed multivariate data)에 대한 생성 모델을 정의합니다. 모델에서 데이터 변수는 미지의 잠재 변수의 선형 혼합으로 가정되며 혼합 시스템도 알 수 없습니다. 잠재 변수는 가우스(Gaussian)가 아니며 상호 독립적인 것으로 가정되며 관측된 데이터의 독립적인 구성 요소라고 합니다.
ICA는 PCA와 관련이 있지만, 이 고전적인 방법이 완전히 실패할 때 소스의 기본 요소를 찾을 수있는 훨씬 더 강력한 기술입니다. ICA는 디지털 이미지, 문서 데이터베이스, 경제 지표 및 심리 측정에 응용됩니다.

## 출처

- [텐서플로우 블로그](https://tensorflow.blog/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D/2-5-%EC%9A%94%EC%95%BD-%EB%B0%8F-%EC%A0%95%EB%A6%AC/)

