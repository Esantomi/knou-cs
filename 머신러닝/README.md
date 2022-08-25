# 머신러닝

### 목차
- [1강. 머신러닝 소개](#1강-머신러닝-소개)
  - [머신러닝의 개념](#머신러닝의-개념)
  - [머신러닝의 처리 과정](#머신러닝의-처리-과정)
  - [머신러닝의 기본 요소](#머신러닝의-기본-요소)
  - [머신러닝에서의 주제](#머신러닝에서의-주제)

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
    - 입력 데이터가 어떤 부류에 속하는지를 자동으로 판단하는 문제
    - 베이즈 분류기, K-최근접이웃 분류기, 결정 트리, 랜덤 포레스트, SVM, 신경망(MLP, CNN, LSTM 등)
  - **회귀(regression)**
    - 입력 변수와 출력 변수 사이의 매핑 관계를 분석
    - 선형회귀, 비선형회귀, 로지스틱 회귀, SVM, 신경망(MLP, RBF, CNN, LSTM)
  - **군집화(clustering)**
    - 데이터 집합을 서로 비슷한 몇 개의 그룹(군집, cluster)으로 묶는 문제
    - 분류 문제와 달리 클래스 정보가 주어지지 않음
    - K-평균 군집화, 계층적 군집화, 가우시안 혼합 모델, 신경망(SOM)
- 데이터 표현
  - **특징 추출(feature extraction)**
    - 원래 데이터로부터 데이터 분석에 적용하기 좋은 특징을 찾아내는 문제
      - `예) 영상 데이터의 차원 축소, 데이터 시각화`
    - 주성분분석(PCA), 선형판별분석(LDA), MDS, t-SNE
- 분류(classification)
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
