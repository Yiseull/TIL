# @Controller와 @RestController 차이

Spring MVC에서 컨트롤러를 지정해주기 위한 어노테이션은 @Controller와 @RestController가 있습니다.<br>

## @Controller
return 값으로 View 페이지를 반환 ViewResolver에 의해

View 페이지가 아닌 반환값 그대로 클라이언트한테 return 하고 싶은 경우 메소드 위에 @ResponseBody를 사용
```java
@Controller
public class HelloController {

    @ResponseBody
    @RequestMapping()
    public String hello() {
        return "Hello!";
    }
}
```
문자열이 아닌 VO 객체 반환도 가능, 객체를 반환하면 Json 형태로 반환

## @RestController
@RestController는 @Controller와  @ResponseBody의 조합입니다. Spring에서 RESTful 웹 서비스를 보다 쉽게 개발할 수 있도록 Spring 4.0에 추가되었습니다.

REST API를 개발해야하는 상황에 @ResponseBody를 붙여서 데이터를 그대로 반환하도록 할 수 있는데
@RestController는 @Controller와 @ResponseBody가 합쳐진 거

아까 코드를 아래처럼
```java
@RestController
public class HelloController {

    @RequestMapping()
    public String hello() {
        return "Hello!";
    }
}
```