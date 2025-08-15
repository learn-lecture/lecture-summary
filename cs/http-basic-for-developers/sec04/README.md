# HTTP 역사

* HTTP/1.1
  * 1997년부터 가장 많이 사용하는 버전
  * RFC7230 ~ 7235
* HTTP/2
  * 성능 개선 버전
* HTTP/3
  * UDP로 성능 개선

# Stateful, Stateless

* 상태유지: client의 정보를 계속 갖고 있어야 함.
  * 연결이 끊기지 않고 정보를 계속 보유 중
    * 서버에 갑자기 장애가 발생하면?
    * client는 연결이 끊기면서 지금까지의 정보를 잃음
    * 처음부터 다시 프로세스 진행
* 무상태: client의 정보를 갖고 있지 않음.
  * 클라이언트가 자신의 정보를 포함해서 요청함.
  * 클라이언트가 조금 복잡해지는 단점은 있음.
    * 대신 서버에 장애가 발생하면?
    * 다른 서버에서 같은 요청을 하면 됨.
    * Scale Out 최강

# 비연결성(connectionless)

* 기본적으로 연결을 끊음 -> 여러 사용자 동시 처리 효율 극대화
  * 배식을 해주는 곳에서 음식을 받은 자리에서 다먹어야한다면?
  * 다음 사람들은 계속 무한정 기다림
  * 음식을 받자말자 벗어나게 한다면?
  * 다음 사람들은 기다림을 최소화하고 음식만 받고 이동하면 됨
* HTTP 한계
  * 매번 3-hand-shake 발생
  * html 에서  여러 resource 들을 요구
  * 각 파일들은 http 프로토콜로 resource 에 접근해서 가져옴
    * 각 파일들에 3-hand-shake 발생
* Persist Connection (지속 연결, Keep-Alive)
  * html 하나에 연관된 resource 가 다 도착할 때까지 연결해둠
    * 각 파일 별로 3-hand-shake 발생 X
    * 모든 resource 가 다 다운로드 되면 연결 종료

# Http Message

## 구조

|       start-line       |
|:----------------------:|
| * header-fields + CRLF |
|          CRLF          |
|      message body      |