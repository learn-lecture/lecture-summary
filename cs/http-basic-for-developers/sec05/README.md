# HTTP API

* 리소스를 기준으로 설계
  * 복수단어 사용

# HTTP 속성

* 안전 (Safe)
  * 호출 시 리소스가 변경되지 않는 특성
  * GET, HEAD, OPTIONS
* 멱등 (Idempotent)
  * 여러번 호출해도 결과가 똑같다.
  * GET, PUT, DELETE, PATCH
    * 여러번 호출해도 같은 결과를 보장함
    * 여러번 조회해도 서버는 변경 사항이 없음
    * 여러번 PUT 해도 같은 값으로 대체 됨
    * 여러번 DELETE 호출해도 계속 삭제 됨
    * 여러번 PATCH 해도 같은 값으로 수정 됨
* 캐시 가능 (Cacheable)
  * 응답 결과 리소스를 캐시 해두는 여부
  * GET, POST, PATCH, HAED 는 캐시가 된다.
  * 실제로는 GET, HEAD 정도만 캐시
    * POST, PATCH는 바디까지 캐시해둬야 하므로 무거움 (경우의 수 많음)
    * GET, HEAD는 URL을 기준으로 캐시 쉬움