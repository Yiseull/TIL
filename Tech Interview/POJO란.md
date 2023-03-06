# POJO란?

### 1분 답변

<aside>
📌 POJO란 특정 기술에 종속되지 않은 순수한 자바 객체를 의미합니다. 스프링 프레임워크는 POJO 방식의 프레임워크로, 스프링의 주요 기술은 애플리케이션을 POJO로 개발할 수 있게 해줍니다. 스프링에서는 도메인과 비지니스 로직을 수행하는 대상이 POJO 대상이 될 수 있습니다.

</aside>

### 상세 설명

**POJO**란 Plain Old Java Object 직역하면, 오래된 방식의 간단한 자바 오브젝트로, EJB 같이 같이 무거운 객체에 반발하여 사용하게 된 용어이다. 

**POJO**는 다른 클래스나 인터페이스를 구현하거나 확장하지 않은 단순한 클래스로 자바에서 제공하는 API 외에 종속되지 않는다. 일반적으로 우리가 알고 있는 getter, setter 같이 **기본적인 기능만 가진 자바 객체**를 말한다.

**POJO 예시**

```java
public class User {
    private String name;
    private int age;
    
    public String getName() {
    	return name;
    }
    public int getAge() {
    	return age;
    }
    
    public void setAge(int age) {
    	this.age = age;
    }
}
```

**POJO의 장점**

- 간결한 코드
- 자동화 테스트에 유리 (환경 종속적인 코드는 자동화 테스트가 어려움)
- 객체지향 설계를 자유롭게 적용

**POJO 프레임워크**

스프링 프레임워크는 POJO 방식의 웹 프레임워크이다. 스프링의 주요 기술인 IoC, DI, AOP는 애플리케이션을 POJO로 개발할 수 있게 해주는 기술이다. 스프링에서는 도메인과 비지니스 로직을 수행하는 대상이 POJO 대상이 될 수 있다.

*토비의 스프링*

> 진정한 POJO란 객체지향적인 원리에 충실하면서, 환경과 기술에 종속되지 않고 필요에 따라 재활용될 수 있는 방식으로 설계된 오브젝트를 말한다.
> 

<br>

### Reference

- [https://velog.io/@galaxy/Spring의-기본-특징-POJO](https://velog.io/@galaxy/Spring%EC%9D%98-%EA%B8%B0%EB%B3%B8-%ED%8A%B9%EC%A7%95-POJO)
- [https://doing7.tistory.com/81](https://doing7.tistory.com/81)