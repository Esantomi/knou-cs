# 머신러닝

### 목차
- [1강. 머신러닝 소개](#1강-머신러닝-소개)
  - [머신러닝의 개념](#머신러닝의-개념)
  - [머신러닝의 처리 과정](#머신러닝의-처리-과정)
  - [머신러닝의 기본 요소](#머신러닝의-기본-요소)
  - [머신러닝에서의 주제](#머신러닝에서의-주제)
  - [학습 시스템 관련 개념](#학습-시스템-관련-개념)
- [2강. 지도학습: 분류](#2강-지도학습-분류)
  - [분류의 개념](#분류의-개념)
  - [베이즈 분류기](#베이즈-분류기)
  - [K-최근접이웃 분류기](#K-최근접이웃-분류기)
- [3강. 지도학습: 회귀](#3강-지도학습-회귀)
  - [회귀의 개념](#회귀의-개념)
  - [선형회귀](#선형회귀)
  - [선형회귀의 확장](#선형회귀의-확장)
  - [로지스틱 회귀](#로지스틱-회귀)
- [5강. 데이터 표현: 특징추출](#5강-데이터-표현-특징추출)
  - [선형변환에 의한 특징추출](#선형변환에-의한-특징추출)
  - [주성분분석법](#주성분분석법)
  - [선형판별분석법](#선형판별분석법)
  - [거리 기반 차원 축소 방법](#거리-기반-차원-축소-방법)
- [6강. 앙상블 학습](#6강-앙상블-학습)
  - [앙상블 학습의 개념](#앙상블-학습의-개념)
  - [배깅과 보팅](#배깅과-보팅)
  - [부스팅](#부스팅)
  - [결합 방법](#결합-방법)

### 교재 및 강의 구성
![image](https://user-images.githubusercontent.com/61646760/185350045-f4cea6ef-9456-49f8-959e-4b991fbc138f.png)

## 1강. 머신러닝 소개
### 머신러닝의 개념
- 딥러닝 ⊂ 머신러닝 ⊂ 인공지능
  - 머신러닝은 인공지능의 한 분야
  - 머신러닝 중 심층 신경망을 기반으로 하는 머신러닝 방법을 딥러닝이라고 함
- **인공지능(Artificial Intelligence, AI)**
  - 인간 지능을 모방하여 문제 해결을 위해 사람처럼 학습/이해하는 기계를 만듦
  - **약 인공지능(weak AI)**
    - 실제 지능의 소유 여부와 상관없이 **지능적인 것처럼 행동**하는 기계
    - 단지 정의된 특정 목적을 달성하고 문제를 해결하는 능력
  - **강 인공지능(strong AI)**
    - 지능의 모방이 아닌 **실제로 인간처럼 생각**하는 기계
    - 스스로 문제 정의 및 해결, 지속적인 학습, 자아, 감정 등의 광범위한 지적 능력을 포함
    - Artificial General Intelligence (AGI), Human-Level AI
- 인공지능의 역사  
  ![image](https://user-images.githubusercontent.com/61646760/185351677-b81bca09-3d49-47a2-97f2-1fce556267a1.png)
  - 인공지능의 성장 과정  
    ![image](https://user-images.githubusercontent.com/61646760/185351905-2ed8a7a2-77da-49dc-bf2f-192352b000ea.png)
- 머신러닝이란?
  - 기계학습
  - 인간이 갖고 있는 고유의 지능적 기능인 학습 능력을 기계를 통해 구현하기 위한 접근 방법
  - 주어진 데이터를 분석하여 그로부터 **일반적인 규칙이나 새로운 지식을 기계 스스로가 자동으로 추출**하기 위한 접근 방법  
    ![image](https://user-images.githubusercontent.com/61646760/185353424-720c0e6f-69b7-4a71-a1a8-6ddb763e5b87.png)
    - 규칙 기반 프로그래밍은 규칙을 지정해 주지만, 머신러닝은 규칙을 스스로 도출함
  - 왜 필요한가?
    - 데이터의 다양한 변형을 다루기 위해
    - **명시적 지식 표현, 프로그래밍이 어렵거나 불가능한 경우** 유용
- 딥러닝이란?
  - 심층 학습(deep learning)
  - 심층 신경망 기반의 머신러닝 분야
    - 입력층, 출력층 외에 은닉층이 많음
### 머신러닝의 처리 과정
![image](https://user-images.githubusercontent.com/61646760/186606200-2950960e-bde3-4e0f-8c58-507f9c96c79a.png)
### 머신러닝의 기본 요소
- 데이터와 데이터 분포
  - 데이터 표현  
    ![image](https://user-images.githubusercontent.com/61646760/186635791-e0086546-ea04-462d-bfc5-3118616e56c7.png)
    - 열 벡터(column vector)의 전위행렬(transpose)인 행 벡터(row vector)로 표기
  - 데이터 집합의 분포 특성
    - 해당 공간상에서 점들이 분포된 모양
    - 2차원 데이터 집합의 산점도(scatter plot)  
      ![image](https://user-images.githubusercontent.com/61646760/186636571-008ee68a-e32e-4364-9159-e3563e9a1db8.png)
- **특징 추출(feature extraction)**
  - 주어진 데이터를 처리하는 데 핵심이 되는 정보를 추출하는 것  
    ![image](https://user-images.githubusercontent.com/61646760/186637022-06fba006-dcea-4998-ab4d-56c75979eb17.png)
  - 목적 : 비용(계산량, 메모리) 절약, 데이터에 포함된 불필요한 정보의 제거
  - 사영(projection)에 의한 특징 추출  
    ![image](https://user-images.githubusercontent.com/61646760/186637225-de9cc5b9-1455-4ea5-8e4f-aca01f854d57.png)
- **성능 평가(performance evaluation)**
  - **학습 시스템(Learning System)**
    - 데이터로부터 학습을 통해 추출하고자 하는 정보를 표현하는 시스템  
      ![image](https://user-images.githubusercontent.com/61646760/186637805-7da3fb7f-9ac7-4af9-b2fe-bc5d5a2a7ae1.png)
    - 입·출력 매핑 형태의 함수로 정의
    - 학습 : 데이터를 이용하여 함수 `𝑓`를 찾는 것 → 학습 시스템의 매개변수 `𝜽`를 찾는 것
      - 학습의 궁극적 목표 : 앞으로 주어질 새로운 데이터에 대한 성능을 최대화하는 것
  - **목적 함수(objective function)**
    - 주어진 데이터 집합을 이용하여 학습 시스템이 달성해야 하는 목표를 기계가 알 수 있는 수학적 함수로 정의한 것
  - **오차 함수(error function)**
    - 대표적인 목적 함수
      - 손실 함수(loss function), 비용 함수(cost function)라고도 함
    - 학습 시스템의 출력 값과 원하는 출력 값의 차이(‘오차’)로 정의
    - 학습의 목적 : 오차를 최소화하는 것
  - 오차 함수를 이용한 성능 평가 기준
    - **학습 오차(training error)**  
      ![image](https://user-images.githubusercontent.com/61646760/186639261-e423ec0c-1234-4f9e-8422-03ad746cbfb2.png)
      - 학습에 사용된 데이터(‘학습 데이터’) 집합에 대해 계산된 오차
    - **테스트 오차(test error)**  
      ![image](https://user-images.githubusercontent.com/61646760/186639778-4961c5af-83cb-4fea-a1a4-40e476805867.png)
      - 학습에 사용되지 않은 새로운 데이터(‘테스트 데이터’) 집합에 대해 계산된 오차
      - **경험 오차(empirical error)**
    - **일반화 오차(generalization error)**  
      ![image](https://user-images.githubusercontent.com/61646760/186639984-b8661340-efa9-4d9c-8b85-f77d227da3de.png)
      - 관찰될 수 있는 모든 데이터 분포 전체에 대해 정의되는 오차
      - 실제 계산이 불가해서 테스트 오차로 대신하여 평가
  - 일반화 오차의 추정
    - **교차검증법(cross validation method)**
      - 제한된 데이터 집합을 이용하여 일반화 오차에 좀 더 근접한 오차 값을 얻어 내기 위한 방법
      - **K-분절 교차검증법(K-fold cross validation)**  
        ![image](https://user-images.githubusercontent.com/61646760/186640487-7b88b2fd-e97c-442f-96ad-c003b3ff9552.png)
### 머신러닝에서의 주제
- 데이터 분석
  - **분류(classification)**
    - 입력 데이터가 어떤 부류(class)에 속하는지를 자동으로 판단하는 문제
      - `예) ~인식 (숫자인식, 얼굴인식, 생체인식)`
    - 베이즈 분류기, K-최근접이웃 분류기, 결정 트리, 랜덤 포레스트, SVM, 신경망(MLP, CNN, LSTM 등)
  - **회귀(regression)**
    - 입력 변수와 출력 변수 사이의 매핑 관계를 분석
      - `예) 시계열 예측 : 시장 예측, 환율 예측, 주가 예측 등`
    - 선형회귀, 비선형회귀, 로지스틱 회귀, SVM, 신경망(MLP, RBF, CNN, LSTM)
  - **군집화(clustering)**
    - 데이터 집합을 서로 비슷한 몇 개의 그룹(군집, cluster)으로 묶는 문제
      - `예) 데이터 그룹화, 영상 분할`
    - 분류 문제와 달리 클래스 정보가 주어지지 않음
    - K-평균 군집화, 계층적 군집화, 가우시안 혼합 모델, 신경망(SOM)
- 데이터 표현
  - **특징 추출(feature extraction)**
    - 원래 데이터로부터 데이터 분석에 적용하기 좋은 특징을 찾아내는 문제
      - `예) 영상 데이터의 차원 축소, 데이터 시각화`
    - 딥러닝에서는 **Representation learning**이라고 함
    - 주성분분석(PCA), 선형판별분석(LDA), MDS, t-SNE
- **분류(classification)**
  - 분류 시스템의 입·출력 관계  
    ![image](https://user-images.githubusercontent.com/61646760/186642140-fe2126c7-1585-420c-8536-37d37a8da47d.png)
  - 학습 결과 : <strong>결정 경계(decision boundary)</strong>와 **결정 함수(decision function)**
  - 학습 목표 : 분류 오차를 최소화하는 최적의 결정 경계 `𝑔(𝒙;𝜽)=0`를 찾는 것
  - 성능 평가 척도  
    ![image](https://user-images.githubusercontent.com/61646760/186642520-6f06f098-9a5c-4ed1-ab35-0fa468b6621d.png)
    - 분류율(classification rate)
    - 분류 오차(classification error)
  - 2차원 분류 문제의 예  
    ![image](https://user-images.githubusercontent.com/61646760/186642800-7e6671d5-7ed7-4bd2-9bba-3eb94814efdc.png)
- **회귀(regression)**
  - 회귀 시스템의 입·출력의 관계  
    ![image](https://user-images.githubusercontent.com/61646760/188251410-70337ed3-96d7-4c67-baec-b41e490867fc.png)
  - 학습 결과 : 회귀 함수(regression function)
  - 학습 목표 : 회귀 오차를 최소화하는 최적의 회귀 함수 `𝑦=𝑓(𝒙;𝜽)`를 찾는 것  
    ![image](https://user-images.githubusercontent.com/61646760/188251488-fa12c227-3b8f-4bcd-b818-934509a8a983.png)
  - **제곱 오차(squared error)**  
    ![image](https://user-images.githubusercontent.com/61646760/188251478-fd803582-eb08-4201-b8d3-8ff16fcfd113.png)
- **군집화(clustering)**
  - 군집화 시스템의 입·출력의 관계  
    ![image](https://user-images.githubusercontent.com/61646760/188251538-4afe5f23-09ee-4683-a2ca-1c68cde5d5d3.png)
  - 학습 결과 : K개의 서로소(disjoint)인 부분집합(클러스터)
  - 학습 목표 : 최적의 클러스터의 집합을 찾는 것
    - 클러스터 내의 분산은 최소화, 클러스터 간의 분산은 최대화  
      ![image](https://user-images.githubusercontent.com/61646760/188251576-d0e1d1d1-77c0-419a-afa8-fe3b9fda45ae.png)
- **특징 추출(feature extraction)**
  - 특징추출 시스템의 입·출력의 관계  
    ![image](https://user-images.githubusercontent.com/61646760/188251806-46056a91-a366-4694-8641-19fb1bf56af7.png)
  - 학습 결과 : 변환 함수(embedding function)
  - 학습 목표 : 분석 목적에 따라 달라짐
    - `예) 차원 축소 : 원래 데이터가 가지는 정보로부터의 손실량 최소화`  
      ![image](https://user-images.githubusercontent.com/61646760/188251860-c61352a3-eba9-4e79-8d1a-ba2bf70b18d7.png)
### 학습 시스템 관련 개념
- 머신러닝의 유형  
  ![image](https://user-images.githubusercontent.com/61646760/188251893-85263aa5-318c-4ee0-957a-381fc8f3ea38.png)
  - **지도학습, 교사학습(supervised learning)**
    - 학습할 때 시스템이 출력해야 할 목표 출력 값(교사)을 함께 제공
    - **분류, 회귀**
  - **비지도학습, 비교사학습(unsupervised learning)**
    - 학습할 때 목표 출력 값에 대한 정보가 없음
    - **군집화**
  - **준지도학습, 반지도학습(semi-supervised learning)**
    - 지도학습 + 비지도학습
    - 클래스 레이블링 비용을 줄이려는 목적
  - **강화학습(reinforcement learning)**
    - 출력 값에 대한 교사 신호가 ‘보상(reward)’ 형태로 제공
    - 교사 신호는 정확한 값이 아니고, 즉시 주어지지 않음
- 학습 시스템의 복잡도  
  ![image](https://user-images.githubusercontent.com/61646760/188252218-79b5987b-1247-4c4b-b876-3f18e9aa8a9c.png)
- **과다적합(overfitting)**
  - 학습 시스템이 학습 데이터에 대해서만 지나치게 적합한 형태로 결정 경계가 형성되는 현상  
    ![image](https://user-images.githubusercontent.com/61646760/188252103-551b7e27-dccd-4e7e-85ba-b580a935cfc1.png)
    - 검증 오차가 증가하기 시작하는 지점이 최적의 복잡도
  - 원인 : 학습 데이터의 확률적 잡음과 학습 데이터 개수의 부족
  - 영향 : 일반화 성능 저하 초래
- 학습 시스템의 복잡도를 조정하는 방법
  - 다양한 변형을 가진 충분한 학습 데이터 사용
  - 조기 종료 방법
  - 정규항을 가진 오차 함수 사용
  - 모델 선택 방법
- 머신러닝의 고급 주제
  - **앙상블 학습(ensemble learning)**
    - 복수 개의 간단한 학습 시스템을 결합하여 일반화 성능을 향상시킴
  - **능동 학습(active learning)**
    - 학습 과정에서 데이터를 선별적으로 선택하여 수행
  - **메타 학습과 자동 머신러닝(meta-learning, auto ML)**
    - 학습 시스템의 복잡도 등의 하이퍼파라미터까지 학습을 통해 최적화
  - **지속/증분 학습(continual/incremental learning)**
    - 기존에 학습된 내용에 대한 손실 없이 새로운 내용을 추가로 학습

## 2강. 지도학습: 분류
### 분류의 개념
- 데이터 분류
  - 입력 데이터를 이미 정의된 몇 개의 클래스로 구분하는 문제
  - `예) 숫자인식, 얼굴인식 등`
  - 베이즈 분류기, K-최근접이웃 분류기, 결정 트리, 랜덤 포레스트, SVM, 신경망(MLP, CNN, LSTM 등)
- 분류기의 입출력 관계  
  ![image](https://user-images.githubusercontent.com/61646760/188248175-e9f8ffc8-ac4f-4278-93e5-07418b3dab9c.png)
  - 학습 결과 : 결정경계와 결정함수
- 결정경계 `𝑔(𝒙;𝜽)`를 얻는 두 가지 접근법
  - **확률 기반 방법**
    - `𝑃(𝐶_𝑘|𝒙)`를 추정하여 분류
    - **베이즈 분류기**
  - **데이터 기반 방법**
    - 데이터 간의 관계를 바탕으로 분류
    - **K-최근접이웃 분류기**
### 베이즈 분류기
- 확률 분포에 기반한 분류의 개념  
  ![image](https://user-images.githubusercontent.com/61646760/188248333-34a7fe72-8efe-4d20-b001-b357654c00b0.png)
### K-최근접이웃 분류기

## 3강. 지도학습: 회귀
### 회귀의 개념
- **회귀(regression)**
  - 입력 변수와 출력 변수 사이의 매핑 관계를 찾는 것
    - 입력과 출력 간의 관계를 나타내는 함수 `𝑓`를 찾는 것
    - `예) 시계열 예측 → 주가 예측, 환율 예측 등`  
      ![image](https://user-images.githubusercontent.com/61646760/188299053-629c629e-3b8f-49c7-9179-b8431e4d1537.png)
  - 선형회귀, 비선형회귀, 로지스틱 회귀, SVM, 신경망(MLP, RBF, CNN, LSTM)
- 입력·출력의 관계  
  ![image](https://user-images.githubusercontent.com/61646760/188299375-6a24560e-1659-4311-8e51-3143650437e9.png)
  - `𝒙_𝑖` : 입력
  - `𝑦_𝑖` : 목표 출력 값(target output)
  - 분류 문제와의 차이
    - 출력 값 형태의 차이
    - 분류는 이산적인 값을 갖는 class label, 회귀는 연속적인 값을 갖는 실수
- 학습 결과 : 회귀 함수
- 학습 목표 : 예측 오차를 최소화하는 최적의 회귀 함수 `𝑦=𝑓(𝒙;𝜽)`를 찾는 것
  - **최소제곱법(least square method)** : 제곱 오차 = (목표 출력 값 - 𝒙에 따른 실제 출력 값)의 제곱  
    ![image](https://user-images.githubusercontent.com/61646760/188299532-a0cc751a-d36e-47ef-a833-63d55d55d502.png)
- 보간법(interpolation)과 회귀
  - 데이터를 가장 잘 표현하는 직선/곡선을 찾는 경우  
    ![image](https://user-images.githubusercontent.com/61646760/188299703-cead80a9-c4d7-4140-a5c3-32a3c1aa60d3.png)
    - 보간 곡선 : 제곱 오차가 0이지만 매우 복잡
    - 회귀 직선 : 작은 오차, 전체적인 데이터의 경향을 보여 주는 입출력의 관계 표현에 적합
    - 주어진 데이터가 어느 정도의 노이즈, 관측 오차를 포함하고 있다는 가정하에, 보간 곡선과 같이 모든 점들을 지나는 정확한 곡선을 찾는 것은 별 의미가 없고, 전체적인 데이터가 어떤 경향을 갖는 보여 주는 직선 또는 곡선을 찾는 것이 보다 합리적임
### 선형회귀
- **선형회귀(linear regression)**
  - 데이터집합 `𝐷={(𝑥_𝑖, 𝑦_𝑖)}_𝑖=1,⋯,𝑁 (𝑥_𝑖∈𝑅, 𝑦_𝑖∈𝑅)`에 대해 `(𝑥, 𝑦)` 관계(입력-출력 관계)를 설명할 수 있는 선형 함수 `𝑦=𝑤_1𝑥 + 𝑤_0 + 𝑒`를 찾는 것  
    ![image](https://user-images.githubusercontent.com/61646760/188301357-37e5050b-beca-4515-a45d-1d2f0053f7d4.png)
    - `𝑤_1` : 기울기
    - `𝑤_0` : 절편
    - `𝑒` : 오차 또는 잔차(residual)
    - 선형 함수상의 `𝑦_𝑖` 값과 실제 `𝑦` 값은 `𝑒_𝑖`의 오차를 가짐
- 좋은 선형회귀 모델
  - 모든 데이터에 대해서 잔차가 가능한 작아야 함  
    ![image](https://user-images.githubusercontent.com/61646760/188302130-0d4a537a-6f88-44a2-a736-1e9f9d4fbce1.png)
    - 즉 `𝑒_𝑖`가 작아야 함
  - 평가 기준
    - 모든 데이터에 대한 잔차의 합  
      ![image](https://user-images.githubusercontent.com/61646760/188302177-e9c9250a-e296-455d-bb20-f9b473876a48.png)
      - 부적합한 방법  
        ![image](https://user-images.githubusercontent.com/61646760/188302304-556193d9-7c7e-4a85-8253-29a57ca6e4fa.png)
        - `𝑒_𝑖`가 양수일 수도, 음수일 수도 있으므로 실선일 수도, 점선일 수도 있음 (두 직선이 생성)
    - **잔차의 제곱의 합**  
      ![image](https://user-images.githubusercontent.com/61646760/188302197-8d61ff80-6b5d-4f66-8dff-00865324ea7f.png)
      - 주어진 데이터 집합에 대해 유일한 직선을 생성
        - 원래 `1/𝑁`이 시그마 앞에 있어야 하지만, 없어도 무방하여 제거함
      - **평균 제곱 오차(MSE, Mean Squared Error)**
- 최적의 회귀 매개변수
  - 오차 함수  
    ![image](https://user-images.githubusercontent.com/61646760/188302399-873432db-d12a-4454-960e-f88e9c0aec08.png)
    - 평균 제곱 오차(MSE)
    - 오차 함수에서 찾아야 할 패러미터는 `𝑤_1`(기울기)과 `𝑤_0`(절편)
  - 최적의 매개변수  
    ![image](https://user-images.githubusercontent.com/61646760/188302407-04944ac2-785b-44e2-89aa-14dc374b286a.png)
    - `𝑤_1`(기울기)과 `𝑤_0`(절편)를 구하는 공식
      - 데이터를 바탕으로 `𝑤_1`을 먼저 계산하고, 그를 바탕으로 대입해서 `𝑤_0`를 계산하면 됨
    - `𝒙_bar`는 `𝒙`의 평균, `𝑦_bar`는 `𝑦`의 평균
- 매개변수 계산 과정
  ![image](https://user-images.githubusercontent.com/61646760/188303516-93d7cb3b-ebab-4a39-864e-5d7d171be8ac.png)
  - 색칠 칸은 각각 '각 매개변수에 대해서 편미분 수행', '연립방정식 형태로 정리'
  - `𝑤_0`에 대해 편미분, `𝑤_1`에 대해 편미분 후 -2는 날리고 시그마를 배분하여 `𝑤_0`과 `𝑤_1`에 해당하는 이원 일차 연립방정식 형태로 정리 후 풀어 주면 최적의 매개변수 `𝑤_1`과 `𝑤_0`을 구할 수 있음
  - 예제  
    ![image](https://user-images.githubusercontent.com/61646760/188304116-302571b9-7592-4b68-aee9-d781e4121454.png)
    - 상단 '데이터', 하단 '회귀함수'
- 예측과 평가
  - 회귀 함수를 사용한 새 데이터 `𝑥_𝑛𝑒𝑤`에 대한 예측  
    ![image](https://user-images.githubusercontent.com/61646760/188304256-b0dac235-5b36-4bb0-a6cd-2a4b41dea3f9.png)
  - 테스트 데이터 집합 ![image](https://user-images.githubusercontent.com/61646760/188304296-4b4e013f-10a7-48bb-b311-68c3fd41ea52.png)에 대한 평가 기준
    - **평균 제곱 오차(Mean Squared Error: MSE)**  
      ![image](https://user-images.githubusercontent.com/61646760/188304359-52f0609b-57ce-43cd-9384-8fd4147a8e8e.png)
      - 목표 출력 값과 실제(시스템) 출력 값의 차 제곱의 평균
    - **평균 제곱근 오차(Root Mean Square Error: RMSE)**  
      ![image](https://user-images.githubusercontent.com/61646760/188304368-1673cde3-47f3-4301-9871-ddcaf6ba840d.png)
      - 제곱에 루트를 씌움
      - 루트 때문에 제곱이 사라지므로 목표 출력 값과 실제 출력 값 간의 차이를 보다 직관적으로 파악할 수 있음
- **다변량 선형 회귀(Multivariate Linear Regression)**
  - n차원 입력 벡터 `𝒙 = {𝑥_1, 𝑥_2, ⋯ , 𝑥_𝑛}`
    - 하나의 데이터 `𝒙`가 n차원 즉, 𝑛개의 값으로 이루어짐  
      ![image](https://user-images.githubusercontent.com/61646760/188305013-3d0fed0d-1ae5-4dad-b9f7-e66b60a1873c.png)
      - y축은 수축기 혈압
      - 나이, 몸무게가 주어졌을 때 수축기 혈압을 찾는 선형 평면
  - 입력이 여러 개의 값으로 이루어진 경우 (실제로 많은 경우)
  - 회귀함수  
    ![image](https://user-images.githubusercontent.com/61646760/188305093-fe175ebe-77f7-4b5c-91be-5a848c6771a0.png)
    - 입력(`𝑥`)은 𝑛개, 패러미터(`𝑤`)는 𝑛+1개
  - 행렬 형태의 표현  
    ![image](https://user-images.githubusercontent.com/61646760/188305164-668568e2-65ba-44db-9ef2-b14779d38356.png)
    - 빈칸은 '데이터 집합', '경우'
    - 데이터가 1개인 경우
      - `x̃` (x tilde) : 패러미터 𝑤는 𝑛+1개의 값을 가지므로, 데이터(`𝒙`)-패러미터(`𝑤`) 값 간 차원을 맞추기 위해, 원래 주어진 데이터 `𝒙`에 1이라는 값을 더한 `x̃`를 설정함
      - `𝑤^Tx̃`와 같은 행렬 형태로 표현 가능
    - 데이터가 여럿인 경우
      - 각각의 `𝑥_𝑖`는 n차원으로 이루어짐
      - 각각의 `𝑥_𝑖`에 1을 집어 넣고, 이를 `x̃_𝑖`로 표기
  - 오차 함수  
    ![image](https://user-images.githubusercontent.com/61646760/188305462-0f2b65e5-4d8a-47bf-a2bb-61b8f88ba485.png)
    - 목표 출력 값(`𝑦`)과 실제(시스템) 출력 값 `𝑿𝑤`의 차의 2차 노름(norm) 형태로 오차 함수가 주어짐
      - [나무위키 : 노름(수학)](https://namu.wiki/w/노름(수학))
  - 최적의 파라미터 `𝑤`  
    ![image](https://user-images.githubusercontent.com/61646760/188305482-28f76069-6e7e-4cc0-a060-b865679f3316.png)
    - 빈칸은 '를 곱하면'
    - 오차 함수를 최소화시키는 `𝑤`는, `𝑤`에 대해 오차 함수를 편미분하여 0이 되는 값
    - 행렬과 그 행렬의 역행렬을 곱하면 단위행렬이 되므로 좌변은 `𝑤`만 남음
    - 새 데이터 `𝑥_𝑛𝑒𝑤`에 대한 예측  
      ![image](https://user-images.githubusercontent.com/61646760/188305778-72bd2e82-97d2-4798-adaa-30242add6d94.png)
### 선형회귀의 확장
- 선형회귀의 한계
  - `𝑥`와 `𝑦`의 관계를 선형 매핑으로 표현할 수 없는 경우  
    ![image](https://user-images.githubusercontent.com/61646760/188305839-d9a97e51-4a0f-41eb-b632-97ca28fceb9f.png)
  - 선형화(linearization) 과정을 거친 후 선형회귀 적용
    - `𝑥`와 `𝑦`를 `x̃`와 `ỹ`로 적절히 변형한 후 선형 매핑 관계 `ỹ = 𝑚x̃ + 𝑏`를 찾는 방식
- 선형화(linearization)
  - 지수 형태  
    ![image](https://user-images.githubusercontent.com/61646760/188305930-2ab3d63b-c24c-4a11-967f-9aa721a9d84c.png)
    - 데이터 입출력의 관계가 지수 형태면 곧바로 선형회귀를 적용할 수 없음
    - 자연로그(ln)을 취해 선형화 과정을 거쳐야 함
      - `𝑥`와 `ln 𝑦`의 공간 그래프로 변경 후 선형회귀 적용 가능
  - 단순 거듭제곱 형태  
    ![image](https://user-images.githubusercontent.com/61646760/188306084-ecdc21c3-f3af-47dd-b9f1-7d4f0f51893f.png)
    - 로그를 취해 `log𝑥`와 `log𝑦`로 바꿔 선형회귀를 적용
  - 포화된 증가 형태  
    ![image](https://user-images.githubusercontent.com/61646760/188306148-2832d112-e6f6-419d-a3ac-c9e5e2684511.png)
    - 역수를 취하여 바뀐 공간에서 직선을 찾는 문제로 변형
- 다른 접근법
  - 보다 복잡한 형태의 곡선으로의 매핑을 위한 방법
  - **다항 회귀(polynomial regression)**
    - 고차다항식 사용  
      ![image](https://user-images.githubusercontent.com/61646760/188306261-127eff27-0079-4e65-9538-025fcc89ce15.png)
  - 비선형 입력 변환함수를 사용한 선형회귀  
    ![image](https://user-images.githubusercontent.com/61646760/188306273-73ba583c-4536-478a-96fa-0e1ca3943396.png)
  - **비선형회귀(nonlinear regression)**
    - 신경망과 같은 복잡한 비선형함수를 사용하는 방법
    - 커널을 이용하여 고차원 공간으로 매핑하는 SVM 적용
### 로지스틱 회귀
- **로지스틱 회귀(logistic regression)**
  - 범주형 데이터의 회귀
    - 선형회귀 분석의 종속변수(출력)를 범주형으로 확장한 것
      - 회귀의 출력은 기본적으로 실수(output∈R)
      - 출력을 실수가 아닌 범주(category), class label로 만든 것
    - 분류 문제에 적용 가능
      - 즉, **분류 문제에 적용할 수 있도록 회귀를 확장**시킨 것
    - 입력 값이 각 클래스에 속하는 확률 값을 회귀분석으로 예측  
      ![image](https://user-images.githubusercontent.com/61646760/188306446-e0afd23e-eb22-4b96-9366-3343ef828eca.png)
      - 우측 빈칸이 '로지스틱 회귀'
      - 0과 1이 class label(범주)
- **로지스틱 함수(logistic function)**
  - 𝑥 ∈ (−∞, ∞)를 항상 0, 1 범위로 매핑하는 S자형 함수  
    ![image](https://user-images.githubusercontent.com/61646760/188306531-82cfb737-1be0-4714-a1be-ba82e092d6fa.png)
  - 로지스틱 함수를 이용한 분류  
    ![image](https://user-images.githubusercontent.com/61646760/188306778-9fab2f31-989b-446a-8744-60f2bfa7836a.png)
    - 함수의 출력값 : 클래스 레이블에 대한 사후확률 `𝑃(𝑦=1|𝑥)`
      - 즉, 입력 값 𝑥가 주어졌을 때, class label이 1인 조건부 확률  
      ![image](https://user-images.githubusercontent.com/61646760/188306638-bb9c25e2-562d-46d8-a8c2-ddd7aa0ec890.png)
    - 로지스틱 함수를 이용한 사후확률 추정  
      ![image](https://user-images.githubusercontent.com/61646760/188306666-fbeb46e4-252e-4802-9770-6407dd287e81.png)
      - 결국 구하고 싶은 것은 `𝑚`과 `𝑏`
  - 파라미터 `𝑚`과 `𝑏` 값에 따른 함수의 형태  
    ![image](https://user-images.githubusercontent.com/61646760/188306884-5b5d757a-0cef-4f32-970e-e3e2f6a9f9fa.png)
- **오즈비(odds ratio, 승산비)**  
  ![image](https://user-images.githubusercontent.com/61646760/188306978-47f5b15a-30ef-4bd9-9bf6-434906f55cb3.png)
  - 분모 `1 - 𝑥가 주어졌을 때 𝑦가 1일(class C2에 속할) 확률` : C1에 속할 확률
  - 분자는 C2에 속할 확률
  - 즉, 입력 𝑥가 C1에 속할 확률과 C2에 속할 확률의 비율을 오즈비라고 함
    - `𝑥`가 C2에 속하면 분자가 크므로 오즈비는 1보다 큼
    - `𝑥`가 C1에 속하면 분모가 크므로 오즈비는 1보다 작음
- **로짓 함수(logit function)**
  - 오즈비에 대해 로그를 취한 것  
    ![image](https://user-images.githubusercontent.com/61646760/188306991-c3621b10-32ac-4d46-9bd6-1b1f35ed5d14.png)
    - 오즈비에 자연로그를 취하면 exponential이 사라짐  
      ![image](https://user-images.githubusercontent.com/61646760/188307206-4e2f7cda-998a-49ed-81dd-806cd0a3b1e9.png)
    - 로짓 함수(`𝑚𝑥 + 𝑏`)가 0보다 작으면 `𝑥`는 C1에 속함
- 로지스틱 회귀의 결정경계  
  ![image](https://user-images.githubusercontent.com/61646760/188307005-73bff439-0012-44ce-a2af-feccec3d5c23.png)
  - 로짓 함수를 0으로 둬서 판별함수, 결정경계로 사용 가능
- 로지스틱 회귀의 매개변수 추정
  - 데이터  
    ![image](https://user-images.githubusercontent.com/61646760/188307380-5f3e0a72-a348-4734-aae2-75171c99c41e.png)
  - `𝑝(𝑦|𝑥)`의 확률함수 : 베르누이 분포를 따름  
    ![image](https://user-images.githubusercontent.com/61646760/188307394-843ebda4-47ec-4eec-8fb0-3ef173e6342a.png)
  - 목적 함수 : `𝐷`에 대한 로그 우도(log likelihood)  
    ![image](https://user-images.githubusercontent.com/61646760/188307443-920fb150-bb79-43fb-9812-dd23a1dad03c.png)
    - 목적 함수를 이용해 `𝑚`과 `𝑏`를 찾아야 함
  - 추정 : **최대 우도 추정법(maximum likelihood estimation)**  
    ![image](https://user-images.githubusercontent.com/61646760/188307491-d42ddaeb-e3e7-493d-b244-eecc01368fd0.png)
    - 수치적 최적화 방법으로 반복적 추정을 통해 최적화
    - `𝑚`과 `𝑏`에 대해 편미분
  - 파라미터 `𝑚`과 `𝑏`의 추정 후 새로운 데이터의 분류 과정  
    ![image](https://user-images.githubusercontent.com/61646760/188307510-789afada-02af-4cd6-9197-be57c94e4c1e.png)
### 정리하기
![image](https://user-images.githubusercontent.com/61646760/188298889-9fbf6ece-1c46-4063-bbca-e23142f37116.png)

## 5강. 데이터 표현: 특징추출
### 선형변환에 의한 특징추출
- **특징 추출(feature extraction)**  
  ![image](https://user-images.githubusercontent.com/61646760/189130124-cc837069-3a4f-4083-92f3-4762db727128.png)
  - 학습(데이터 분석)을 통해 변환함수 `Φ`를 찾는 것을 특징 추출이라고 함
    - `Φ`를 통해 𝑛차원의 입력 데이터 `𝑥`는 `𝑦`라는 `𝑚` 차원의 특징 벡터로 변환됨
  - 학습(특징 추출)의 목적
    - 분석에 불필요한 정보를 제거하고 **핵심 정보만 추출**
    - **차원 축소**를 통한 분석 시스템의 효율 향상
      - 계산량/메모리 감소, 성능 향상
- **변환함수(embedding function, transformation function)** 종류
  - **선형변환(linear transformation)**
    - 𝑛차원 열벡터 `𝒙`에 변환행렬 `𝐖(𝑛×𝑚)`를 곱하여 𝑚차원 특징을 획득  
      ![image](https://user-images.githubusercontent.com/61646760/189291893-5e8ed868-ce17-4f69-a8af-c3a47771623e.png)
      - `𝐖(𝑛×𝑚)`을 transpose한 것은 `(𝑚×𝑛)`이고, `𝒙`는 `(𝑛×1)`이므로, `𝑦`는 `(𝑚×1)`
    - 통계적 방법으로 특징벡터 `𝒚`가 원하는 분포가 되도록 하는 `𝐖`를 찾음
  - **비선형변환(nonlinear transformation)**
    - 복잡한 비선형 함수 `∅(𝒙)`를 이용하여 𝑛차원 벡터를 𝑚차원 벡터로 매핑
    - 사용 방법
      - 수작업(handcrafted)에 의한 특징추출
      - 표현학습(representation learning) : 딥러닝에서 주로 사용하는 용어
- **수작업에 의한 특징추출**
  - 입력 데이터의 특성과 분석 목적에 맞는 특징을 개발자가 설계함
    - 전통적인 방법 (여전히 사용)
      - 데이터 특성에 따라 다른 특징 사용
      - 어떤 특징을 사용할지는 개발자가 결정
    - 숫자 인식을 위한 특징  
      ![image](https://user-images.githubusercontent.com/61646760/189293737-e43efe76-c95b-456d-88be-2ab73a3e8795.png)
    - 영상 분석을 위한 특징 : 에지, 가로/세로 방향 성분 등
    - 문서 분석을 위한 특징 : 단어의 발생 빈도 등
- **표현학습(representation learning)**
  - 특징추출을 위한 비선형 변환함수를 신경망 등의 머신러닝 모델로 표현
  - 학습을 통해 분석이 잘 되도록 변환함수의 최적화가 가능
  - `예) 딥러닝 모델을 이용한 얼굴 인식용 특징추출 (CNN)`  
    ![image](https://user-images.githubusercontent.com/61646760/189294756-a5d31c76-ecbf-4422-9519-4231e1f06dc9.png)
- **선형변환에 의한 특징추출**
  - 차원 축소 관점에서의 특징추출
    - 데이터의 특성에 의존하지 않는 좀 더 일반적인 사용 가능
    - 데이터의 차원이 크다는 것은 많은 정보를 가지고 있다는 것
      - 많은 정보 중에는 불필요한 정보도 많음
      - 이를 처리로 돌리면 처리 성능을 높일 수 있음
    - 데이터의 차원이 커지면 성능도 계속 좋아질까?
      - 어느 정도까지는 좋아지지만 갑자기 안 좋아지는 구간이 있으며, 이를 차원의 저주라고 부름  
        ![image](https://user-images.githubusercontent.com/61646760/189297817-e6a739b3-ac51-4d57-810d-57f2f4c2e471.png)
      - **[차원의 저주(Curse of Dimensionality)](https://en.wikipedia.org/wiki/Curse_of_dimensionality)** : 차원이 증가함에 따라 모델의 성능이 나빠지는 현상
    - 차원 축소  
      ![image](https://user-images.githubusercontent.com/61646760/189298448-15970ecf-a932-479d-90a8-282adc215dbb.png)
      - 𝑛차원의 랜덤 벡터(`𝒙`)를 변환행렬 `𝐖`를 통해 𝑚차원의 특징 벡터(`𝑦`)로 축소 (당연히 𝑚은 𝑛보다 작음)  
        ![image](https://user-images.githubusercontent.com/61646760/189299236-b46c2339-174a-451e-82e3-240f5df22e74.png)
        - **특징값 `𝑦_𝑖` : `𝒙`를 `𝐖`의 열벡터 `𝒘_𝑖` 위로 사영한 값 (단, `𝒘_𝑖`는 단위벡터)**
          - **단위벡터(unit vector)** : 길이가 1인 벡터
  - 2차원 데이터 `𝒙`를 1차원 특징 `𝑦`로 변환
    - 벡터 `𝒙`를 `𝒘` 위로 사영 : `𝑦=𝑤^𝑇𝒙` (단, `𝒘`는 단위벡터)  
      ![image](https://user-images.githubusercontent.com/61646760/189468763-50fbb658-a387-4ee0-a63f-1f97a20d7c1d.png)
      - 벡터 `𝒙`를 `𝒘` 위로 사영(projection)한 결과 값이 특징벡터 `𝑦`
  - 3차원 데이터 : 2차원 특징추출  
    ![image](https://user-images.githubusercontent.com/61646760/189474079-9c9c70e0-b032-4788-aab1-16fddeb979b8.png)
    - `𝒙(3x1)`, 변환행렬 `𝐖`는 (크기가 1이라 단위벡터인) 2개의 열벡터(`𝒘_1`, `𝒘_2`)를 가짐
### 주성분분석법
### 선형판별분석법
### 거리 기반 차원 축소 방법

## 6강. 앙상블 학습
### 앙상블 학습의 개념
- **앙상블 학습(ensemble learning)**
  - 선형 분류기와 같은 간단한 학습기로 학습을 수행하지만, 복수 개의 학습기를 결합함으로써 결과적으로 더 좋은 성능을 가진 학습기를 만드는 방법  
    ![image](https://user-images.githubusercontent.com/61646760/192756330-49c7b2e0-c274-466d-9fe2-50472173ffb6.png)
    - 즉, **간단한 학습기를 결합해 사용함으로써 복잡한 학습기와 같은 성능**을 내는 것
      - 간단한 학습기는 구현이 쉬우나 성능이 떨어지고, 복잡한 학습기(SVM, 딥러닝 등)는 성능은 좋으나 학습을 통해 찾아야 할 패러미터가 많을 뿐 아니라 찾기 어렵고, 과적합을 통해 일반화 성능이 떨어지는 문제가 있을 수 있음
    - 그런데 어떤 학습기를 사용해, 어떻게 결합할 것인가?
- 학습기 결합의 고려 사항
  - 학습기의 차별화 방법
    - **학습 알고리즘의 차별화**
      - 접근 방법이 서로 다른 학습기 선택
        - `예) 베이즈 분류기&K-NN, 신경망&SVM`
      - 학습 알고리즘이 완전히 다른 학습기를 함께 사용
    - **모델 선택과 관련된 패러미터의 차별화**
      - K값이 서로 다른 복수의 K-NN, 은닉층의 뉴런 수가 서로 다른 복수의 MLP
        - `예) K 값을 5, 10, 15, 20 등등 여럿으로 줌`
    - **학습 데이터의 차별화**
      - 같은 모델을 사용하되 학습 데이터 집합을 달리하여 복수 개의 학습기를 생성
      - 이론적으로 성능이 증명되어 있음
        - 따라서 집중해서 살펴볼 것!!
  - 학습기 결합 방법
    - 병렬적 결합 : 각 학습기의 결과를 한번에 모두 함께 고려하여 하나의 최종 결과를 생성
    - 순차적 결합 : 각 학습기의 결과를 단계별로 결합
- 앙상블 학습의 개요  
  ![image](https://user-images.githubusercontent.com/61646760/192758277-4644644d-c822-474a-905f-9d61d217677c.png)
  - 학습 데이터 생성 방법에 따른 분류
    - 필터링(filtering)에 의한 방법 : **초기 부스팅 방법**, **캐스케이딩 방법**
      - 각 학습기의 학습 때마다 새로운 데이터를 생성하고, 이를 이미 학습이 완료된 학습기에 적용하여 제대로 처리되지 못하는 데이터들만 필터링하여 학습
    - 리샘플링(resampling)에 의한 방법 : **배깅 방법**, MadaBoost 방법
      - 각 학습기의 학습 때마다 학습 데이터를 새로 생성하지 않고, 주어진 전체 학습 데이터로부터 일부 집합을 추출하여 각 학습기를 학습
    - 가중치 조정(reweighting)에 의한 방법 : **AdaBoost 방법**
      - 모든 학습기에 대해 동일한 학습 데이터를 사용하되, 각 데이터에 대해 가중치를 주어 학습에 대한 영향도를 조정
### 배깅과 보팅
- 배깅과 보팅
  - 배깅(bagging) : 학습기를 선택하는 방법
  - 보팅(voting) : 학습기의 결과를 결합하는 방법
- **배깅(bagging)에 의한 학습**
  - “bootstrap aggregating”의 약자
  - 부트스트랩 방법을 앙상블 학습에 적용한 것
    - **부트스트랩(bootstrap)** : 제한된 데이터 집합을 이용하여 시스템의 학습과 평가를 동시에 수행하기 위한 리샘플링 기법
    - 즉, 하나의 데이터 집합에서 데이터를 일부분 추출하여 각각의 시스템을 학습시킨 것
  - 배깅에 의한 𝑀개의 서로 다른 학습기의 학습 과정
    1. 𝑁개의 데이터로 이루어진 학습 데이터 집합 𝑋를 준비하고, 학습을 위한 학습기 모델(`예) KNN, 베이즈 분류기, 신경망 등`)을 정의한다. **𝑀개의 학습기를 각각 학습시키기 위해 사용될 데이터 집합의 크기 Ñ**(Ñ≤𝑁)을 정한다.
    2. 𝑖번째 학습기 ℎ_𝑖(𝒙) 모델의 파라미터를 초기화하고, 학습 데이터 집합 𝑋로부터 Ñ개의 데이터를 랜덤하게 선출하여 데이터 집합 𝑋_𝑖를 만든다. 이때 같은 데이터가 중복해서 선출되는 것도 허락한다(복원 추출).
    3. 데이터 집합 𝑋_𝑖를 이용한 학습을 수행하여 최적화된 파라미터 𝜽_𝑖를 찾아 𝑖번째 학습기를 위한 판별함수 ℎ_𝑖(𝒙, 𝜽_𝑖)를 얻는다.
    4. ②~③ 과정을 𝑀번 반복하여 서로 다른 𝑀개의 학습기를 생성하고, 이들을 결합하여 최종 판별함수 𝑓(ℎ_1, ℎ_2, ⋯, ℎ_𝑀)을 찾는다.
  - 고려 사항
    - 데이터 집합의 크기 Ñ
      - 주어진 전체 학습 데이터 집합 𝑋의 크기 𝑁이 충분히 크지 않으면 Ñ과 𝑁은 같은 값으로 지정
      - 복원추출을 사용하므로 매 단계마다 생성되는 데이터의 집합은 동일하지 않음
    - 학습에 사용될 학습기의 모델
      - 학습기에 의해 찾아지는 판별함수가 데이터 집합의 변화에 민감한 모델을 선택하는 것이 바람직
        - 데이터 집합만 바꿔 적용하므로 
      - `예) 다층 퍼셉트론, 최근접이웃 분류기 등`
  - **배깅(bagging)으로 M개의 학습기를 만든 뒤, 학습기를 결합하기 위해 보팅(voting)을 사용**함
- **보팅(voting)에 의한 학습**
  - 보팅법(voting), “**committee machine**”
    - 𝑀개의 학습기 결과를 모두 동일한 정도로 반영하여 평균한 결과를 얻는 방법(“단순평균법”)
  - 보팅에 의한 결합함수  
    ![image](https://user-images.githubusercontent.com/61646760/192771093-7eb6924e-49df-4a2d-836b-f437779aba57.png)
    - 각각의 학습기가 도출한 결과를 다 더한 뒤 1/𝑀로 나눔으로써 평균을 내 줌
    - 이산적인 값이 나오는 분류 문제의 경우, 별도의 처리 과정이 필요
### 부스팅
### 결합 방법
