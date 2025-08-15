* Front Controller Pattern
  * Controller 들 앞 단에 공통 controller(servlet)을 둬서 핸들링
  * v1 - 다형성을 활용해서 해결 가능
    * Key, Value = {url, controller}
  * v2 - v1에서 view를 분리
    * v1에서 각 Controller가 View를 반환하며 FrontController에서 최종적으로 View를 Render
    * 추상화가 잘된 케이스
  * v3 - v2에서 model을 추가 및 view 중복성 제거
    * servlet 의존성이 확 떨어짐.
    * 비즈니스 로직에만 집중 가능
    * resolver를 활용해 view에서 큰 수정이 발생하면 그냥 수정 사항이 거의 없음
  * v4 - 조금 더 단순하고 실용적으로 처리
    * Model-View 객체에 관리하는 것도 중복
    * Model-View 관리도 front-controller에게 맡기고 비즈니스 로직은 그냥 값만 던져줌
  * v5 - 어댑터를 활용한 유연한 컨트롤러
    * 내가 구현한 ExcelDownloader 와 같은 구조 였다.