# 꼭 알아야 할 전공 개념

### JAVA

- 객체지향 언어의 특징은?

  1. 캡슐화 
     - 객체의 역할에 맡게 데이터와 기능을 묶는 것 --> 정보 은닉에 사용 
     - 접근제어자에 의해 구현되어진다.
  2. 상속 
     - 상위 클래스의 특징을 하위 클래스가 물려받음.
     - 코드의 재사용을 증대시킬 수 있다.
  3. 다형성
     - 여러 가지 형태를 가질 수 있는 능력
     - 조상클래스 타입의 참조변수로 자손클래스의 인스턴스를 참조할 수 있도록 하였다

- 접근제어자 

  1. public : 접근 제한이 없다.
  2. protected : 같은 패키지 내의 클래스 혹은 다른 패키지의 상속 클래스에서 접근이 가능하다.
  3. default : 같은 패키지 내의 클래스들만 접근이 가능하다.
  4. private : 같은 클래스 내에서만 접근이 가능하다.

- static 이란?

  > 정적 변수. 
  >
  > static 키워드가 붙은 변수나 메서드들은 인스턴스를 생성할 필요 없이 자동으로 메모리에 할당하는 기능이다. 

- Overriding VS Overloading

  - Overriding 

    > 상속받은 클래스의 메소드를 하위클래스에 맞게 재정의 하는 것

  - Overloading 

    >  같은 클래스 내의 return value와 메소드명이 동일한 메소드를 매개변수만 다르게 만들어 다양한 상황에 맞게 메소드가 호출될 수 있도록 하는 것 (다형성)

- JVM이란 ?

  > Java Virtual Machine. 스택 기반의 가상머신이다.
  >
  > 자바 어플리캐이션을 클래스 로더를 통해 읽어들여 자바 api와 함께 실행시킨다. 또한 JAVA와 OS 사이의 중개자 역할을 하여 JAVA가 OS에 구애받지 않고 재사용이 가능하도록 해준다.
  >
  > 가장 중요한 역할로는 메모리 관리, garbage collection을 수행한다.





------

### OS

- process와 thread의 차이?

  - process

    > 실행중인 프로그램에 대한 인스턴스이다. 자신만의 고유공간과 자원을 할당받아 사용한다.
    >
    > 부팅 후 최초의 프로세스는 os에 의해 생성되고, 그 후엔 기존 프로세스 fork 후 시스템 콜을 통하여 새로운 작업을 덮어씌운다.

  - thread

    > 경량 프로세스라고 불린다. 프로세스 생성시 하나의 메인스레드가 함께 생성된다. 
    >
    >  프로세스 내에서 동작되는 여러 실행의 흐름으로, 프로세스 내의 주소 공간이나 자원들을 대부분 공유하면서 실행된다.  프로세스에 비해 생성시 오버헤드가 적고, 시스템의 자원 소모가 줄어들며 프로그램 응답시간이 줄어든다는 장점이 있다.
    >
    > (단. 단일 프로세서 시스템에서는 효과를 기대하기 어렵다)

- multi programming, multi processing, multi threading 차이 

- scheduling이 뭐지? 종류가 뭐가 있는지 ? 언제 사용 ? 

  > 자원을 어떤 프로세스에 얼마나 할당하는지 정책을 만드는 것으로 비 선점형 방식과 선점형 방식이 존재.
  >
  > 선점형 방식은 I/O요청, I/O응답, Interrupt발생, 작업완료 등의 상황에서 스케줄링이 일어날 수 있지만,
  >
  > 비선점형 방식은 프로세스가 스스로 CPU를 놓아주는 시점(작업이 완료되는 시점)에만 스케줄링이 일어난다. 

  - 선점형 (HRM, SRT, 라운드 로빈, 다단계 큐, 다단계 피드백 큐 스케쥴링)

    > 1. 실행상태에 있던 프로세스가 타이머 인터럽트 발생에 의해 준비상태로 바뀌는 경우
    > 2. I/O요청으로 봉쇄 상태에 있던 프로세스의 I/O 작업이 완료되어 인터럽트가 발생하고 그 결과 이 프로세스의 상태가 준비상태로 바뀌는 경우


  - 비 선점형 (SJF, Priority, Deadline, FIFO)

    > 1. 실행 상태에 있던 프로세스가 I/O 요청등에 의해 봉쇄(blocked)상태로 바뀌는 경우
    > 2. CPU에서 실행 상태에 있는 프로세스가 종료되는 경우

- 디스패처

  - 스케줄링이 발생하면 실행중이던 프로세스의 context를 그 프로세스의 pcb에 저장한 후 새롭게 선택된 프로세스의 context을 pcb로부터 복원한 후 그 프로세스에게 CPU를 넘귀는 과정을 수행한다.
  - 디스패처 지연시간 --> 디스패처가 하나의 프로세스를 정지시키고 다른 프로세스에게 CPU를 전달하기까지 걸리는 시간.





------

### 네트워크

- osi 7계층에 대해 설명

  1. Physical Layer

     - 물리적 매체로 로 비트흐름을 전송. (Ethernet)

  2. Data-link Layer (Frame) 

     - Frame의 시작과 끝을 구분하는 Frame 동기화
     - 개방시스템 간(노드-노드) 효율적이고 신뢰성 있는(흐름제어, 오류제어) 정보 전송을 하도록 함. (MAC)

  3. Network Layer (Packet)

     - 다중 네트워크 링크에서 Packet을 단위로 목적지까지의 경로를 설정한다.( = 라우팅 )
       시작지부터 목적지까지 성공적으로  전달되도록  한다. (IP, ICNP, IGMP, Routing)

  4. Transport Layer (Segment)

     - 종단(End-to-End, 발신자-목적지)간 신뢰성있고 정확한(흐름제어, 오류제어) 데이터 전송을 담당한다.
     - 패킷의 전송이 유효한지 확인, 재전송과 같은 신뢰성 있는 통신 보장 (TCP/UDP)

  5. Session Layer

     - 통신세션을 구성하며 포트번호를 기반으로 연결. 
     - 송수신(Duplex), 반이중(Half-Duplex), 전이중(Full-Duplex) 방식의 통신

  6. Presentation Layer

  7. Application Layer

     ​

- Protocol이란?

  - 컴퓨터와 컴퓨터간의 정보를 전달할 경우, 원활한 정보 전달을 위한 협정 또는 규칙

- TCP와 UDP ?

  - 둘 다 4(Transport) Layer의 프로토콜

  - TCP

    > 연결 지향적이며 신뢰성 있는 통신을 보장한다. 신뢰성 있다는 것은은 패킷의 손실여부를 확인 후 패킷이 손실된 경우에는 해당 패킷을 재전송한다는 것을 뜻한다. 패킷 손실의 여부는 시퀀스 넘버와 ack넘버 값을통해 확인한다.
    >
    > 연결시에는 3-way handshaking ()을 수행하며 종료시에는 4-way handshaking(fin-> ack<- fin<- ack-> )을 수행한다.
    >
    > 모든  TCP연결은 전이중, 점대점 방식이다. 

  - UDP

    > 비연결 지향적이며 비신뢰성의 특징을 갖는 프로토콜이다.
    >
    > 패킷의 손실여부를 확인하지 않으며 재전송또한 하지않아 tcp에 비하여 속도가 빠르며 실시간 통신(스트리밍 등)에 적합하다.

- HTTP 프로토콜이란?

  - 인터넷상에서 HyperText 형식의 문서를 주고박은 서버/클라이언트 모델을 따르는 프로토콜이다.

  - HTTP 문제점

    > 1. HTTP는 평문 통신이기 때문에 도청이 가능하다.
    > 2. 통신 상대를 확인하지 않기 때문에 위장이 가능하다.
    > 3. 완전성을 보장할 수 없기 때문에 변조가 가능하다.

  - HTTPS --> 소켓통신에서 일반 텍스트 대신 SSL을 통해 세션 데이터를 암호화 (부하 발생 가능)

- GET과 POST

  - GET

    > GET메소드는 요청데이터가 `HTTP Request Message`의 Header부분의 url에 쿼리스트링으로 담겨서 전송된다.
    >
    > 데이터를 조회하는 경우에 주로 쓰이며 데이터가 url상에 요청되기때문에 로그인과 같이 보안이 필요한 데이터에 대해서는 적절하지 않다.
    >
    > GET방식의 요청은 브라우저에서 Caching이 가능하기 때문에 Post방식으로 요청해야할 것을  보안이 필요하지 않고 요청 데이터 크기가 작다는 이유만로 사용하면 기존에 Caching되었던 데이터가 요청될 가능성이 있다.

  - POST

    > POST메소드는 요청데이터가  `HTTP Request Message`의 Body부분에 담겨 전송된다. 서버의 값이나 상태를 변경 혹은 추가하기 위해 사용한다. 전송 데이터의 크기가 제한적이지 않다.

- ARP와 RARP

  - ARP

    > IP address를 알고있을 때 MAC주소를 알아내야할 경우 사용하는 프로토콜이다.

  - RARP

    > ARP와 반대로 MAC주소를 알고있을 때 IP주소를 알아내야할 경우 사용하는 프로토콜 이다.

