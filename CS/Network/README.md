# **Network**

## **네트워크의 정의**
네트워크는 Net과 Work의 합성어로 컴퓨터와 같은 노드들이 통신 기술을 통해 그물망처럼 연결되어 있는 통신을 하는 형태를 뜻하며, 데이터 및 리소스를 송신, 교환 또는 공유하기 위한 목적으로 케이블(유선) 또는 WIFI(무선)으로 연결된 2개 이상의 컴퓨터로 구성된다.  

> **몇 개의 독립적인 장치가 적절한 영역 내에서 적당히 빠른 속도로 물리적 통신 채널을 통하여 서로가 직접 통신할 수 있도록 지원해주는 데이터 통신 체계**

<br>

## **용어 정리**
- ip주소 : 통신을 위해 인터넷 프로토콜을 사용하는 네트워크에 연결된 모든 디바이스에 할당된 고유 번호
- 노드 : 데이터를 송신, 수신, 작성 또는 저장할 수 있는 네트워크 내의 연결지점, ex) 컴퓨터, 프린터, 모뎀, 브릿지 및 스위치
- 라우터 : 네트워크 간에 데이터 패킷에 포함된 정보를 전송하는 물리적 또는 가상 디바이스. 패킷교환기라고도 한다.
- 라우팅 : 라우터가 패킷을 네트워크에서 목적지까지 보내는 최적의 경로를 선택하는 과정
- 스위치 : 다른 디바이스를 연결하고 네트워크 내의 노드간 통신을 관리함으로써 데이터 패킷이 최종 목적지에 도달하도록 보장하는 디바이스
- 포트 : 네트워크 디바이스 간의 특정 연결 식별
- 프로토콜 : 컴퓨터가 다른 컴퓨터와 통신하는데 필요한 장비(네트워크 장비)가 서로 통신을 위해 정해놓은 통신규약.
- 패킷 교환 : 데이터를 일괄적으로 한번에 보내지 않고 여러개로 분할하여 송신하는 것

<br>

## **네트워크의 종류**
- WAN(Wide Area Network) : 지역 간 또는 대륙간의 넓은 지역에 컴퓨터를 연결. 인터넷은 전 세계 수십억 대의 컴퓨터를 연결하는 가장 큰 WAN
- MAN(Metropolitan Area Network) : 일반적으로 도시 및 정부기관이 소유, 관리
- LAN(Local Area Network) : 상대적으로 짧은 거리에 있는 컴퓨터를 연결. ex) 사무실, 학원, 병원의 모든 컴퓨터 연결 가능
- PAN(Personal Area Network) : 약 5m 전후의 인접통신. ex) 아이폰과 맥에서 정보를 공유하는 형태

## **TCP와 UDP**
- **TCP(Transmission Control Protocol, 전송제어 프로토콜)** 는 신뢰성이 없는 인터넷을 통해 종단간에 신뢰성 있는 **바이트 스트림** 을 전송하도록 설계되었다. TCP 서비스는 송신자와 수신자 모두 소켓이라고 부르는 종단점을 생성함으로써 이루어진다. TCP에서 연결 설정(connection establishment)은 **<u>3-way handshake</u>** 를 통해 행해진다.  
  모든 TCP 연결은 전이중(full-duplex), 점대점(point to point)방식이다. 전이중이란 전송이 양방향으로 동시에 일어날 수 있음을 의미하며 점대점이란 각 연결이 정확히 2개의 종단점을 가지고 있음을 의미한다. TCP는 멀티캐스팅이나 브로드캐스팅을 지원하지 않는다.

     - **<u>3-way handshake</u>**  
    TCP/IP 프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전에 먼저 정확한 정송을 보장하기 위해 상대방의 컴퓨터와 사전에 세션을 미리 수립하는 과정을 의미한다.  
    양쪽 모두 데이터를 전송할 준비가 되었다는 것을 보장하고, 실제로 데이터를 전달하기 전에 한쪽이 다른 쪽이 준비되었다는 것을 알 수 있도록 한다.
    1. A클라이언트는 B서버에 접속을 요청하는 SYN 패킷을 보낸다. 이때 A클라이언트는 SYN을 보내고 SYN/ACK 응답을 기다리는 SYN_SENT 상태가 된다.
    2. B서버는 SYN요청을 받고 A클라이언트에게 요청을 수락한다는 ACK 와 SYN flag가 설정된 패킷을 발송하고 A가 다시 ACK으로 응답하기를 기다린다. 이때 B서버는 SYN_RECEIVED 상태가 된다.
    3. A클라이언트는 B서버에게 ACK를 보내고 이후로부터는 연결이 이루어지고 데이터가 송수신 된다. 이때 B서버 상태가 ESTABLISHED이다.

<br>

- **UDP(User Datagram Protocol, 사용자 데이터그램 프로토콜)** 는 **비연결성 프로토콜** 이다. IP 데이터그램을 캡슐화해서 보내는 방법과 연결 설정을 하지 않고 보내는 방법을 제공한다. UDP는 흐름제어, 오류제어, 또는 손상된 세그먼트의 수신에 대한 재전송을 하지 않는다. UDP가 행하는 것은 포트들을 사용하여 IP 프로토콜에 인터페이스를 제공하는 것이다.  
UDP를 사용한 것들에는 DNS가 있다. 어떤 호스트 네임의 IP 주소를 찾을 필요가 있는 프로그램은, DNS 서버로 호스트 네임을 포함한 UDP 패킷을 보낸다. 이 서버는 호스트의 IP 주소를 포함한 UDP 패킷으로 응답한다. 사전에 설정이 필요하지 않으며 그 후에 해제가 필요하지 않다.

<br>

## **OSI 7계층**
OSI 7계층은 네트워크에서 통신이 일어나는 과정을 7단계로 나눈것을 말한다. 계층을 나눔으로써 통신이 일어나는 과정을 단계적으로 파악하고, 흐름파악과 이해에 용이하다. 또한 7단계 중 특정한 곳에 이상이 생기면 다른 단계의 장비 및 소프트웨어를 건들이지 않고도 이상이 생긴 단계만 고칠 수 있다.  

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F995EFF355B74179035)  

### **OSI 7계층 단계**
1. **물리 계층(Physical Layer)**  
    주로 전기적, 기계적, 기능적인 특성을 이용해서 통신 케이블로 데이터를 전송한다.  
    사용되는 통신 단위는 비트이며 이것은 1과 0으로 나타나고, 전기적으로는 ON, OFF와 같다.  
    이 계층에서는 단지 데이터를 전달만 할뿐 전송하거나 받으려는 데이터가 무엇인지, 어떤 에러가 있는지 등에 대해서는 전혀 신경쓰지 않는다.  
    단지 데이터를 전기적인 신호로 변화해서 주고 받는 기능만 할 뿐이다. 대표적인 장비로는 통신케이블, 리피터, 허브 등이 있다.

<br>

2. **데이터링크 계층(DataLink Layer)** 
    물리계층을 통해 송수신되는 정보의 오류와 흐름을 관리하여 안전한 정보의 전달을 수행할 수 있도록 도와주는 역할을 한다. 따라서 통신에서의 오류도 찾아주고 재전송도 하는 기능을 가지고 있다.  
    이 계층에서는 맥 주소를 가지고 통신하게 되며, 전송하는 단위를 프레임이라고 한다. 대표적인 장비로는 브리지, 스위치등이 있다.

<br>

3. **네트워크 계층(Network Layer)**  
     이 계층에서 가장 중요한 기능은 데이터를 목적지까지 가장 안전하고 빠르게 전달하는 기능(라우팅)이다.  
     여기서 사용되는 프로토콜의 종류도 다양하고, 라우팅하는 기술도 다양하다.
     이 계층은 경로를 선택하고 주소를 정하고 경로에 따라 패킷을 전달해주는 것이 이 계층의 역할이다. 대표적인 장비는 라우터이다.

     네트워크 계층은 여러개의 노드를 거칠 때 마다 경로를 찾아주는 역할을 하는 계층으로 다양한 길이의 데이터를 네트워크를 통해 전달하고, 그 과정에서 전송 계층이 요구하는 서비스 품질(QoS)을 제공하기 위한 기능적, 절차적 수단을 제공한다.

     네트워크 계층은 라우팅, 흐름제어, 세그멘테이션(segmentation/desegmentation), 오류 제어, 인터네트워킹(Internetworking)등을 수행한다.
     논리적인 주소 구조(IP), 네트워크 관리자가 직접 주소를 할당하는 구조를 가지며, 계층적이다.

     - **IP계층**  
        TCP/IP 상에서 IP계층이란 네트워크 주소(IP 주소)를 정의하고, IP 패킷의 전달 및 라우팅을 담당하는 계층이다.  
        OSI 7계층모델의 관점에서 보면 IP 계층은 네트워크 계층에 해당하며, 패킷을 목적지까지 전달하는 역할 및 그에 수반되는 기타 역할을 한다.
        - **IP 계층의 주요 역할**  
            IP 계층에서는 그 하위계층인 데이터링크 계층의 하드웨어적인 특성에 관계없이 독립적인 역할을 수행

        - **IP 계층 상에 있는 주요 프로토콜**  
            - 패킷을 전달을 책임지는 IP
            - 패킷 전달 에러의 보고 및 진달을 위한 ICMP
            - 복잡한 네트워크에서 인터네트워킹을 위한 경로를 찾게해주는 라우팅 프로토콜
   
    <br>

    - **IP 프로토콜**
        TCP/IP 기반의 인터넷 망을 통하여 데이터그램의 전달을 담당하는 프로토콜

        - **주요 기능**  
            IP계층에서 IP 패킷의 라우팅 대상이 됨(Routing)  
            IP 주소 지정(Addressing)
        
        - **주요 특징**  
            - Best_Effort Service : 신뢰성(에러제어) 및 흐름제어 기능이 없음 -> 신뢰성을 확보하려면 IP 계층 위의 TCP와 같은 상위 트랜스포트 계층에 의존
            - Connectionless : 연결성 데이터그램 방식으로 전달되는 프로토콜
            - Unreliable : 패킷의 완전한 전달(소실, 중복, 지연, 순서바뀜 등이 없게 함)을 보장하지않음
            - IPv4헤더, IPv6헤더, IP주소 : IP 패킷 해더 내 수신 및 발신 주소를 포함
            - Big-endian : IP 헤더 내 바이트 전달 순서 : 최상위 바이트(MSB)를 먼저 내보냄
            - IP 단편화 참조 : 경우에 따라, 단편화가 필요
            - TCP, UDP, ICMP, IGMP 등이 IP 데이터그램에 실려서 전송
  
  <br>

4. 전송 계층(Transport Layer)  
    통신을 활성화 하기 위한 계층이며, 보통 TCP 프로토콜을 이용한다. 데이터가 오면 4계층에서 데이터를 하나로 합쳐서 5계층에 던저준다.  
    단대단 오류제어 및 흐름제어 이 계층 까지는 물리적인 계층에 속한다.

    전송계층은 양 끝 단의 사용자들이 신뢰성 있는 데이터를 주고 받을 수 있도록 해주어, 상위 계층들이 데이터 전달의 유효성이나 효율성을 생각하지 않도록 해준다.  
    시퀀스 넘버기반의 오류 제어 방식을 사용하며, 전송 계층은 특정 연결의 유효성을 제어하고, 일부 프로토콜은 상태개념이 있으며(stateful), 연결기반(connection oriented)이다.  
    이는 전송 계층이 패킷들의 전송이 유효한지 확인하고 전송 실패한 패킷들을 다시 전송한다는 것을 뜻한다.  

    종단간 통신을 다루는 최하위 계층으로 종단간 신뢰성 있고 효율적인 데이터를 전송하며, 기능은 오류검출 및 복구와 흐름제어, 중복검사 등을 수행한다.

    - TCP 프로토콜  
        - OSI 계층모델의 관점에서 전송 계층에 해당
        - 양종단 호스트 내 프로세스 상호 간에 신뢰적인 연결지향성 서비스를 제공  
            신뢰적인 전송을 보장함으로써, 어플리케이션 구현이 한층 쉬워지게 됨
        - 신뢰성 있음(Reliable)  
            패킷 손실, 중복, 순서바뀜 등이 없도록 보장
            TCP 하위계층은 IP 계층의 신뢰성 없는 서비스에 대해 다방면으로 신뢰성을 제공
        - 연결지향적(Connection-oriented)  
            같은 전송계층의 UDP가 비연결성인 것과는 달리, TCP는 연결지향적이다.  
            연결 관리를 위한 연결설정 및 연결해제가 필요하며, 양단간 어플리케이션/프로세스는 TCP가 제공하는 연결성 회선을 통하여 서로 통신한다.  
    
    <br>

    - UDP 프로토콜  
        - 전송 계층의 통신 프로토콜 중 하나이며 신뢰성이 낮은 프로토콜로써 완전성을 보장하지 않으나, 가상회선을 굳이 확립할 필요가 없고 유연하며 효율적 응용의 데이터 전송에 사용한다.  
        - 비연결성이고, 신뢰성이 없으며, 순서화되지 않은 Datagram 서비스 제공  
            - 메세지가 제대로 도착했는지 확인하지 않음(확인응답 없음)
            - 수신된 메세지의 순서를 맞추지 않음(순서제어 없음)
            - 흐름 제어를 위한 피드백을 제공하지 않음(흐름제어 없음)
            - 검사합을 제외한 특별한 오류 검출 및 제어 없음(오류제어 거의 없음)  
                UDP를 사용하는 프로그램 쪽에서 오류제어 기능을 스스로 갖추어야 한다.
            - 데이터그램 지향의 전송계층용 프로토콜(논리적인 가상회선 연결이 필요없음)  
                비연결접속상태 하에서 통신
        - 실시간 응용 및 멀티캐스팅 가능  
            - 빠른 요청과 응답이 필요한 실시간 응용에 적합
            - 여러 다수 지점에 전송 가능(1:N)
        - 헤더가 단순함
          - UDP는 TCP 처럼 16비트의 포트 번호를 사용하나, 헤더는 고정크기의 8바이트(TCP는 20바이트)만 사용, 즉 헤더 처리에 많은 시간과 노력을 요하지 않는다.

<br>

5. 세션 계층(Session Layer)  
    데이터가 통신하기 위한 논리적인 연결이며 세션설정, 유지, 종료ㅈ, 전송 중단 시 복구 등의 기능이 있다.  
    세션 계층은 양 끝단의 응용 프로세스가 통신을 관리하기 위한 방법을 제공한다.
    동시 송수신 방식(duplex), 반이중 방식(half-duplex), 전이중 방식(Full Duplex)의 통신과 함께, 체크 포인팅과 유휴, 종료, 다시 시작 과정 등을 수행한다.  
    이 계층은 TCP/IP 세션을 만들고 없애는 책임을 진다.  
    -> 통신을 하기 위한 세션을 확립/유지/중단(운영체제가 함)

    <br>

6. 표현 계층(Presentation Layer)  
    데이터 표현이 상이한 응용 프로세스의 독립성을 제공하고, 암호화 한다.  
    표현 계층은 코드 간의 번역을 담당하여 사용자 시스템에서 데이터의 형식상 차이를 다루는 부담을 응용 계층으로부터 덜어준다. MIME 인코딩이나 암호화 등의 동작이 이 계층에서 이루어진다.  
    예를 들면, EBCDIC로 인코딩된 문서 파일을 ASCII로 인코딩된 파일로 바꿔 주는 것, 해당 데이터가 TEXT인지, 그림인지, GIF인지 JPG인지의 구분 등이 이 표현 계층의 몫이다.  
    ->사용자의 명령어를 완성 및 결과 표현, 포장/압축/암호화

    <br>

7. 응용 계층(Application Layer)  
    최족 목적지로서 HTTP, FTP, SMTP, POP3, IMAP, Telent등과 같은 프로토콜이 있다.
    해당 통신 패킷들은 방금 나열한 프로토콜에 의해 모두 처리되며 우리가 사용하는 브라우저나, 메일 프로그램은 프로토콜을 보다 쉽게 사용하게 해주는 응용프로그램이다. 한마디로 모든 통신의 양 끝단은 HTTP와 같은 프로토콜이지 응용프로그램이 아니다.  

    응용 계층은 응용 프로세스와 직접 관계하여 일반적인 응용 서비스를 수행한다.  
    일반적인 응용 서비스는 관련된 응용 프로세스 사이의 전환을 제공한다.  
    -> 네트워크 소프트웨어 UI부분, 사용자의 I/O 부분  
    - HTTP 프로토콜  
        웹 상에서 웹 서버 및 웹브라우저 상호 간의 데이터 전송을 위한 응용계층 프로토콜  
        처음에는, WWW 상의 하이퍼텍스트 형태의 문서를 전달하는데 주로 이용  
        현재에는, 이미지나 비디오, 음성 등의 모든 형식의 데이터 전송 가능  

      - 요청 및 응답의 구조  
        동작 형태가 클라이언트 / 서버 모델로 동작  

      - 메세지 교환 형태의 프로토콜  
        클라이언트 서버 간에 HTTP메세지를 주고받으며 통신

      - 트랜잭션 중심의 비연결성 프로토콜  
        종단간 연결이 없음(Connectionless)  

        이전의 상태를 유지하지 않음(Stateless)
      - 전송계층 프로토콜 및 사용 포트 번호  
        전송계층 프로토콜 : TCP
        사용 포트 번호 : 80번

      - http 표준
  
<br>

## **Socket**
소켓(Socket)은 TCP/IP 기반 네트워크 통신에서 데이터 송수신의 마지막 접점을 말한다. 소켓통신은 이러한 소켓을 통해 서버-클라이언트간 데이터를 주고받는 양방향 연결 지향성 통신을 말한다. 소켓통신은 보통 지속적으로 연결을 유지하면서 실시간으로 데이터를 주고받아야 하는 경우에 사용된다.  
소켓통신에서는 서버와 클라이언트가 존재하며, 서버는 데이터를 제공하고, 클라이언트는 데이터를 요청하여 제공받는 쪽을 말한다.  
소켓은 TCP/IP 4계층에서 전송 계층 위에 있으며, 전송계층 프로토콜 제어를 위한 코드를 제공한다.  

## **소켓 API 실행 흐름**
- 클라이언트  
    소켓 생성, 연결 요청, 데이터 송수신, 소켓 닫기
    
- 서버  
    소켓 생성, 결합, 주시, 받아들이기, 데이터 송수신, 소켓 닫기

### **클라이언트 흐름**
#### 1. 클라이언트 소켓 생성
연결 대상에 대한 정보가 들어있지 않은 Socket(껍데기 소켓)을 생성한다.  
이 때 소켓의 종류를 선택해야 하는데 TCP 소켓을 위해서는 stream 타입을, UDP 소켓을 위해서는 데이터그램 타입으로 지정이 가능하다.

#### 2.  연결 요청 
연결하고 싶은 대상에게 연결 요청을 보낸다. 이때 **IP주소와 서비스 포트 번호** 로 연결하고 싶은 타겟 대상을 특정한다.
요청을 보내고 단순히 끝나는 게 아니고, 그 요청에 대한 결과가 돌아와야만 Connect의 실행이 끝난다.

#### 3. 데이터의 송수신 (Send, Recieve)  
연결 요청과 같이, 요청을 보낸다고 끝난게 아니라 요청에 대한 결과(신호)가 들어와야 실행이 끝난다.
그러나 송신할 때에는 데이터를 보내는 것이기 때문에 데이터를 언제 얼마나 보낼것인지 알수있지만, 수신할 때에는 상대방이 언제 얼만큼의 데이터를 보낼 것인지 알 수 가 없다는 서로의 차이점이 존재한다.  
그렇기 때문에 **수신하는 API는 별도의 Thread에서 진행하게 된다.**

#### 4. 소켓 닫기  
더 이상의 데이터 송수신이 없다고 판단되면 소켓을 닫는다.

<br>

### **서버의 흐름**
#### 0. 데이터를 송수신 할 때는 보안이 제일 중요하다.  
어떤 데이터를 보내려고 할 때, 수신 측에서 무작정 데이터를 수신하는게 아니라 포트번호를 식별하여 알맞게 들어온 프로세스만을 수신하여야 한다.

#### 1. 서버 소켓 생성  
클라이언트 소켓과 마찬가지로 연결 대상에 대한 정보가 들어있지 않은 껍데기 소켓을 생성한다.

#### 2. 바인딩(bind)  
우리는 컴퓨터를 사용할 때 매우 많은 서비스를 이용하고 있다. 즉, 수많은 프로세스가 동시에 돌아가고 있다.  
만약 서버 소켓이 받은 데이터를 다시 돌려주어야할 때 프로세스들의 포트번호가 동일하다면 혼란이 생길 수 있다. 따라서 서버 소켓이 고유한 포트 번호를 만들 수 있도록 소켓과 포트번호를 결합해주는 작업이 필요하다.  
이러한 이유로 운영체제에서는 소켓들이 중복된 포트 번호를 사용하지 않도록, 내부적으로 포트 번호와 소켓 연결 정보를 관리한다.

하나의 프로세스는 동일한 포트 번호를 가진 여러 개의 소켓을 결합할 수 있다. 다시 말해서, 호스트가 하나의 Port로 여러 개의 Socket을 만들어 다른 호스트들과 데이터를 주고 받을 수 있다.  
이러한 이유로 우리는 하나의 채팅앱을 사용하더라도 동시에 많은 사람들과 채팅을 주고 받을 수 있다.  

#### 3. 클라이언트 연결 요청 대기  
서버 소켓에서 포트번호와 바인딩 작업을 마치고 나면 클라이언트로부터 연결 요청을 받아들일 준비가 된 것이다.  
클라이언트가 연결 요청을 할 때 까지 기다리다가 연결 요청이 오면 대기 상태를 종료하고 리턴한다.

#### 4. 클라이언트 연결 수립  
서버소켓은 연결 요청을  받아들임과 동시에 새로운 소켓을 생성한다.  
서버 소켓의 메인 역할은 클라이언트 연결 요청을 기다리는 것이다. 따라서 클라이언트 소켓으로부터 연결 요청을 받으면 새로운 소켓을 열고, 이것과 클라이언트 소켓을 맵핑하여 넘겨준다.

#### 5. 데이터 송수신(Send, Recieve)  
클라이언트와 동일하다.

#### 6. 소켓 닫기  
클라이언트와 동일하다. 하지만 서버 소켓은 자신이 생성한 소켓들도 관리 해야한다.