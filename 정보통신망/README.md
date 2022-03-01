# 정보통신망

### 목차
- [1강. 컴퓨터 통신망의 소개](#1강-컴퓨터-통신망의-소개)
  - [컴퓨터와 통신](#컴퓨터와-통신)
  - [데이터 통신 시스템](#데이터-통신-시스템)
  - [통신 프로토콜](#통신-프로토콜)

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
### 통신 프로토콜
