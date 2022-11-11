# @Controller와 @RestController 차이

Spring에서 컨트롤러를 지정해주기 위한 어노테이션은 @Controller와 @RestController가 있다.<br>

둘의 차이점은 HTTP Response Body가 생성되는 방식이다.

<br>

## @Controller
Spring MVC의 컨트롤러로 주로 View를 반환하기 위해 사용한다.<br><br>

View가 아닌 데이터를 반환해야 하는 경우에는 @ResponseBody를 활용하면 된다.<br>

이때 데이터 형식은 문자열, VO 객체 모두 가능하며, 객체를 반환하면 Json 형태로 반환된다.

```java
@Controller
@ResponseBody
public class HelloController {
    ...
}
```
<br>

## @RestController
RESTful Web Service에서 사용되는 특수 컨트롤러이며, @Controller + @ResponseBody와 동일하다.<br>

```java
@RestController
public class HelloController {
    ...
}
```

<br>

참고<br>
<https://mangkyu.tistory.com/49>
<https://dncjf64.tistory.com/288>