# 정보통신망

### 목차
- [1강. 컴퓨터 통신망의 소개](#1강-컴퓨터-통신망의-소개)
  - [컴퓨터와 통신](#컴퓨터와-통신)
  - [데이터 통신 시스템](#데이터-통신-시스템)
  - [통신 프로토콜](#통신-프로토콜)
- [2강. 데이터 통신의 기초(I)](#2강-데이터-통신의-기초I)
  - [데이터 통신의 개요](#데이터-통신의-개요)
  - [변조 및 복조](#변조-및-복조)
  - [전송 코드](#전송-코드)

## 1강. 컴퓨터 통신망의 소개
### 컴퓨터와 통신
- **분산 시스템(distributed systems)**
  - 컴퓨터 자원을 공유하고 그들의 확장과 축소를 용이하도록 하며 오류에 대한 신뢰도를 높일 수 있도록 컴퓨터 자원을 분산시켜 작업을 처리하는 시스템
  - 분산의 정도
    - **강연결(strongly coupled) 분산 시스템** : 분산된 거리가 비교적 짧고 처리기 간의 상호 작용이 비교적 많은 분산 시스템
    - **약연결(loosely coupled) 분산 시스템** : 분산된 거리가 비교적 길고 처리기 간의 상호 작용이 비교적 적은 분산 시스템
      - 정보통신망이 이에 해당
        - 즉, 정보통신망은 약연결 분산 시스템이다.
      - `예) LAN, MAN, WAN`
  - 분산 시스템의 종류  
    ![image](https://user-images.githubusercontent.com/61646760/156188627-9345c0af-4ae3-473a-a455-5adb697bb0db.png)
    - 강연결 분산 시스템
      - Data flow machine
      - Multiprocessor
    - 약연결 분산 시스템
      - 근거리 통신망(LAN: Local area network)
      - 도시권 통신망(MAN: Metropolitan area network)
      - 원거리 통신망(WAN: Wide area network)
      - Interconnection network
    - **개인 통신망(PAN: Personal area network)**
      - 개인의 작업 공간을 중심으로 장치들을 서로 연결하기 위한 컴퓨터 네트워크
      - 강연결? 약연결?
- 컴퓨터 통신망의 정의
  - **통신(communication)**
    - 협의로서, 원격통신(telecommunication)
    - 전자적 정보의 전송
  - **데이터 통신(data communication)**
    - 컴퓨터 시스템에 의한 데이터 처리 기술과 통신 시스템에 의한 데이터 전송 기술이 결합된 것
  - **데이터 통신망(data communication network)**
    - 데이터 통신 기술과 망 기술이 융합된 개념
      - 즉, 데이터 처리 기술 + 데이터 전송 기술 + 망 기술
    - 곧, 컴퓨터 통신망(computer communication network)
    - 약연결 분산 시스템
- 컴퓨터 통신망의 목적
  - 자원의 공유
  - 처리 기능의 분산
  - 신뢰도 향상
  - 안전성 보장
  - 호환성 확대
- 컴퓨터 통신망의 역사  
  ![image](https://user-images.githubusercontent.com/61646760/156192940-9696461f-4a2d-474d-a584-916ea9cb23b1.png)
  - 원격 계산기에 데이터 통신(G. Stibitz, 1940년)
    - 최초로 멀리 있는 계산기에 데이터를 송신하고 수신함
  - **SAGE 시스템**(1958년)
    - Semi-Automatic Ground Environment
    - 컴퓨터와 통신을 결합시킨 최초의 컴퓨터 통신 시스템
  - **ARPA Network** (1960년대)
    - Advanced Research Project Agency
      - 미국 국방부의 고등 연구 계획국(ARPA)의 주도하에 만들어진 세계 최초의 패킷 교환 네트워크
    - TCP/IP 개발
      - 인터넷 프로토콜인 TCP/IP를 처음 개발하여 사용
      - 인터넷의 전신이므로 대단히 중요함
    - 패킷 교환 네트워크
  - **SABRE 시스템**(1964년)
    - Semi-Automatic Business Research Environment
    - American Airline사의 여객기 좌석 예약 업무 처리
  - **ALOHA 시스템**(1968년)
    - Additive Links Online Hawaii Area
    - 하와이 대학, 실험적 무선 패킷 교환 네트워크
  - **TELENET**(1974년)
    - 최초의 대중화된 상용 패킷 교환 네트워크
- 컴퓨터 통신망의 서비스
  - e-Mail
  - 파일 전송
  - 분산 데이터베이스 시스템
  - 웹 서비스
  - SNS
### 데이터 통신 시스템
- 데이터 통신 시스템의 구성  
  ![image](https://user-images.githubusercontent.com/61646760/156470144-5624ccb7-6521-4033-b0a1-e91a9d96cccf.png)
  - 단말 장치(DTE: Data Terminal Equipment)
  - 데이터 전송 회선
    - 신호 변환 장치(Data Communication Equipment) : Modem, DSU(Digital Service Unit)
    - 통신 회선
  - 통신 제어 장치(CCE: Communication Control Equipment) : CCP라고도 함
  - 컴퓨터
- 데이터 통신 시스템의 기능  
  ![image](https://user-images.githubusercontent.com/61646760/156523391-8c0d39ff-a9db-4356-bbcc-c458e2bcd4e6.png)
- **통신 소프트웨어(Communication software)**
  - 데이터 전송 회선과 통신 제어 장치를 이용하여 컴퓨터와 단말 장치 사이에서 정보를 송수신하기 위한 프로그램  
    ![image](https://user-images.githubusercontent.com/61646760/156470640-f6ed61be-0d5a-402b-91dc-30c8632faac0.png)
### 통신 프로토콜
- **통신 프로토콜(communication protocol)**
  - 통신을 원하는 두 개체 간에 무엇을, 어떻게, 언제 통신할 것인지를 서로 정한 규약
  - 프로토콜의 주요 요소
    - 구문(syntax) : 데이터 형식이나 신호 수준 등을 포함한다.
    - 의미(semantic) : 전송의 조정, 오류 관리를 위한 제어 정보를 포함한다.
    - 타이밍(timing) : 전송 속도 조절 및 전송 순서 조정 등을 포함한다.
- **컴퓨터 통신망 구조(computer network architecture)**
  - 모든 통신 기능을 담고 있는 하나의 프로토콜을 사용하는 대신 통신 기능을 구현하는 프로토콜의 구조적 집합
    - **A set of protocols**
  - IBM, SNA(System Network Architecture) : 1974년에 만들어진 IBM의 사유 네트워크 아키텍처
  - DEC, DNA(Digital Network Architecture)
  - **OSI 참조 모델(Open Systems Interconnection Reference Model)**  
    ![image](https://user-images.githubusercontent.com/61646760/156527215-75764754-2b09-490c-b92e-0166ee84752c.png)
    - 7-Layered Reference Model
    - 국제표준화기구(ISO)에서 개발

## 2강. 데이터 통신의 기초(I)
### 데이터 통신의 개요
- 통신이란? 한 점으로부터 다른 점으로 어떤 정보(data 또는 message)를 전달
  - 통신의 3대 요소  
    ![image](https://user-images.githubusercontent.com/61646760/156584998-129939fe-c8c1-405e-a251-0e16cd695523.png)
  - 통신 성능의 요인
    - 메시지가 서로 이해되어야 함 (coding)
    - 통신상의 간섭 현상이 있을 수 있음 (noise)
### 변조 및 복조
- **모뎀(MODEM, MOdulator and DEModulator)**
  - 정보 전달(주로 디지털 정보)을 위해 신호를 **변조**하여 송신하고 수신측에서 원래의 신호로 복구하기 위해 **복조**하는 장치
- **변조(modulation)**
  - 전송 신호(baseband signal)를 높은 주파수 대역의 반송파 신호(carrier signal)에 싣는 과정  
    ![image](https://user-images.githubusercontent.com/61646760/156586189-af9bbc72-1f5b-460f-9cad-81a2ef5fccea.png)
    - 위가 AM, 아래가 FM
    - oscillator로 반송파 생성
    - 반송파는 정현파라고도 함
  - 변조의 종류
    - 아날로그 변조 : 전송 신호가 아날로그 신호인 경우
    - 디지털 변조 : 전송 신호가 디지털 신호인 경우
  - 변조의 방식
    - 진폭 변조(Amplitude Modulation, AM)
    - 주파수 변조(Frequency Modulation, FM)
    - 위상 변조(Phase Modulation, PM)
- 아날로그 변조
  - **진폭 변조(Amplitude Modulation, AM)**
    - 베이스밴드 신호의 순간 진폭에 비례하여 반송파 신호의 순간 진폭을 변화시키는 방법  
      ![image](https://user-images.githubusercontent.com/61646760/156592652-026d97b8-aaf6-45cc-8408-9a226ec38690.png)
      - modulating signal이 곧 baseband signal
  - **주파수 변조(Frequency Modulation, FM)**
    - 반송파 신호의 진폭은 일정하게 한 채로 베이스밴드 신호를 주파수 변화로 변환시키는 방법  
      ![image](https://user-images.githubusercontent.com/61646760/156592742-c9e37f77-ef4b-4a15-afff-f02084241e50.png)
  - **위상 변조(Phase Modulation, PM)**
    - 반송파 신호의 진폭은 일정하게 한 채로 베이스밴드 신호를 주파수 위상각의 변화로 변환시키는 방법  
      ![image](https://user-images.githubusercontent.com/61646760/156592802-ad2c5d38-7d68-406c-ac32-365448dc74b0.png)
- 디지털 변조
### 전송 코드
