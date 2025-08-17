## MVC 패턴의 등장 배경

* Servlet 기반은 너무 View 작성이 힘들다.
* JSP 기반은 View와 Bussiness가 모여있다.
  * 높은 결합도
* MVC로 나누어 개선
  * Model: 화면에 그릴 데이터를 담는 역할
  * View: 화면에 그릴 역할
  * Controller: 화면에 그리기 전 데이터를 처리하는 역할