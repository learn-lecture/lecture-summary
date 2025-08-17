* HTTP Message Converter
  * ByteArrayHttpMessageConverter
    * org.springframework.http.converter
    * byte[] 타입으로 변환
  * StringHttpMessageConverter
    * org.springframework.http.converter
    * 문자열로 데이터 변환
  * MappingJackson2HttpMessageConverter
    * org.springframework.http.converter.json 
    * 클래스 or 미디어 타입으로 변환
  * `canRead()`, `canWrite()` 메서드로 확인 후 `read()`, `write()` 메서드 실행

* RequestMappingHandlerAdapter
  * HandlerMethodArgumentResolver
    * org.springframework.web.method.support
    * 얘를 통해서 Controller Parameter 정보를 추출
  * HandlerMethodReturnValueHandler
    * org.springframework.web.method.support
    * 얘를 통해서 Controller 응답 값 정보를 추출
  * 여기서 직접적으로 HTTP Message Converter 를 찾아서 처리함
    * Loop 돌려서 타입, 조건 등에 맞는 Converter 꺼내서 처리