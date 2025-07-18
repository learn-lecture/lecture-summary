# HTTP 헤더 개요

* 표헌(Representation): 표현 메타데이터 + 표현 데이터
  * 표현 헤더 = 표현 메타데이터 + 페이로드 메시지
  * 메시지 본문 = 표현 데이터
  * RFC723x 에서 부터 사용

# 표현

* Content-Type: 표현 데이터 형식
* Content-Encoding: 표현 데이터 압축 방식
* Content-Language: 표현 데이터의 자연 언어
* Content-Length: 표현 데이터의 길이

# 협상 (콘텐트 네고시에이션)

* 요청시, 클라이언트가 원하는 표현 방식을 작성
    * 우선순위: Quality Values(q) 값 사용
* Accept
  * 우선순위: 구체적인 것이 우선순위
  * Accept: text/*, text/plain
    * text/plain 이 가장 우선순위
  * q 값을 사용해 활용 가능, 미디어 타입 맞출 
* Accept-Language
  * 0 ~ 1, 클수록 높은 우선순위
  * default = 1 (생략 가능)
  * Accept-Language: ko-KR,ko;q=0.9, ... 
    * 다양한 언어 정보
    * https://www.andiamo.co.uk/resources/iso-language-codes/
* 그 외 Accept-Encoding, Accept-Charset

# 전송 방식

* 단순 전송: length
* 압축 전송: zip
* 분할 전송: chunked
  * Content-length 가 없다.
* 범위 전송: range

# 특별한 정보

* Host Header
  * 실제로 ALB 설정할 때, 활용한 경험이 있음