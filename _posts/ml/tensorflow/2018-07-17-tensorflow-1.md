---
layout: post
title: "머신러닝 시스템의 종류와 텐서플로우 알고리즘 종류"
comment: true
---

#머신러닝 시스템의 종류와 텐서플로우 알고리즘 종류
머신러닝 시스템의 종류는 굉장히 많으므로 다음 기준으로 넓은 범주에서 분류하면 이해해 도움이 된다.
* 사람의 감독하에 훈련하는 것인지 그렇지 않은 것인지(지도,비지도,준지도,강화 학습)
* 실시간으로 점진적인 학습을 하는지(안라인 학습과 배치 학습)
* 단순하게 알고 있는 데이터 포인트와 새 데이터 포인트를 비교하는 것인지 아니면 훈련 데이터셋에서 데이터 사이언티스트들 처럼 패턴을 발견하여 예측 모델을 만드는지(사례 기반 학습과 모델 기반 학습)


![머신러닝_유형.png](./images/ml/tensorflow/머신러닝_유형.png)


일단 아래에서는 지도 학습과 비지도 학습에 대해서 먼저 알아보고 넘어가겠다.

## 지도학습(Supervised learning)
지도학습에는 알고리즘에 주입하는 훈련 데이터에 레이블(Label)이라는 원하는 답이 포함된다. (그림 1-5)

![지도학습_레이블된훈련세트1.png](./images/ml/tensorflow/지도학습_레이블된훈련세트1.png)
분류(classification)가 전형적인 지도 학습 작업이며, 스팸 필터가 좋은 예이다. 스팸필터는 많은 메일 샘플과 소속 정보(스팸인지 아닌지)로 훈련되어야 하며, 어떻게 새 메일을 분류할지 학습해야 한다.

또 다른 전형적인 작업은 예측 변수(predictor variable)라 부르는 특성(feature)(주행거리, 연식, 브랜드 등)을 사용해 중고차 가격 같은 타깃수치를 예측하는 것이다. 이런 종류의 작업을 회귀(regression)라고 부른다.(그림 1-6)
시스템을 훈련시키려면 예측 변수와 레이블(중고차 가격)이 포함된 중고차 데이터가 많이 필요한다.

노트) 머신러닝에서 **속성(attribute)**은 데이터 타입(예를들면 주행거리, 연식 등)을 말한다. **특성(feature)**는 문맥에 따라여러 의미를 갖지만 일반적으로 속성과 값이 합쳐진 것을 의미한다.(예를 들면 주행거리=15,000).
하지만 많은 사람들이 속성과 특성을 구분하지 않고 사용한다.

![회귀.png](./images/ml/tensorflow/회귀.png)


### 중요 지도학습(Supervised learning) 알고리즘
**1. k-최근접 이웃(k-Nearest Neighbors. k-NN)** : 가장 간단한 머신러닝 알고리즘. 훈련 데이터를 저장하는것이 모델을 만드는 과정의 전부이다. 새로운 데이터 포인트에 대해 예측 할 땐 알고리즘이 훈련 데이터셋에서 가장 가까운 데이터 포인트, 즉 최근접 이웃을 찾는다.
작은 데이터셋일 경우, 기본 모델로서 좋고 설명하기 쉬움

**2. 선형회귀(Linear Regression)** : 선형회귀 분석은 변수들 사이의 관계를 분석하는데 사용하는 통계학적 방법이다. 이 방법의 장점은 알고리즘의 개념이 복잡하지 않고 다양한 문제에 폭 넓게 적용할 수 있다는 것이다.
지도학습 중 가장 기본이 되는 알고리즘 중 하나이이며, 대용량 데이터셋 가능. 고차원 데이터에 적용 가능.

**3. 로지스틱 회귀(Logistic Regression)**
	- 분류에 사용하는 모델이다.
	- 선형 함수 결과를 시그모이드 함수를 이용하여 0 ~ 1 사이로 압축한다.
	- 이진 분류는 0.5보다 높을 때는 True, 그이하는 Flase로 하여 모델을 학습시킨다.
	- 시그모이드 함수를 사용한 크로스 엔트로피 비용함수의 미분 결과는 선형 함수를 사용한 MSE 비용함수의 미분과 동일하다.
	- 로지스틱 회귀는 다중 분류도 지원.
	- 분류(Classification)
		- 클래스 레이블을 예측한다.
		- 출력 결과는 이산적이다.
		- Binary Classification(이진 분류), Multiclass Classification(다중 분류)
		- ex) 스팸분류 , 암 진단, 꽃의 품종 판별, 손글씨 숫자 분류

일반적으로 회귀분석은 다음과 같은 실제 응용 프로그램에서 사용할 수 있다.
- 신용 점수
- 마케팅 캠페인의 성공률 측정
- 특정 제품의 매출 예측율
- 특정 날에 지진이 발생할 확율

**4. 서포트 백터 머신(Support Vector Machines, SVM)** : SVM은 바이너리 분류 알고리즘(binary classification algorithm)입니다. N차원 장소에서 2가지 유형의 점 집합이 주어지면 SVM은 (N-1) 차원의 초평면(hyperplane)을 생성하여, 이 점들을 두 그룹으로 분리한다. 종이에 선형적으로 분리 가능한 2가지 유형의 포인트가 있다고 가정하면 SVM은 이 점들을 2가지 유형으로 분리하고 모든 점들로부터 가능한 멀리 위치하는 직선을 발견 할 것 이다. 규모면에서 SVM을 사용하여 해결된 가장 큰 문제는 디스플레이 광고, 사람의 이미지 분해 인식, 이미지 기반 성별 탐지, 대규모 이미지 분류 등이다.
비슷한 의미의 특성으로 이뤄진 중간 규모 데이터셋에 잘맞음. 데이터 스케일 조정 필요. 매개변수에 민감.

**5. 의사결정 트리(Decision Trees)** : 의사 결정 트리는 의사 결정 지원 도구로, 우연한 이벤트 결과, 리소스 비용 및 유틸리티를 포함하여 트리와 같은 그래프 또는 의사 결정 모델 및 가능한 결과를 사용한다.
비즈니스 의사 결정의 관점에서, 의사 결정 트리는 대부분의 시간에 올바른 결정을 내릴 확률을 평가하기 위해 질문해야 하는 예/아니오 질문의 최소 수이다. 방법으로 논리적인 결론에 도달하기 위해 구조화되고 체계적인 방식으로 문제에 접근 할 수 있다.


**6. 랜덤 포레스트(random forest)** : 랜덤 포레스트는 분류, 회귀분석 등에 사용되는 앙상블 학습 방법의 일종으로, 훈련 과정에서 구성한 다수의 결정 트리로 부터 분류 또는 평균 예측치(회귀분석)를 출력함으로써 동작한다.
랜덤 포레스트 방법은 크게 다수의 결정 트리를 구성하는 학습 단계와 입력 벡터가 들어왔을 때, 분류하거나 예측하는 테스트 단계로 구성되어 있다. 랜덤 포레스트는 검출, 분류, 그리고 회귀 등 다양한 애플리케이션으로 활용되고 있다.
결정 트리 하나보다 거의 항상 좋은 성능을 냄. 안정적이고 강력함. 데이터스케일 조정 필요 없음. 고차원 희소 데이터에는 잘 안맞음.

**7. 신경망/딥러닝(Neural networks/deep learning)** : 신경망이라 알려진 알고리즘들은 최근 딥러닝이란 이름으로 다시 주목받고 있다. 딥러닝이 많은 머신러닝 애플리케이션에서 매우 희망적인 성과를 보여주고 있지만, 특정 분야에 정교하게 적용되어 있을때가 많다.
특별히 대용량 데이터셋에서 매우 복잡한 모델을 들 수 있음. 매개 변수 선택과 데이터 스케일에 민감. 큰 모델은 학습이 오래 걸림.

## 비지도 학습(Unsupervised learning)
비지도 학습에는 말 그대로 훈련 데이터에 레이블(label)이 없다.(그림 1-7)
시스템이 아무런 도움 없이 학습한다.

![비지도학습.png](./images/ml/tensorflow/비지도학습.png)

### 중요 비지도 학습(Unsupervised learning) 알고리즘
-  **군집**
	- **k-평균(k-Means)**
	k-means는 클러스터링 문제를 풀기 위한 비감독 학습 알고리즘이다. 이 알고리즘은 간단한 방법으로 주어진 데이터를 지정된 클러스터 갯수(k)로 그룹핑한다. 한 클러스터 내의 데이터들은 동일한 성질을 가지며 다른 그룹에 대하여 구별된다. 즉 한 클러스터 내의 모든 엘리먼트들은 클러스터 밖의 데이터보다 더 닮아 있다.
    
    알고리즘의 결과는 센트로이드(centroid)라 불리는 K개의 포인트로서 서로 다른 그룹의 중심을 나타내며 데이터들은 K 클러스터 중 하나에만 속할 수 있다.한 클러스터 내의 모든 데이터들은 다른 센트로이드보다 자신의 센트로이드와의 거리가 더 가깝다.
    
    클러스터를 구성하는데 직접 에러 함수를 최소화하려면 계산 비용이 매우 많이든다. (NP-hard 문제로 알려져 있음) 그래서 스스로 로컬 최소값에 빠르게 수렴할 수 있는 방법들이 개발되어 왔다. 가장 널리 사용되는 방법은 몇번의 반복으로 수렴되는 반복 개선(iterative refinement) 테크닉이다.
    
	- **계층 군집 분석(Hierarchical Cluster Analysis, HCA)**
	계층 군집은 비슷한 군집끼지 묶어가면서 최종적으로는 하나의 케이스가 될때까지 군집을 묶는 클러스터링 이다.
    군집간의 거리를 기반으로 클러스터링을 하는 알고리즘이며, K Means와는 다르게 군집의 수를 미리 정해주지 않아도 된다.
	- **기댓값 최대화(Expectation Maximization, EM)**
	텐서플로우에서 제공하는지 확인 안됨.
- **시각화(Visualization)와 차원 축소(Dimensionality reduction)**
	- **주성분 분석(Principal Component Analysis. PCA)**
	- **커널(kernel)**
	- **지역적 선형 임베딩(Locally-Linear Embedding. LLE)**
	- **t-SNE(t-distributed Stochastic Neigbor Embedding)**
- **연관 규칙 학습(Association rule learning)**
	- **어프라이어리(Apriori)**
	- **이클렛(Eclat)**

#### 군집(Clustering)
블로그 방문자에 대한 데이터가 많이 있다고 하자. 비슷한 방문자들을 그룹으로 묶기 위해 군집 알고리즘을 적용하려 한다.(그림 1-8).
하지만 방문자가 어떤 그룹에 속하는지 알고리즘에 알려줄 수 있는 데이터 포인트가 없다. 그래서 알고리즘이 스스로 방문자 사이의 연결고리를 찾는다. 예를들어 40%의 방문자가 만화책을 좋아하며 저녁때 블로그 글을 읽는 남성이고, 20%는 주말에 방문하는 공상과학을 좋아하는 젊은 사람임을 알게 될지도 모른다. **계층 군집(hierarchical clustering) 알고리즘**을 사용하면 각 그룹을 더 작은 그룹으로 세분화 할 수 있다.
그러면 각 그룹에 맞춰 블로그에 글을 쓰는데 도움이 될 것이다.

![clustering.png](./images/ml/tensorflow/clustering.png)

#### 시각화(Visualization)
시각화 알고리즘도 비지도 학습 알고리즘의 좋은 예이다. 레이블이 없는 대규모의 고차원 데이터를 넣으면 도식화가 가능한 2D나 3D 표현을 만들어 준다.(그림 1-9).
이런 알고리즘은 가능한 한 구조를 그대로 유지하려 하므로(예를 들어 입력 공간에서 떨어져 있던 클러스터는 시각화된 그래프에서 겹쳐지지 않게 유지된다) 데이터가 어떻게 조직되어 있는지 이해할 수 있고 예상하지 못한 패턴을 발견할 수도 있다.

비슷한 작업으로는 너무 많은 정보를 잃지 않으면서 데이터를 간소화하려는 **차원 축소(dimensioonality reduction)**가 있다.
이렇게하는 한가지 방법은 상관관계가 있는 여러 특성을 하나로 합치는 것이다. 예를 들어 차의 주행거리는 연식과 매우 연관되어 있으므로 차원 축소 알고리즘으로 두 특성을 차의 마모 정도를 나타내는 하나의 특성으로 합칠 수 있다. 이를 특성 추출(Geature Extraction)이라고 한다.

참고) 머신러닝 알고리즘(지도학습 알고리즘)에 데이터를 주입하기 전에 차원축소 알고리즘을 사용하여 훈련 데이터의 차원을 줄이는 것이 유용할 때가 많다. 실행 속도가 훨씬 빨라지고 디스크와 메모리를 차지하는 공간도 줄고 경우에 따라 성능이 좋아지기도 한다.


![군집_시각화.png](./images/ml/tensorflow/군집_시각화.png)

#### 연관규칙 학습(Association rule learning)
널리 사용되는 또다른 비지도 학습은 대량의 데이터에서 특성 간의 흥미로운 관계를 찾는 연관규칙 학습이다. 예를들어 내가 슈퍼마켓을 운영한다고 가정하자. 판매 기록에 연관 규칙을 적용하면 바비큐 소스와 감자를 구매한 사람이 스테이크도 구매하는 경향이 있다는 것을 찾을 지도 모른다.

또 하나의 중요한 비지도 학습은 이상치 탐지(anomaly detection)이다. 예를 득ㄹ어 부정 거래를 막기 위해 이상한 신용카드 거래를 감지하고, 제조 결함을 잡아내고, 학습 알고리즘에 주입하기 전에 데이터셋에서 이상한 값을 자동으로 제거하는 것 등이다. 머신러닝 모델은 정상 샘플로 훈련되고, 새로운 샘플이 정상 데이터인지 혹은 이상치인지 판단한다.


![이상치탐지.png](./images/ml/tensorflow/이상치탐지.png)


## 준지도 학습(semisupervised learning)
어떤 알고리즘은 레이블이 일부만 있는 데이터도 달룰 수 있다. 보통은 레이블이 없는 데이터가 많고, 레이블이 있는 데이터는 아주 조금이다.
이를 준지도 학습이라고 한다.(그림 1-11)

구글 포토 호스팅 서비스가 좋은 예이다. 이서비스에 가족사진을 모두 올리면 사람 A는 사진 1, 5, 11에 있고, 사람 B는 사진  2, 5, 7에 있다고 자동으로 인식한다. 이는 비지도 학습(군집)이다.
이제 필요한 것은 이 사람들이 누구인가 하는 정보이다. 사람마다 레이블이 하나씩만 주어지면 사진에 있는 모든 사람의 이름을 알 수 있고, 편리하게 사진을 찾을 수 있다.

대부분의 준지도 학습 알고리즘은 지도 학습과 비지도 학습의 조합으로 이루어져 있다.
예를들어 심층 신뢰 신경망(deep belief network. DBN)은 여러 겹으로 쌓은 제한된 볼츠만 머신(restricted Boltzmann machine. RBM)이라 불리는 비지도 학습에 기초한다. RBM이 비지도 학습 방식으로 순차적으로 훈련된 다음 전체 시스템이 지도 학습 방식으로 세밀하게 조정된다.


![준지도학습.png](./images/ml/tensorflow/준지도학습.png)



## 출처

- [텐서플로우 블로그](https://tensorflow.blog/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D/2-5-%EC%9A%94%EC%95%BD-%EB%B0%8F-%EC%A0%95%EB%A6%AC/)
- [핸즈온 머신러닝](https://tensorflow.blog/%ED%95%B8%EC%A6%88%EC%98%A8-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-1%EC%9E%A5-2%EC%9E%A5/1-3-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-%EC%8B%9C%EC%8A%A4%ED%85%9C%EC%9D%98-%EC%A2%85%EB%A5%98/)


