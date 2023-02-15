# REST, REST API, RESTful

## REST(Representational State Transfer)
- **REST란?**
    - API 작동 방식에 대한 대한 조건을 부과하는 소프트웨어 아키텍처의 한 형식이다.
    - HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource) 명시하고, HTTP Method(POST, GET, PUT, DELETE, PATCH)를 통해 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미한다.
    - REST는 리소스 지향 아키텍처(ROA, Resource Oriented Architecture) 설계의 중심에 Resource가 있고, HTTP Method를 통해 Resource를 처리하도록 설계된 아키텍처를 의미한다.
    - 웹 사이트의 이미지, 텍스트, DB 내용 등의 모든 자원에 고유한 ID인 HTTP URI를 부여한다.
- **REST 구성 요소**
    - 자원(Resource): URI
        - 모든 자원에 고유한 ID가 존재하고, 이 자원은 Server에 존재한다.
        - Client는 URI를 이용해서 자원을 지정하고 해당 자원의 상태(정보)에 대한 조작을 Server에 요청한다.
    - 자원에 대한 행위(Verb): HTTP Method
    - 자원에 대한 행위의 내용(Representations): HTTP Message Payload
- **REST 아키텍처 스타일 원칙**
    - Uniform Interface(인터페이스 일관성)
        - HTTP 표준에 만 따른다면, 특정 언어나 기술에 종속되지 않고 모든 플랫폼에 사용할 수 있으며, URI로 지정한 Resource에 대한 조작이 통일된 인터페이스로 수행한다.
    - Stateless(무상태성)
        - HTTP 프로토콜이 Stateless Protocol이므로 REST도 무상태성을 가진다.
        - 다시 말해 Server는 Client의 context(세션, 쿠키) 정보를 별도로 저장하고 관리하지 않으며, 각 요청이 분리되어 있다.
        - 그래서 서비스의 자유도가 높아지고 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해진다.
    - Cacheable(캐시 처리 가능)
        - REST의 가장 큰 특징 중 하나는 HTTP라는 기존 웹 표준을 그대로 사용하기 때문에, 웹에서 사용하는 기존 인프라를 그대로 활용할 수 있다.
        - 따라서 HTTP가 가진 캐싱 기능을 적용할 수 있다. HTTP 프로토콜 표준에서 사용하는 Last-Modified 태그나 E-Tag를 이용하면 캐싱 구현이 가능하다.
        - 대량의 요청을 효율적으로 처리하기 위해 캐시가 요구된다.
        - 캐시 사용을 통해 응답시간이 빨라지고 REST Server 트랜잭션이 발생하지 않기 때문에 전체 응답시간, 성능, 서버의 자원 이용률을 향상시킬 수 있다.
    - Client-Server(클라이언트-서버 구조)
        - REST Server는 API 제공하고, Client는 사용자 인증이나 context(세션, 로그인 정보) 등을 직접 관리하는 구조로 각각의 역할이 확실히 구분된다.
        - 아키텍처를 단순화시키고 작은 단위로 분리함으로써 클라이언트-서버의 각 파트가 독립적으로 개선될 수 있도록 해준다.
    - Layered System(계층화)
        - Client는 보통 대상 서버에 직접 연결되었는지, 또는 중간 서버를 통해 연결되었는지 알 수 없고, 서버의 계층을 볼 수 없다.
        - Server는 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성을 둘 수 있고, Proxy와 게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있게 한다.
    - Code on demand
        - 서버에서 클라이언트로 실행 가능한 코드를 전송하여 클라이언트 기능을 확장할 수 있다. Javascrip나 Java Applet 등이 여기에 해당한다.
        - 예를 들어, 웹 사이트에서 등록 양식을 작성하면 브라우저는 잘못된 전화번호와 같은 실수를 즉시 강조 표시한다. 서버에서 전송한 코드로 인해 이 작업을 수행할 수 있다.
- **REST의 장단점**
    - 장점
        - HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요가 없다.
        - HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
        - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
        - Hypermedia API의 기본을 충실히 지키면서 범용성을 보장한다.
        - REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
        - 여러 가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
        - 서버와 클라이언트의 역할을 명확하게 분리한다.
    - 단점
        - 표준이 자체가 존재하지 않아 정의가 필요하다.
        - HTTP Method 형태가 제한적이다.
        - 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Header 정보의 값을 처리해야 하므로 전문성이 요구된다.

<br>

## REST API

- **REST API란?**
    - REST 아키텍처 스타일을 따르는 API를 의미한다.
- **REST API 설계 규칙**
    - URI는 동사보다는 명사를, 대문자보다는 소문자를 사용한다.
        
    - 마지막에 슬래시(/)를 포함하지 않는다.
        
    - 언더바(_) 대신 하이폰(-)을 사용한다. 공백제거
    
    - 파일확장자는 URI에 포함하지 않는다.
        
    - URI에 자원에 대한 행위를 포함하지 않는다.
        

<br>

## RESTful

- **RESTful이란?**
    - REST의 원리를 따르는 시스템을 의미한다.
    - REST를 사용했다 하여 모두가 RESTful 한 것은 아니다. REST API의 설계 규칙을 올바르게 지킨 시스템이 RESTful하다.
- **RESTful의 목적**
    - RESTful한 API를 구현하는 근복적인 목적은 일반적인 컨벤션을 통한 API의 이해도 및 호환성을 높이는 것
    - 즉, 이해하기 쉽고 사용하기 쉬운 REST API를 만드는 것
- **RESTful 하지 못한 경우**
    - CRUD 기능을 모두 POST로만 처리하는 API
    - route에 resource, id 외의 정보가 들어가는 경우

<br><br>

참고

- [http://www.incodom.kr/REST](http://www.incodom.kr/REST)
- [https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)
- [https://www.redhat.com/ko/topics/api/what-is-a-rest-api](https://www.redhat.com/ko/topics/api/what-is-a-rest-api)
- [https://aws.amazon.com/ko/what-is/restful-api](https://aws.amazon.com/ko/what-is/restful-api/)
- [https://ko.wikipedia.org/wiki/REST](https://ko.wikipedia.org/wiki/REST)