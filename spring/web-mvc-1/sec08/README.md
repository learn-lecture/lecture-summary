* 실습 중 트러블 슈팅
  * 파라미터 아규먼트 리졸브는 NoArgs 기반으로 동작
  * Noargs가 private이면 reflection 불가능해서 오류 남
* PRG 패턴의 중요성
  * SSR 에서는 필요하지만 CSR 이라면?
  * trust but verify 로 멱등성을 보장할 방법을 생각
    * 멱등키, 비즈니스 로직 강화 등