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
- [11강. TCP/IP(III)](#11강-TCPIPIII)
  - [주소 변환](#주소-변환)
  - [ICMP](#ICMP)
  - [IGMP](#IGMP)
  - [DHCP](#DHCP)
- [12강. 근거리 통신망(I)](#12강-근거리-통신망I)
  - [근거리 통신망 개요](#근거리-통신망-개요)
  - [근거리 통신망의 특성 및 효과](#근거리-통신망의-특성-및-효과)
  - [근거리 통신망의 분류](#근거리-통신망의-분류)
- [13강. 근거리 통신망(II)](#13강-근거리-통신망II)
  - [LAN 참조 모델](#LAN-참조-모델)
  - [무선 LAN](#무선-LAN)
  - [고속 LAN](#고속-LAN)
- [14강. 네트워크 보안(I)](#14강-네트워크-보안I)
  - [네트워크 보안 개요](#네트워크-보안-개요)
  - [보안 위협 유형](#보안-위협-유형)
- [15강. 네트워크 보안(II)](#15강-네트워크-보안II)
  - [암호 기법](#암호-기법)
  - [디지털 서명](#디지털-서명)
  - [웹 보안 프로토콜](#웹-보안-프로토콜)
  - [방화벽과 프락시 서버](#방화벽과-프락시-서버)

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
- **통신(communication)**
  - 한 점으로부터 다른 점으로 어떤 정보(data 또는 message)를 전달
  - 통신의 3대 요소  
    ![image](https://user-images.githubusercontent.com/61646760/156584998-129939fe-c8c1-405e-a251-0e16cd695523.png)
    - 정보원
    - 전달매체
    - 수신체
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
- **아날로그 변조(Analog Modulation)**
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
- **디지털 변조(Digital Modulation)**
  - **진폭 편이 변조(Amplitude Shift Keying, ASK)**
    - 변조 신호를 가지고 반송파의 진폭을 변화시키는 변조 방식  
      ![image](https://user-images.githubusercontent.com/61646760/156890092-4525a52d-d8a7-44c1-be0d-a421727abf01.png)
  - **주파수 편이 변조(Frequency Shift Keying, FSK)**
    - 변조 신호를 가지고 반송파의 주파수를 변화시키는 변조 방식  
      ![image](https://user-images.githubusercontent.com/61646760/156890102-ad193329-1aa5-4052-8ba6-9206b28430c6.png)
  - **위상 편이 변조(Phase Shift Keying, PSK)**
    - 변조 신호를 가지고 반송파의 위상을 변화시키는 변조 방식  
      ![image](https://user-images.githubusercontent.com/61646760/156890112-9dd49e45-4ab3-4c26-97e5-be0c88889b3e.png)
      - 0에서 1로 바뀔 때와 1에서 0으로 바뀔 때, x축을 기점으로 방향이 전환됨
  - 디지털 변조 한눈에 보기  
    ![image](https://user-images.githubusercontent.com/61646760/156890360-41745faa-57ed-446d-a3c9-6ad410de502d.png)
- 정보의 디지털화
  - **펄스(pulse)**
    - 매우 짧은 시간 동안 진행되는 네모꼴의 전자기 파형
    - 펄스의 3대 요소  
      ![image](https://user-images.githubusercontent.com/61646760/156890489-c43a9234-b66b-4f31-bdb6-ffac33e6dc11.png)
      - 진폭(amplitude) : 전자기 파형의 높이
      - 위치(position) : 기준 시각부터 펄스 발생 시각까지의 시간
      - 폭(width) : 전자기 파형이 어느 정도 유지되었는지
  - **펄스 코드 변조(PCM: Pulse Code Modulation)**
    - 아날로그 신호를 디지털 신호로 바꾸는 과정
      - 표본화(sampling) 과정
      - 양자화(quantization) 과정
      - 부호화(encoding) 과정
    - `예) PCM 부호화 과정`  
      ![image](https://user-images.githubusercontent.com/61646760/156890757-aaca882a-be19-4428-b4b8-086787ce0737.png)
        - PAM(Pulse Amplitude Modulation) 펄스 : 원신호를 표본화(sampling)한 것
        - PCM(Pulse Code Modulation) 펄스 : PAM 펄스를 양자화(quantization)한 것
        - PCM 결과 : PCM 펄스를 부호화(encoding)한 것
### 전송 코드
- **코드(code)**
  - 암호, 부호, 규칙, 법규
    - '약속'이라는 공통적인 의미 요소를 지님
  - 코드 종류  
    ![image](https://user-images.githubusercontent.com/61646760/159013864-93db82be-0a4a-47ea-8711-330005ae385f.png)
- **Baudot 코드**
  - Murray code
    - CCITT Alphabet No.2
    - International Alphabet No.2
  - Telex code
    - 텔렉스 망에서 사용
  - 5bit ➔ 32개의 문자 표현 가능
- **ASCII 코드**
  - American Standard Code for Information Interchange
    - CCITT Alphabet No.5
    - International Alphabet No.5
  - ISO Seven-Bit Coded Character Set
    - for Information Processing Interchange
  - 7bit ➔ 128개의 문자 표현 가능
    - 정보를 표현하기 위해 7비트를 사용하고, 데이터 전송의 오류를 검사하기 위해 (패리티 검사를 위해) 별도의 1비트를 사용
    - 즉, ASCII 코드는 7비트의 정보와 패리티 검사를 위한 1비트로 구성된 8비트 코드
  - `예) ASCII code table`  
    ![image](https://user-images.githubusercontent.com/61646760/159002493-b4629757-8b44-48d1-b609-5ac4213a5e12.png)
    - `H`는 1001000에 해당
    - `SYN` 패킷은 흐름 제어, 오류 제어를 위한 패킷으로, 0010110에 해당
      - 1은 3비트로 001, 06은 4비트로 0110에 해당
    - ASCII 문자 세트에서 32개의 제어 문자가 있으며, 이들은 전송제어, 포맷제어, 장치제어, 정보분리의 기능을 갖고 있음
  - **패리티 비트(parity bit)**
    - 전송 오류 제어를 위한 비트
      - 정보의 전달 과정에서 오류가 생겼는지를 검사하기 위해 추가된 비트 (ASCII 7bit + parity 1bit)
      - 문자열 내 1비트의 모든 숫자가 짝수 또는 홀수인지를 보증하기 위해 전송하고자 하는 데이터의 각 문자에 1비트를 더하여 전송하는 방법
    - 두 종류의 패리티
      - **짝수(even) 패리티** : 전체 비트에서 1의 개수가 짝수가 되도록 패리티 비트를 정하는 것인데, 이를테면 데이터 비트에서 1의 개수가 홀수이면 패리티 비트를 1로 정함
      - **홀수(odd) 패리티** : 전체 비트에서 1의 개수가 홀수가 되도록 패리티 비트를 정하는 방법
    - 패리티 검사  
      ![image](https://user-images.githubusercontent.com/61646760/159006817-f9ea01e6-98ed-49d8-8bd8-c34bd7770a33.png)
      - 1개의 비트가 잘못된 경우
        - 홀수 패리티까지, 1의 개수가 5개
        - 전송 오류가 발생해서 4번째 칸의 1이 0으로 바뀜
          - 1의 개수가 4개
          - 홀수 패리티인데 4개면 전송 오류가 발생했음을 알 수 있음
      - 2개의 비트가 잘못된 경우
        - 홀수 패리티까지, 1의 개수가 5개
        - 전송 오류가 발생해서 4번째 칸, 5번째 칸의 1이 0으로 바뀜
          - 1의 개수가 3개
          - 홀수 패리티이니 전송 오류 식별 불가
        - 짝수 개의 비트가 잘못된 경우 패리티 비트로 오류 검출이 불가함
          - 이후 오류 제어 부분에서 공부
- **BCD 코드**
  - Binary Coded Decimal
    - 2진 코드로 만들어진 10진 숫자
  - 컴퓨터 내부 코드
  - 10진 숫자의 표현
    - `0000` : 1
    - `0001` : 2
    - `1000` : 8
    - `1001` : 9
    - `1010`~`1111` : 미사용
      - `예) 5는 0101, 9는 1001, 159는 0001 0101 1001`
        - 159의 실제 2진수 표현은 `10011111`
        - 즉, 2진 숫자 같지만 10진 숫자처럼 사용한 것
- **EBCDIC 코드**
  - Extended BCD Interchange Code
  - 8bit ➔ 256개의 문자 표현 가능
  - IBM 컴퓨터 내부 데이터 전송용
- **유니코드**
  - 만국 공통 국제 문자 코드
    - 26개 언어의 문자 및 특수 기호
  - 데이터, 프로그램, 시스템의 호환성과 확장성
  - 2byte (16bit) ➔ 2<sup>16</sup>개(65536개)의 문자 표현 가능  
  - IBM, Microsoft, Lotus, Sun Microsystems
  - ISO/IEC Universal Multi-Octet Coded Character Set
## 11강. TCP/IP(III)
### 주소 변환
- **ARP**(Address Resolution Protocol) : IP 주소를 물리 주소로 매핑해 주는 프로토콜
- **RARP**(Reverse Address Resolution Protocol) : 물리 주소로 호스트 자신의 IP 주소를 찾는 프로토콜
### ICMP
- **ICMP**(Internet Control Message Protocol)
  - 인터넷 계층 프로토콜
  - IP는 비연결성, 비신뢰성 전송 서비스 (실패 가능성 있음)
  - IP 데이터그램 전송의 오류가 발생할 경우 오류 메시지 또는 제어 메시지를 제공해 주는 프로토콜
    - 즉, 전송 오류 제어
  - ICMP 메시지 유형
    - 오류 보고 메시지(error reporting)
    - 질의 메시지(simple query)
### IGMP
- **IGMP**(Internet Group Management Protocol)
  - 인터넷에서 multicast 서비스를 위해 사용되는 프로토콜
  - IP 호스트가 어떤 멀티캐스트 그룹에 참가하고 있는지를 멀티캐스트 라우터에 통보하는 프로토콜
    - Multicast : 하나의 그룹에 속한 호스트들에게 메시지 전송 (1-to-many)
  - 클래스 D 주소 사용
### DHCP
#### IP 주소 관리
- IP 주소 (32 비트. 150.183.135.215 등으로 표시)
  - 기억하기 어려움 ➔ 주소 관리 방법의 필요
    - Host Table
    - DNS (Domain Name System)
    - BOOTP (Bootstrap Protocol)
    - DHCP (Dynamic Host Configuration Protocol)
- **Host Table**
  - 모든 IP 주소와 이와 mapping되는 호스트 이름으로 구성된 테이블
- **DNS** (Domain Name System)
  - 계층적 구조 및 분산 관리 특성
    - `예) 도메인 이름 : knou.ac.kr`
- **BOOTP** (Bootstrap Protocol)
  - 기존의 방식은 IP 주소를 수작업으로 할당 (정적 할당)
  - BOOTP는 동적으로 IP 주소를 할당
  - 디스크가 없는 호스트(X 터미널)에 대해 주소 및 설정 정보를 자동적으로 할당하고 관리하는 프로토콜
#### DHCP 메시지 형식
- **DHCP**(Dynamic Host Configuration Protocol)
  - 응용 계층 프로토콜
  - BOOTP에서 발전된 동적 주소 할당 프로토콜로서, IP 주소 재사용이 가능함
    - 동적 주소 할당 프로토콜
      - IP 주소 pool에서 사용 가능한 IP 주소를 선택하여 원하는 호스트에게 일정 기간 임대해 줌
    - **IP 주소 자동 할당**
  - DHCP 메시지 형식은 BOOTP와 동일함
## 12강. 근거리 통신망(I)
### 근거리 통신망 개요
- **LAN**(Local Area Network)
  - 근거리 통신망
  - IEEE 컴퓨터 표준위원회
    - “다수의 독립된 컴퓨터 기기들의 상호 통신이 가능하도록 해 주는 데이터 통신 시스템”
  - William Stallings
    - “좁은 지역 내에서 다양한 통신기기의 상호 연결을 가능하게 하는 네트워크”
### 근거리 통신망의 특성 및 효과
- 특성
  - 단일기관의 소유이다
  - 광대역 전송매체의 사용으로 고속통신이 가능하다
  - 라우팅이 필요 없다
  - 확장성과 재배치성이 좋다
### 근거리 통신망의 분류
#### 위상에 의한 분류
#### 전송 매체에 의한 분류
#### 전송 방식에 의한 분류
#### 매체 접근 방법에 의한 분류
## 13강. 근거리 통신망(II)
### LAN 참조 모델
- OSI 참조 모델과 LAN 참조 모델  
  ![image](https://user-images.githubusercontent.com/61646760/174313219-42f72112-046f-491d-90a9-f484770868b0.png)
  - 물리 계층
    - **물리 매체(cable)**
      - 케이블을 통해 전기적 신호를 전달하는 역할을 수행
      - twisted pair cable, coaxial cable, optical fiber, electric wave
    - **매체 접근 장치(MAU)**
      - signaling, encoding 기능과 매체를 다루는 기능을 수행
  - 데이터링크 계층
    - **매체 접근 제어(MAC)**
      - MAU와 LLC 사이의 인터페이스
      - 데이터 전송 매체의 사용권을 모든 노드에게 균등하게 제공하는 기능을 수행
    - **논리 링크 제어(LLC)**
      - MAC에 의해 확보된 데이터 전송 권한을 이용해 흐름 제어, 오류 제어, 순서화 및 연결 관리 등의 기능 수행
  - 논리 링크 제어(LLC) 계층
    - 중간 노드 없이 인접 두 노드 사이의 데이터 전송
    - OSI 참조 모델의 데이터링크 계층
    - 차이점
      - LLC는 다중 접근을 지원함
      - 매체 제어는 MAC에서 해결하므로 LLC는 관여하지 않음
      - 데이터링크 계층 기능의 일부만을 수행함
- LAN 관련 표준
  - IEEE 802 프로토콜  
    ![image](https://user-images.githubusercontent.com/61646760/174318294-ee660a85-e08a-48f6-b817-fd6dc784748f.png)
    - IEEE 802는 근거리 통신망(LAN)과 도시권 통신망(MAN)을 관할하는 전기 전자 기술자 협회(IEEE) 표준 규칙들의 계열을 말한다.
### 무선 LAN
- **무선 LAN**
  - 적외선이나 전파를 사용하여 노드들을 연결한 LAN
- 무선 LAN의 통신 방식
  - **애드혹(Ad hoc) 방식**  
    ![image](https://user-images.githubusercontent.com/61646760/174315795-f202d813-2262-4789-acec-90e422dbb62a.png)
    - 무선 LAN의 전파가 도달하는 범위 안에서 무선 LAN 카드를 장착한 노드들끼리 직접 통신하는 방식
    - <strong>IBSS(Independent Basic Service Set)</strong>라는 독립적 단위로 단독 네트워크를 구성함
    - 하나의 IBSS 내의 노드들끼리는 서로 통신이 가능하지만 다른 IBSS와는 데이터를 송수신할 수 없음
  - **인프라스트럭처(infrastructure) 방식**  
    ![image](https://user-images.githubusercontent.com/61646760/174316420-38f8e3f3-5436-407f-bdbb-20a58ec534ab.png)
    - 무선 LAN 카드를 장착한 노드들이 허브나 라우터와 연결된 AP(Access Point)를 통해 서로 통신하는 방식
    - **BSS(Basic Service Set)**
      - 하나의 AP로 구성되는 무선 LAN
    - **ESS(Extended Service Set)**
      - 서로 연결된 BSS들의 집합을 하나의 BSS처럼 보이도록 만든 무선 LAN
### 고속 LAN
- **고속 LAN**
  - 기존의 LAN 프로토콜을 이용하면서 100Mbps 이상의 속도를 지원하는 LAN
    - Fast Ethernet, Gigabit Ethernet, FDDI
- **고속 이더넷**
  - 기존의 이더넷 기술(10Mbps)을 발전시켜 100Mbps를 지원하는 “fast Ethernet”
  - 기존 이더넷과 거의 동일하나, 전송 가능한 케이블의 최대 길이를 줄임으로써 속도를 향상
  - 매체 접근 방식 : CSMA/CD (IEEE 802.3u)
- **기가비트 이더넷**
  - 기존의 Ethernet과 최대한 호환성 유지하며 1Gbps 속도를 지원하는 Ethernet
- **FDDI**(Fiber Distributed Data Interface)  
  ![image](https://user-images.githubusercontent.com/61646760/174317630-ae67802e-4cda-4b1a-a8c2-033ed37bcb9e.png)
  - 100Mbps 전송 속도 제공
  - ANSI 표준 ➔ ISO 표준
  - 광섬유 케이블을 이용하는 이중 링 구조의 LAN
  - 2개의 링이 token passing 방식으로 운용
    - 정해진 규칙에 따라 1개의 링을 선택하여 사용
    - multi token 방식 이용
    - 전송 방향이 서로 반대
## 14강. 네트워크 보안(I)
### 네트워크 보안 개요
#### 보안의 필요성
- 보안의 3가지 목표 : 보안 원칙
  - **기밀성(confidentiality)** : 허가되지 않은 사람에게 정보가 노출되지 않는 것을 보장
  - **무결성(integrity)** : 허가되지 않은 사람에 의해 정보가 변경되지 않는 것을 보장
  - **가용성(availability)** : 허가된 사람에게 부당한 지체 없이 정보가 접근되고 사용할 수 있도록 하는 것을 보장
#### 보안의 종류
- **시스템 보안**
  - 권한이 없는 사람에 의한 파일 및 장치 등의 사용을 제한함으로써 시스템을 보호하는 방법
  - 시스템 보안 방법
    - 접근 통제 : 권한이 있는 사용자들에게 접근을 제한
    - 감시 통제 : 시스템에서의 활동을 감시
- **네트워크 보안**
  - 내부 네트워크가 인터넷과 같은 외부의 네트워크와 연결되면서 내부 조직의 네트워크 보안이 점점 중요해지고 있음
    - `예) 인터넷 뱅킹, 전자 상거래, 각종 증명서 발급 (공인인증서 이용)`
  - 권한이 없는 사람의 접근이나 우연 또는 의도적인 방해나 파괴로부터 네트워크를 보호하기 위한 방법
  - 하드웨어나 소프트웨어, 인위적인 보안 조치를 총칭
#### 네트워크 보안의 요구 사항
1. 실체 인증 : 통신에 참여한 실체에 대한 진위 검증
2. 데이터 무결성 : 데이터가 파괴되거나 변경되지 않도록 보호
3. 데이터 보안성 : 정보의 비밀 보장, 합법적 사용자의 접근 보호
4. 데이터 인증 : 데이터가 신뢰할 수 있는 발신처에서 전송된 것인지 확인
5. 부인 방지 : 데이터의 수신이나 전송 사실에 대한 확인
### 보안 위협 유형
- 사람 : 제3자, 통신 당사자(송신자, 수신자)
- 악성 프로그램 : 바이러스, 웜, 트로이 목마
- 기타 : phishing, pharming
#### 제3자에 의한 불법적인 공격 유형
1. **가로채기(interception)**
    - 공격자가 전송되고 있는 정보를 몰래 열람, 또는 도청하는 행위
      - `예) 네트워크상에서 개인 정보 데이터를 부정한 방법으로 복사하거나 도청하는 행위 등`
    - 정보의 기밀성(confidentiality) 보장을 위협
2. **변조(modification)**
    - 공격자가 시스템에 접근하여 데이터를 조작하여 원래의 데이터를 다른 내용으로 바꾸는 행위
      - `예) 송수신자가 알아채지 못하도록 전송 중인 메일 내용을 변경하거나 데이터 파일 내의 값들을 변경하는 것`
    - 정보의 무결성(integrity) 보장을 위협
3. **위조(fabrication)**
    - 공격자가 거짓 정보나 잘못된 정보를 삽입하여 수신자에게 전송하고 수신자가 정당한 송신자로부터 정보를 수신한 것처럼 착각하도록 만들어 이를 통해 이득을 보려는 행위
      - `예) 위조된 메시지를 수신자에게 전송하는 행위 등`
    - 정보의 무결성(integrity) 보장을 위협
4. **방해(interruption)**
    - 송신자와 수신자 간의 정보 송수신이 원활하게 이루어지지 못하도록 시스템의 일부를 파괴하거나 사용할 수 없게 하는 행위
      - `예) 통신 회선의 절단이나 파일 관리 시스템의 파손 등`
    - 정보의 가용성(availability) 보장을 위협
5. **서비스거부(Denial of Service)**
    - 공격자가 처리 용량을 넘는 데이터를 전송하여 과도한 부하를 일으켜 시스템을 마비시킴으로써 정당한 이용자가 시스템을 사용하지 못하게 만드는 행위
      - `예) 메일 서버 시스템에 엄청난 양의 스팸 메일을 보내 시스템의 원활한 서비스를 방해하는 행위 등`
    - **분산 서비스 거부(Distributed DoS)**
    - 정보의 가용성(availability) 보장을 위협
#### 통신 당사자 간의 보안 위협
- 부정(사기; fraud)
#### 악성 프로그램의 감염 유형
- **컴퓨터 바이러스(computer virus)**
  - 컴퓨터에서 실행되는 일종의 명령어들의 집합으로서 컴퓨터 프로그램이나 데이터 파일을 감염시킴
  - 감염은 정상 파일에 바이러스 코드를 붙이거나 본래 목적 이외의 작업을 처리하며 동시에 자신을 복제시킴
  - 증상
    - 컴퓨터 부팅 시간이 오래 걸리거나 부팅이 안 되는 증상
    - 프로그램이 오동작하거나 동작되지 않는 증상
    - 저장된 데이터가 변조되거나 삭제되는 증상 등
- **웜(worm)**
  - 네트워크를 통해서 자신을 복제, 전파할 수 있는 프로그램
  - 감염시키지 않고도 복제할 수 있음
  - 감염 경로 : email, P2P, 메신저 등
  - 주요 피해 유형
    - DDoS
    - 침입자가 시스템에 쉽게 접근할 수 있는 통로 제공
- **트로이목마(Trojan horse)**
  - 컴퓨터 사용자의 정보를 빼내가기 위한 목적으로 제작된 악성 프로그램
  - 악성 코드를 유틸리티 프로그램에 내장하여 배포하거나 그 자체를 유틸리티 프로그램으로 위장하여 배포함
  - 자기 복제 능력 없음
#### 기타 유형
- **피싱(Phishing)**
  - Private information + Fishing
  - 인터넷에서 송신자를 알리지 않는 스팸 메일을 이용하여 수신자의 개인 정보를 빼낸 뒤 이를 불법적으로 이용하는 범죄
  - `예) 거짓 이메일을 통해, 가짜 웹 사이트로 유인하여 신상 정보를 요구, 이벤트, 설문조사 등`
- **파밍(Pharming)**
  - Phishing + Farming
  - 정당한 웹 사이트의 도메인을 탈취하거나 DNS 이름을 속여 미리 정해 놓은 웹 사이트로 data traffic을 유인한 뒤, 개인 정보를 빼낸 뒤 이를 불법적으로 이용하는 범죄
  - 피싱의 한 유형이지만 더 위협적임
## 15강. 네트워크 보안(II)
### 암호 기법
- 암호 기법의 개요  
  ![image](https://user-images.githubusercontent.com/61646760/174325502-926b0cac-7429-47f6-abc1-8c48460fb09e.png)
  - **암호화(encryption)**
    - 누구나 읽을 수 있는 평문(plaintext)을 제3자가 읽을 수 없는 형태인 암호문(ciphertext)으로 변환하는 과정
  - **복호화(decryption)**
    - 암호문을 평문으로 변환하는 과정
  - **키(key)**
    - 암호화 키, 복호화 키
- 암호화 기술 분류
  - 동작 형태 : 대치 암호, 전치 암호, 혼합 암호, 대수화 암호
  - 평문의 처리 방법 : 스트림 암호화, 블록 암호화
  - 암호화 키 : 대칭 키 암호화, 공개 키 암호화
#### 동작 형태
  - **대치 암호 (치환 암호; substitution cipher)**
    - 메시지의 각 글자를 다른 글자로 대치하는 방식
  - **전치 암호 (전위 암호; transposition cipher)**
    - 평문의 글자를 재배열하는 방식 (문자의 위치를 바꿔 암호문을 작성)
  - **혼합 압호(product cipher)**
    - 대치와 전치 두 방법 모두를 사용하는 방식
  - **대수적 암호(algebraic cipher)**
    - 각 글자를 숫자로 바꾸어 수학적으로 처리하는 방식
#### 평문 처리 방법
- **스트림 암호화(stream cipher [state cipher] encryption)**
  - 평문과 같은 길이의 키 스트림을 생성하여 평문과 키를 비트 단위로 합하여 암호문을 얻는 방법
  - 평문은 한 번에 한 비트씩, random하게 생성되는 키 스트림과 XOR 연산으로 합해져서 전송됨
- **블록 암호화(block cipher [state cipher] encryption)**
  - 평문을 일정한 길이의 단위(block)로 나눈 뒤, 각 block 단위로 암호화 과정을 수행하여 암호문을 얻는 방법
- 비교
  - 스트림 암호화 방식 : 비트 단위의 암호화
  - 블록 암호화 방식 : 블록 단위의 암호화
#### 암호화 키
- **대칭 키 암호화(symmetric key encryption)**  
  ![image](https://user-images.githubusercontent.com/61646760/174327600-5915d07d-142b-44ef-b929-95a38ff91a33.png)
  - 암호화 키 = 복호화 키
  - 유사어 : **공통 키(common key) 암호화**, 비밀 키(secret key) 암호화, 관용 암호화(conventional encryption)
  - **DES(Data Encryption Standard)**
    - 대칭 키를 사용하는 블록 암호화 방식
    - IBM에서 개발한 LUCIFER의 확장된 형태로 제안되어 1976년 NBS에서 미국 정부 표준 암호 방법으로 제정
  - **AES(Advanced Encryption Standard)**
    - 2001년 NIST에서 미국 정부 표준 암호 방법으로 제정
- **공개 키 암호화 방식(public key encryption)**  
  ![image](https://user-images.githubusercontent.com/61646760/174328479-d185e965-50de-46a3-881f-0fb47c96d3dc.png)
  - 암호화 키 = 공개 키(public key) / 복호화 키 = 개인 키(private key)
  - 유사어 : **비대칭 키(asymmetric key) 암호화**
  - **RSA 암호화 알고리즘**
    - 1978년 MIT의 3명의 수학자(Rivest, Shamir, Adleman)가 개발
    - 가장 대중화된 공개 키 암호화 방식
    - 2개의 큰 소수 p, q를 구하고, 두 소수의 곱 n을 구해 사용하는데, 이 암호화 방식의 안전도는 n의 소인수 분해 난이도에 종속됨
#### 키 관리
- 공개 키 기반 구조
  - Public Key Infrastructure (PKI)
    - 공개 키 인증서를 발급하고 사용할 수 있는 인증서 관리 구조
  - 인증 기관 (Certificate Authority; CA)
    - 일반인에게 개인 키와 공개 키를 부여하고, 인증서를 통해 상대방의 공개 키를 제공하는 서비스 기관
### 디지털 서명
- **디지털서명(digital signature)**
  - 공개 키 암호화 방식에서의 메시지 암호화는 개인 키를 이용한 메시지 작성자만이 할 수 있으므로 이를 이용하여 메시지의 작성자 본인을 알리는 서명을 작성함
  - 서명 알고리즘 및 증명 알고리즘  
    ![image](https://user-images.githubusercontent.com/61646760/174329959-dadbec58-824b-4c9a-be8c-5e48a4834d06.png)
  - 디지털 서명을 포함하는 메시지 전송  
    ![image](https://user-images.githubusercontent.com/61646760/174329865-74cfd783-bcce-4ac1-9de0-d5d8829db7fc.png)
- 디지털 서명의 유효성을 위한 5가지 조건
  - **서명자 인증(user authentication)** : 디지털 서명의 서명자를 불특정한 다수의 사람들이 검증할 수 있어야 함
  - **부인 불가(non-repudiation)** : 서명자는 서명 이후 서명 사실을 부인할 수 없어야 함
  - **변경 불가(unalterable)** : 서명한 문서의 내용은 변경할 수 없어야 함
  - **재사용 불가(not reusable)** : 어느 한 전자 문서의 디지털 서명을 다른 전자 문서의 디지털 서명으로 사용할 수 없어야 함
  - **위조 불가(unforgeable)** : 적법적인 서명자만이 디지털 서명을 할 수 있어야 함
### 웹 보안 프로토콜
### 방화벽과 프락시 서버
