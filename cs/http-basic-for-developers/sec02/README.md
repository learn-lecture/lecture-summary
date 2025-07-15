# IP (Internet Protocol)

* 지정한 IP 주소로 패킷(Packet) 단위로 데이터 전달
  * 출발지 -> 목적지
  * 정보
  * 인터넷 망 간 노드를 통해
* 한계
  * 비연결성: 받을 대상이 없어도 전송됨
  * 비신뢰성: 네트워크 상태로 인해 중간에 패킷이 하나 사라질 수 있음.
    * 즉, 목적지에 도착 못하는 경우가 발생
    * 순서도 모름, 네트워크 상 라우팅 정책으로 패킷의 도착 순서가 다름
  * 프로그램 구분: 한 PC에서 둘 이상의 App이 실행 중
    * 서버는 클라이언트에게 정보를 전송
    * App1 에게? App2 에게? 모름

# TCP, UDP

IP 프로토콜의 한계를 극복하는 규약

## 인터넷 프로토콜의 4계층

* App: HTTP, FTP
* Transfer: TCP, UDP
* Internet: IP
* Network ifc
* ETHERNET_FRAME{IP{TCP{HTTP}}}

## TCP - 전송제어 프로토콜(Transmission Control Protocol)

* IP{TCP}: IP는 출발지, 목적지 IP와 기타 정보로 구성
  * TCP는 출발지, 목적지 포트와 전송제어, 순서, 검증 정보, 데이터 등을 포함
    * 연결 지향으로 신뢰할 수 있는 프로토콜

### 3 Way Handshake

* Syn (동기화 요청) -> Syn + Ack (OK 나도 동기화 요청) -> ACK + {data} (OK data 보낼게)
* 데이터 전달 보증: 연결됐으므로, 서버에서 요청에 대한 응답 가능
* 순서 보장: 서버에서 전달받은 패킷 순서를 보고 재요청 (동기화 처리에 따라 다름)

## UDP - 사용자 데이터그램 프로토콜(User Datagram Protocol)

* IP{UDP}: IP 정보와 UDP는 PORT만 포함
* 빠름, TCP는 신뢰성을 위해 응답이 완료됐는지 클라이언트 측에서 확인해야됨 -> 그동안 뭘 못함
* UDP는 클라이언트 측에서 보내고 끝임 -> 서버로 잘 전달됐는지 몰라도 됨
* 최근 HTTP3가 UDP 기반으로 UDP가 좋음
