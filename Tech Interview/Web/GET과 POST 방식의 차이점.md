# GET과 POST 방식의 차이점

## GET

- 클라이언트가 서버로부터 정보를 조회하기 위해 설계된 메소드이다.
    - ex) 게시글 보기
- GET은 요청을 전송할 때 필요한 데이터를 Body에 담지 않고 쿼리스트링을 통해 전송한다.
- 쿼리스트링을 사용하게 되면 URL에 조회 조건을 표시하기 때문에 특정 페이지를 링크하거나 북마크할 수 있다.
- 불필요한 요청을 제한하기 위해 캐시될 수 있다.
    - 서버에 리소스를 요청할 때 웹 캐시가 요청을 가로채 서버로부터 리소스를 다시 다운로드하는 대신 리소스의 복사본을 반환한다.
    - HTTP 헤더에서 cache-control 헤더를 통해 캐시 옵션을 지정할 수 있다.
- GET 요청은 브라우저 히스토리에 남는다.
- GET 요청은 북마크 될 수 있다.
- GET 요청은 길이 제한이 있다. 길이 제한은 표준이 있진 않고 브라우저마다 제한이 다르다.
- GET 요청은 중요한 정보를 다루면 안된다.
    - GET 요청은 파라미터에 다 노출되기 때문에 보안에 취약하다.
- GET 요청 성공 시, 200(OK) HTTP 응답 코드 반환

## POST

- POST는 리소스를 생성/변경하기 위해 설계된 메서드로, 서버에 데이터를 보내는데 사용된다.
    - ex) 게시판에 글쓰기
- GET과 달리 전송해야될 데이터를 HTTP 메시지 Body에 담아 전송한다.  (Body의 타입은 Content-Type 헤더에 따라 결정된다.)
- HTTP 메시지 Body는 길이 제한이 없다. 따라서 POST 요청은 GET과 달리 대용량 데이터를 전송할 수 있다.
- 데이터가 Body로 전송되어 GET의 쿼리스트링 방식보다 안전하다고 생각할 수 있지만, POST 요청도 크롬 개발자 도구와 같은 툴로 요청 내용을 확인할 수 있기 때문에 민감한 데이터는 암호화해서 전송해야 한다.
- POST 요청은 캐시되지 않는다.
- POST 요청은 브라우저 히스토리에 남지 않는다.
- POST 요청은 북마크 되지 않는다.
- POST 요청 성공 시, 201(CREATED) HTTP 응답 코드 반환


## GET vs POST

|  | GET | POST |
| --- | --- | --- |
| 사용 목적 | 리소스 요청 | 리소스 생성 |
| 리소스 전달 방식 | 쿼리스트링 | HTTP Body |
| URL에 데이터 노출 여부 | O | X |
| HTTP 응답 코드 | 200(OK) | 201(CREATED) |
| 캐시 | O | X |
| 브라우저 기록 | O | X |
| 북마크 추가 | O | X |
| 데이터 길이 제한 | O | X |
| 멱등성(idempotent) | O | X |
| 속도 | POST보다 빠름 | GET보다 느림 |

멱등성(idempotent)이란?
- 연산을 여러 번 적용하더라도 결과가 달라지지 않는 성질을 의미한다.

## 꼬리질문
    
Q.  조회하기 위한 용도로 POST가 아닌 GET 방식을 사용하는 이유는?

A1. GET 방식은 멱등하므로 서버에 여러 번 요청을 하더라도 동일한 응답이 돌아오며, 서버의 데이터나 상태를 변경시키지 않는다. 반면에 POST는 서버의 데이터나 상태를 바꾸기 위한 용도이다.

A2. 모든 리소스는 Link할 수 있는 URL을 가지고 있어야 한다. 어떤 웹페이지를 조회할 때 해당 링크의 정보가 필요하다. 이때 POST 방식의 경우 값이 Body에 있기 때문에 URL만 전달할 수 없기 때문에 GET 방식을 사용해야 한다.

<br>

참고

- [https://brilliantdevelop.tistory.com/33](https://brilliantdevelop.tistory.com/33)
- [https://velog.io/@songyouhyun/Get과-Post의-차이를-아시나요](https://velog.io/@songyouhyun/Get%EA%B3%BC-Post%EC%9D%98-%EC%B0%A8%EC%9D%B4%EB%A5%BC-%EC%95%84%EC%8B%9C%EB%82%98%EC%9A%94)
- [https://github.com/WeareSoft/tech-interview/blob/master/contents/network.md#get-메서드와-post-메서드](https://github.com/WeareSoft/tech-interview/blob/master/contents/network.md#get-%EB%A9%94%EC%84%9C%EB%93%9C%EC%99%80-post-%EB%A9%94%EC%84%9C%EB%93%9C)