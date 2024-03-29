# 🖥 IT[클라우드, 쿠버네티스] 단어정리

| 한국어 | 영어 | 정의 |
| ------- | :---| :--- |
|컴포넌트          |Component       |프로그래밍에 있어 재사용이 가능한 각각의 독립된 모듈을 뜻함 </br> ex) 컴퓨터를 구성하는 cpu, gpu, 메인보드, ssd등 독립된 것을 예시로 들 수 있다.|
|데브옵스          |DevOps          |Development(Dev)와 IT operations(Ops)의 합성어로 개발자와 운영자와의 소통, 형업, 통합을 의미한다.??(수정)| 
|프로덕션 준비      |Production-ready|작동한다, 요규사항을 충족한다, 안정적이다, 유지보수가능, 확장 가능, 문서화되어있다. 의 뜻을 가지고 있다. </br> 일반적으로 "X는 프로덕션 준비(production-ready)가 되지 않았습니다"는 기능, 안정성 및/또는 확장성이 누락된 문제가 있어서 덜 까다로운 시나리오에서는 사용할 수 있지만 대규모 배포(엔터프라이즈 및 인터넷 수준 배포)에서는 실패할 수 있음을 의미합니다.|
|마이그레이션       |migration       |한 운영환경으로부터, 대개의 경우 좀더 낫다고 여겨지는 다른 운영환경으로 옮겨가는 과정을 말한다.(이주)|
|로깅             |logging         |컴퓨팅에서 로그파일(logfile)은 운영 체제나 다른 소프트웨어가 실행 중에 발생하는 이벤트나 각기 다른 사용자의 통신 소프트웨어 간의 메시지를 기록한 파일이다. 로그를 기록하는 행위는 로깅(logging)이라고 한다.|
|클러스터          |cluster         |단일컴퓨터가 아니라 여러대 컴퓨터를 하나의 묶음으로 다루는 것을 뜻함, 즉 여러 가지 컴포넌트를 포함한다.|
|트러블슈팅         |trouble Shooting|문제가 발생했을 떄 **원인을 규명하고** 해결하는 작업을 의미한다. 과정에는 문제 정의, 사실 정리, 원인 추론, 조치 및 방안 검토, 해결 과정으로 나누어진다.|
|매니페스트(명백한)   |manifest|컴퓨팅에서 집합의 일부 또는 논리정연한 단위인 파일들의 그룹을 위한 메타데이터를 포함하는 파일이다. 예를 들어, 컴퓨터 프로그램의 파일들은 이름, 버전 번호, 라이선스, 프로그램의 구성 파일들을 가질 수 있다.|
|베어메탈          |bare metal      |어떤 소프트웨어도 담겨 있지 않은 하드웨어|
|데몬             |taemon          |사용자가 직접적으로 제어하지 않고, 백그라운드에서 돌면서 여러 작업을 하는 프로그램을 말한다.|
|라우팅            |routing        |라우팅은 어떤 네트워크 안에서 통신 데이터를 보낼 때 최적의 경로를 선택하는 과정이다. 최적의 경로는 주어진 데이터를 가장 짧은 거리로 또는 가장 적은 시간 안에 전송할 수 있는 경로다. 라우팅은 전화 통신망, 전자 정보 통신망, 그리고 교통망 등 여러 종류의 네트워크에서 사용된다. |
|프로비저닝        |provisioning   | 서버의 CPU, 메모리, 디스크 등의 물리적 자원을 적절히 할당하여 사용자가 원하는 형태의 가상 머신을 만들어 사용자에게 제공하는 과정|
|수평확장         |Horizontal scaling| IT자원의 수용 증가/감소를 처리할 수 있는 능력, 스케일 아웃과 스케일 인이 있음|
|수직확장         |Vertical scaling| 스케일 업과 스케일 다운, 기존 it 자원ㅇ르 다른 고사양 혹은 저사양 용량을 갖는 자원으로 대체한 경우 ex)데스크탑 성능을 업그레이드 하는것과 같음|
|CRUD             |CRUD           |대부분의 컴퓨터 소프트웨어가 가지는 기본적인 데이터 처리 기능인 Create(생성), Read(읽기), Update(갱신), Delete(삭제)를 묶어서 일컫는 말이다. 사용자 인터페이스가 갖추어야 할 기능(정보의 참조/검색/갱신)을 가리키는 용어로서도 사용된다.|

### point.1
## 클라우드 컴퓨팅의 특성
1. 주문형 자가 서비스(on-demand self service)
2. 폭넓은 네트워크 접근(Broad network access)
3. 자원 풀링(Resource pooling)
다중 임대(multi-tenant)방식으로 다중 사용자에게 제공하기 위해 풀 혀애로 유지
4. 신속한 탄력성(rapid elasticity)
- 신속한 확장/ 축소
5. 측정 서비스(measured service)
- 사용한만큼 페이지출

클라우드 model
- Saas(software as a service)
  + 웹브라우저 통한 접근 (구글 드라이브)
- Paas(Platform as a Service)
  + ids
- Iaas(infrastructure as a Service)
  - vm 같은것 AMAZON EC2, GCE


## 4.1 가상화 기술
* 가상화 기술 (virtualization, iass 기반 기술)
- 물리적인 자원과 사용자가 사용하는 자원을 분리(cpu, memory)

<img width="793" alt="스크린샷 2021-09-15 오후 1 14 22" src="https://user-images.githubusercontent.com/46950334/133369646-20b106af-4ac2-4674-8e48-7aa591f8546f.png">

> host machine없이 바로 가상화   
> virtualbox같은게 hypervisor, VMM이라고 한다.

### virtualization 키워드
1. 추상화(abstraction)
2. 다중화(multiple instances)
3. 고립, 독립 (isolation)
4. 통합 (consolidation)

### 가상화 장점 
1. 이용률(utilization)을 높인다.
2. 독립(isolation)적인 자원을 제공한 것처러 사용이 가능하다.
3. 여러 물리 자원들은 단일한 가상 자원으로 집계(aggregation)할 수 있다.
4. 이동성을 증가시킴
5. 모의실험(emulation)
> 베타테스터랑 비슷한건가???

### 클라우드 컴퓨팅에서 가상화의 필요성
1. 가상머신동적관리

### 가상화 소프트웨어 구현 층에 따른 분류
1. hardware 기반
- 메모리 사용량이 적고 부하가 적음
- -aws
- 호환성 이슈가 있음 
3. OS 기반 가상화
- host os가 이미 지원하는 장치를 모두 활용 가능
- 가상화 층의 도입에 따른 성능 저하발생
- vm
4. middleware
5. - JVM
### 설계방법
1. 전가상화(full virtualization)
- 변경사항이 없다.
2. 반가상화(para virtualization)
- os 수정하여 성능을 높인다

> 프로세스 가상화는 macos에서 뱅킹서비스를 못쓰니깐 뱅킹같은 특정한 서비스만 사용할 수 있게 만드는 가상화

#### 결국 가상화 목표에 따른 분류는 4가지로 나눌 수 있다.
1. 서버 가상화
2. 스토리지 공간 가상화
3. 네트워크 가상화
- vpn (학교네트워크를 우리가 쓸 수 있게 징검다리 역할을 해준다.)
4. 내장형 시스템 가상화


##### xen architecture : 1유형
Domain 0
Domain U


#### cpu virtualization
* 공평성과 효율성에 맞게 할당해야함
* 직접 수행(direct execution)
  * hypervisor를 사용

#### memory virtualization
* 페이징 세그멘테이션 
* 각 가상 머신이 쓰레싱없이 효과적으로 동작할 수 있도록 할당
VA -> PA -> MM
CACHE
#### i/o virtualization
* SR(single Rot)-IOV
