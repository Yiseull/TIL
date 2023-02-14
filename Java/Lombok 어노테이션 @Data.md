# Lombok 어노테이션 @Data

## Lombok이란?

Lombok은 Java 라이브러리로, 반복되는 메서드를 Annotation을 사용해서 자동으로 작성해준다. 

+ 어노테이션 기반의 코드 자동 생성을 통한 생산성 향상
+ 반복되는 코드 다이어트를 통한 가독성 및 유지보수성 향상
+ Getter, Setter 외에 빌더 패턴이나 로그 생성 등 다양한 방면으로 활용 가능

Lombok 어노테이션 중 @Date에 대해서 알아보자.

## @Date

@Data는 @Getter, @Setter, @RequiredArgsConstructor, @ToString, @EqualsAndHashCode 를 한 번에 적용해주는 어노테이션이다.

- @Getter - 모든 필드에 대한 접근자 자동 생성
- @Setter - 모든 non-final 필드에 대한 설정자 자동 생성
- @RequiredArgsConstructor - 초기화되지 않은 모든 final 필드와 @NonNull 필드에 대한 생성자 자동 생성
- @ToString - 모든 필드에 대한 toString 메서드 자동 생성
- @EqualsAndHashCode - equals 메서드와 hashCode 메서드 자동 생성


참고

<https://zi-c.tistory.com/entry/JAVA-Lombok-%EC%96%B4%EB%85%B8%ED%85%8C%EC%9D%B4%EC%85%98-Data>
<https://mangkyu.tistory.com/78>