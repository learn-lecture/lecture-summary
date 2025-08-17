* HandlerMapping
  * RequestMappingHandlerMapping
    * org.springframework.web.servlet.mvc.method.annotation
    * 어노테이션 기반 `@RequestMapping`을 핸들링 할 수 있도록 작성된 클래스
    * 99.9% 실무에서 사용하는 방식
  * BeanNameUrlHandlerMapping
    * org.springframework.web.servlet.handler
    * Bean Name과 같은 Url을 핸들링 할 수 있도록 작성된 클래스
* HandlerAdapter
  * RequestMappingHandlerAdapter
    * org.springframework.web.servlet.mvc.method.annotation
    * `@RequestMappng` 핸들러를 처리하는 어댑터
  * HttpRequestHandlerAdapter
    * org.springframework.web.servlet.mvc
    * SimpleControllerHandlerAdapter와 동일하다고 생각하면 됨
    * HttpRequestHandler Interface, BeanNameUrlHandlerMapping 을 처리함.
  * SimpleControllerHandlerAdapter
    * org.springframework.web.servlet.mvc
    * Controller Interface, BeanNameUrlHandlerMapping을 처리하는 클래스
* View Resolver
  * InternalResourceViewResolver
    * org.springframework.web.servlet.view
    * IOC를 활용한 properties 정보로 자동구성
    * spring.mvc.view.prefix=/WEB-INF/views/ 
    * spring.mvc.view.suffix=.jsp
  * BeanNameViewResolver
    * Bean Name을 기반으로 뷰를 찾아서 반환
    * Excel 파일과 같은 파일 처리하기 좋음
