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
  - [선형회귀](#선형회귀]
  - [선형회귀의 확장](#선형회귀의-확장)
  - [로지스틱 회귀](#로지스틱-회귀)

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
    - 학습 : 데이터를 이용하여 함수 𝑓를 찾는 것 → 학습 시스템의 매개변수 𝜽를 찾는 것
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
  - 학습 목표 : 분류 오차를 최소화하는 최적의 결정 경계 **𝑔(𝒙;𝜽)=0**를 찾는 것
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
  - 학습 목표 : 회귀 오차를 최소화하는 최적의 회귀 함수 <strong>𝑦=𝑓(𝒙;𝜽)</strong>를 찾는 것  
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
- 결정경계 𝑔(𝒙;𝜽)를 얻는 두 가지 접근법
  - **확률 기반 방법**
    - 𝑃(𝐶_𝑘|𝒙)를 추정하여 분류
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
    - 입력과 출력 간의 관계를 나타내는 함수 𝑓를 찾는 것
    - `예) 시계열 예측 → 주가 예측, 환율 예측 등`  
      ![image](https://user-images.githubusercontent.com/61646760/188299053-629c629e-3b8f-49c7-9179-b8431e4d1537.png)
  - 선형회귀, 비선형회귀, 로지스틱 회귀, SVM, 신경망(MLP, RBF, CNN, LSTM)
- 입력·출력의 관계  
  ![image](https://user-images.githubusercontent.com/61646760/188299375-6a24560e-1659-4311-8e51-3143650437e9.png)
  - 𝒙 : 입력
  - 𝑦 : 목표 출력 값(target output)
  - 분류 문제와의 차이
    - 출력 값 형태의 차이
    - 분류는 이산적인 값을 갖는 class label, 회귀는 연속적인 값을 갖는 실수
- 학습 결과 : 회귀 함수
- 학습 목표 : 예측 오차를 최소화하는 최적의 회귀 함수 𝑦=𝑓(𝒙;𝜽)를 찾는 것
  - **최소제곱법(least square method)** : 제곱 오차 = (목표 출력 값 - 𝒙에 따른 실제 출력 값)의 제곱  
    ![image](https://user-images.githubusercontent.com/61646760/188299532-a0cc751a-d36e-47ef-a833-63d55d55d502.png)
- 보간법(interpolation)과 회귀
  - 데이터를 가장 잘 표현하는 직선/곡선을 찾는 경우  
    ![image](https://user-images.githubusercontent.com/61646760/188299703-cead80a9-c4d7-4140-a5c3-32a3c1aa60d3.png)

### 선형회귀

### 선형회귀의 확장

### 로지스틱 회귀

### 정리하기
![image](https://user-images.githubusercontent.com/61646760/188298889-9fbf6ece-1c46-4063-bbca-e23142f37116.png)
