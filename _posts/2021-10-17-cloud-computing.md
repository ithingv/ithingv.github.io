---
layout: single
title:  "Infra Basics [Week 1]: Cloud Computing"
---

#### Contents
- 클라우드 컴퓨팅이란?
- 클라우드 서비스
    - On premise
    - IaaS, PaaS, SaaS
- 클라우드 유형
    - public cloud
    - private cloud
    - hybrid cloud
- 데이터 스토리지 서버
    - DAS
    - NAS
    - SAN


## 클라우드 컴퓨팅이란?

**클라우드 컴퓨팅**은 사용자의 직접적인 활발한 관리 없이 특히, 데이터 스토리지(클라우드 스토리지)와 컴퓨팅 파워와 같은 컴퓨터 시스템 리소스를 필요 시 바로 제공(**on-demand availability**)하는 것을 말한다. 일반적으로는 인터넷 기반 컴퓨팅의 일종으로 정보를 자신의 컴퓨터가 아닌 클라우드에 연결된 다른 컴퓨터로 처리하는 기술을 의미한다. 공유 컴퓨터 처리 자원과 데이터를 컴퓨터와 다른 장치들에 요청 시 제공해준다. 구성 가능한 컴퓨팅 자원(예: 컴퓨터 네트워크, 데이터 베이스, 서버, 스토리지, 애플리케이션, 서비스, 인텔리전스)에 대해 어디서나 접근할 수 있는, 주문형 접근(on-demand availability of computer system resources)을 가능케하는 모델이며 최소한의 관리 노력으로 빠르게 예비 및 릴리스를 가능케 한다. 클라우드 컴퓨팅과 스토리지 솔루션들은 사용자와 기업들에게 개인 소유나 타사 데이터 센터의 데이터를 저장, 가공하는 다양한 기능을 제공하며 도시를 거쳐 전 세계로까지 위치해 있을 수 있다. 클라우드 컴퓨팅은 전기망을 통한 전력망과 비슷한 일관성 및 규모의 경제를 달성하기 위해 자원의 공유에 의존한다.

[참고: 위키피디아](https://ko.wikipedia.org/wiki/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C_%EC%BB%B4%ED%93%A8%ED%8C%85)

## 클라우드 서비스

<img src='/assets/images/cloud/week1_1.png'>

### On premise
온프레미스는 클라우드 산업이 보편화 되기 이전의 전통적인 서버 구축 방법으로 IT 시스템 운영에 필요한 서버, 네트워크, 보안 등의  자원들을 직접 설정하고 관리하는 방식이다. 이러한 IT 자원을 올바르게 관리하기 위해서는 관련 전문가가 필요하기 때문에 클라우드 방식에 비해 많은 비용이 들고 또한 자원의 수요 증감에 대해 탄력적으로 대응하지 못한다는 단점이 있다. 이로 인해 많은 기업들이 온프레미스 환경에서 클라우드 도입을 고려하지만 보안적인 이유로 비즈니스에 중요하고 보안이 필요한 서비스와 데이터는 온프레미스 환경에서, 덜 중요한 것은 퍼블릭 클라우드 환경을 사용하는 하이브리드 IT 인프라가 대세를 이루고 있다.

### IaaS
- Infrastructure as a Service
- IT의 기본 자원만 제공
- Server, Storage, Network
- 새로 컴퓨터 하나 구매하는 개념 (os 미설치 컴퓨터가 배송와서 os 설치하고 동작시킴)

### PaaS
- Platform as a Service 
- IaaS에 OS, Middleware, Runtime 추가
- Middleware: RDBMS 등
- Runtime: JDK, Python 등 프로그램이 작동하는 환경
- 일반적으로 개발자를 대상으로 함
- 코드 개발만 해서 올리면 고객에게 서비스할 수 있는 상태
- AWS Elastic Beantalk, Google App Engine

### SaaS
- Software as a Service
- 모든 기능이 동작하는 SW를 제공
- 네이버 클라우드, 구글 드라이브, 구글 캘린더, 네이버 메일, Office364, Dropbox 등

## 클라우드 유형

### Public Cloud
- 외부의 어딘가 클라우드가 존재하고 불특정 다수의 기관이 클라우드를 사용할 수 있는 형태
- Cloud 서비스를 필요로 하는 사용자 누구든지 사용 가능
- 누구나 사용한 만큼 비용만 지불하면 됨
- Cloud 사업자가 IT 자원을 서비스로 제공

<div>
<img src='/assets/images/cloud/week1_2.PNG' style="margin-top:10px">
<span style="display: inline-block; width: 95%; text-align: center;">전 세계적으로 널리 사용되는 제공업체들은 다음과 같다.
</span>
</div>

### Private Cloud
- 기업 및 기관 내부에서만 사용 가능한 Cloud Computing 환경을 구축
- 해당 기업/기관에 속하지 않은 사람은 사용 불가
- 기업 자체적으로 구축하며 구축 난이도 높지만, 보안/법적 규제 등의 이유로 사용
- 특정 기관, 내부에서만 사용할 수 있는 cloud 형태(정부기관, 관공서 등)

### Hybrid Cloud
- Public, private cloud가 조합되어 사용하는 상태
- 보안이 중요한 시스템은 Private cloud에 , 그 외 시스템은 Public cloud를 사용가능
- Private Cloud를 주로 사용하되 예상치 못한 수준의 트래픽이 몰리는 경우 Public Cloud로 확장
- 최근 기업들이 가장 관심 갖는 형태


## 데이터 스토리지 서버

### DAS

<img src='/assets/images/cloud/week1_3.PNG' style="margin-bottom:10px">

**DAS(Direct Attached Storage)** 는 내부 케이블을 통해 시스템(예: PC 또는 서버)에 직접 연결되는 디지털 스토리지이다. DAS 시스템은 HBA(호스트 버스 어댑터)를 통해 시스템에 직접 연결된 단일 인클로저에 여러 개의 하드 디스크 드라이브를 보유한다. 이러한 디스크 드라이브 사이에는 네트워크 장치(예: 스위치, 허브, 라우터 또는 네트워크 케이블)가 없다. 개인 PC 사용자의 경우 시스템의 하드 디스크는 DAS의 표준 형태이다. 그러나 기업이나 기업에서는 한 서버에 있는 별도의 디스크 드라이브와 해당 서버 외부에 있는 드라이브를 직접 연결하거나 SCSI(Small Computer System Interface), SATA(Serial Advanced Technology Attachment) 또는 SAS(Serial Attached SCSI)를 통해 연결한다.). DAS의 또 다른 한계는 데이터를 다른 서버나 사용자와 공유할 수 없다.

#### Why DAS?
- DAS is good for local storage provisioning
- Fast & Simple Deployment
- Ideal for small environments
- Costs Lesser
- No complexity

#### Why NOT DAS?
- Single Point of Failure
- Sharing
- Scalability
- Management
- Backups


### NAN


<img src='/assets/images/cloud/week1_4.PNG' style="margin-bottom:10px">


**네트워크 연결 스토리지(Network-Attached Storage)** 는 컴퓨터 네트워크에 연결된 파일 수준의 컴퓨터 데이터 스토리지 서버이다. 중앙 위치에서 권한이 부여된 여러 네트워크 사용자 및 기타 클라이언트 그룹에 데이터에 대한 액세스 및 저장을 제공한다. 이러한 시스템은 일반적으로 엔지니어링 소프트웨어 빌드, 데이터 로깅, 이메일 시스템, 비디오 녹화 및 편집, 비즈니스 분석, 재무 기록, 유전체학 데이터 세트 등을 포함한 공유 애플리케이션을 지원하는 데 사용된다.

파일 시스템은 종종 논리적 중복 스토리지 컨테이너로 배열되는 하나 이상의 스토리지 드라이브에 포함된다. NAS 크기는 속도, 규모 및 예산 요구 사항에 따라 다르다. 따라서 단일 데스크탑 시스템에서 멀티 페타바이트 규모 확장 시스템에 이르기까지 확장될 수 있다. NAS는 내부 네트워크에 노출된 하나 이상의 파일 액세스 프로토콜을 사용한다. 그 다음 NFS(네트워크 파일 시스템) 또는 SMB(서버 메시지 블록)와 같은 프로토콜이나 클라이언트가 NAS에 연결할 수 있도록 하는 독점적인 고성능 프로토콜에 의해 제공된다. TCP/IP 장치 및 기타 컴퓨터와 마찬가지로 NAS는 네트워크 노드 역할을 하고 IP 주소를 유지하며 다른 네트워크 장치와 효과적으로 통신할 수 있다.

#### Why NAS?
- Storage can be shared
- Plug into existing Ethernet
- Co - Exist with Windows & UNIX
- High Availability
- Scalability
- Secure

#### Why NOT NAS?
- Single Point of Failure
- Network Bandwidth
- NAS Filer Capacity
  
### SAN

<img src='/assets/images/cloud/week1_5.PNG' style="margin-bottom:10px">

**스토리지 영역 네트워크(Storage Area Network)** 은 파일 시스템을 제어해야 하는 호스트에 대해 블록 수준 액세스를 제공한다. SAN이 개발되기 전에는 서버가 내부 디스크를 로컬 파일 시스템을 활용하는 블록 장치로 사용됐지만 스토리지는 서버 내부에서만 확장될 수 있었다. SAN은 이 문제를 피하고 네트워크를 통해 블록 장치를 제공합니다. NAS와 달리 SAN은 서버의 성능을 유지하기 위해 복잡한 기술이 필요한 네트워크 스토리지 시스템이다. 구성 요소에는 게이트웨이 장치, 전용 스위치(또는 공유 네트워크의 VLAN), 테이프 백업 장치, 컨트롤러 노드 및 디스크 선반이 포함될 수 있다. SAN 시스템은 SCSI, iSCSI 및 파이버 채널과 같은 프로토콜을 사용한다.

#### Why SAN?
- Dedicated High Speed Network
- Block Data Access
- Centralized Data Management
- High Scalability
- Data Security


#### References
   - [DAS](https://www.youtube.com/watch?v=HCZp236v690)
   - [NAS](https://www.youtube.com/watch?v=80iWe7j28C0&t=1s)
   - [SAN](https://www.youtube.com/watch?v=oWEqKw-QxwQ)
  - [Cloud Storage Types](https://www.youtube.com/watch?v=CczKEbElR9U)
  - [NAS VS. SAN VS. DAS – ADVANTAGES & DISADVANTAGES](https://www.weka.io/learn/nas-vs-san-vs-das-storage-comparison/)