# 인공지능과 컴퓨팅사고력
- 프라임칼리지 평생교육과정 일반교양 (2학점)

### 목차
- [1강. 인공지능의 의미](#1강-인공지능의-의미)
  - [인공지능이란?](#인공지능이란)
  - [기계학습이란?](#기계학습이란)
  - [신경망과 딥러닝이란?](#신경망과-딥러닝이란)

## 1강. 인공지능의 의미
### 인공지능이란?
- 인공지능의 접근 방법
  - **Symbolic AI** (**기호주의 인공지능**)
    - 규칙 기반 지식 표현
    - `예) IBM Deep Blue`
  - **Connectionist AI** (**연결주의 인공지능**)
    - 다른 말로 Non-Symbolic AI
    - Artificial Neural Networks (인공신경망)
      - 인간 두뇌에서 영감을 받은 계산 모델
      - 신경망: 퍼셉트론, 딥러닝
- 인공지능의 정의
  - **약 인공지능** (Weak AI)
    - "Machines can act as if they were intelligent"
    - 정의된 특정 목적을 달성하고 문제를 해결하는 능력
  - **강 인공지능** (Strong AI)
    - "Machines can actually thinking, not just simulating thinking"
    - 스스로 문제를 정의하고 해결, 지속적인 학습, 자아, 감정 등 인간이 가지는 광범위한 지적 능력을 포함
- 인공지능 구현의 판단 기준
  - **튜링 테스트** (Turing test)
    - A. Turing (1950) “Computing machinery and intelligence”
    - 사람과 구분하기 힘들 정도로 지능적 행동을 보이는지 확인
    - 지능적인 여부는 관심이 없고 사람의 행동을 얼마나 흉내 내는가를 고려
- 인공지능, 기계학습, 딥러닝의 관계  
  ![image](https://user-images.githubusercontent.com/61646760/177976883-296c4f66-fc7d-40ba-9be9-09a21ab85866.png)
  - **Artificial Intelligence** : 지능형 기계/프로그램의 제작과 관련된 분야
  - **Machine Learning** : 명시적으로 프로그래밍하지 않고도 학습할 수 있는 능력
  - **Deep Learning** : 심층 신경망에 기반한 학습 방법
### 기계학습이란?
- 기계학습에서의 주제
  - **분류** (Classification) : 입력된 데이터가 어떤 부류에 속하는지를 자동으로 판단하는 문제 (`e.g. 베이즈 분류기, K-NN, 신경망(MLP,CNN,LSTM), SVM, HMM 등`)
  - **군집화** (Clustering) : 데이터 집합을 서로 비슷한 몇 개의 그룹으로 묶는 문제 (`e.g. K-means, 신경망(SOM) 등`)
  - **회귀** (Regression) : 입력 변수와 출력 변수 사이의 매핑 관계를 분석
  - **예측** (Prediction) : 과거에 관찰된 데이터 집합의 특성을 분석, 새로 관찰될 데이터에 대해서 예측하는 문제
- 기계학습 시스템의 전반적인 구조  
  ![image](https://user-images.githubusercontent.com/61646760/177977281-7ee52cac-7192-4ae1-b681-c18bd7a78df9.png)
- 기계학습의 유형
  - **교사(supervised)** vs **비교사(unsupervised)**
    - 교사(지도) 학습 : 학습 시에 시스템이 내야 할 원하는 출력 값(target output)을 미리 알려주는 교사가 존재 → 분류, 회귀 문제
    - 비교사(비지도) 학습 : 학습 시에 원하는 출력 값에 대한 정보 없이 학습을 수행 → 군집화 문제
  - **강화 학습(reinforcement learning)** : 교사 신호가 보상(reward) 형태로 주어짐
  - 준지도 학습(semi-supervised learning)
  - 약 교사 학습(weakly supervised learning)
### 신경망과 딥러닝이란?
- 신경망과 딥러닝의 관계
  - **인공 신경망(artificial neural network)**
    - 생물학적 신경망을 모델링해서 수학적 함수로 표현한 것
    - 원하는 입출력 매핑 함수의 형태를 스스로 찾는 학습 능력을 가짐
    - 데이터를 이용하여 학습을 수행하므로 데이터 분석 툴로 사용
    - 학습 방식(데이터 분석 용도)에 따라 다양한 모델이 존재
  - **심층 신경망(Deep neural network)**
    - 발전된 형태의 신경망 모델들
    - 층상 구조 (입력층, 은닉층, 출력층)
    - 일방향의 정보 흐름
  - **심층 학습(Deep learning)** : 심층 신경망을 이용하여 데이터를 분석하는 기계학습 기술
- 대표적 신경망 모델
  - **퍼셉트론(Perceptron)**
    - Rosenblatt(1958)
    - 활성함수로 계단 함수 사용
    - 구조 : 단층, 전방향, 완전 연결
    - 학습 : 이진 입출력을 갖는 교사(지도) 학습
  - **다층 퍼셉트론(MLP, Multilayer Perceptron)**
    - 학습 → 교사 학습 + 오류 역전파 알고리즘
