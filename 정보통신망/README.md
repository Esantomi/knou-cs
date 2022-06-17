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
