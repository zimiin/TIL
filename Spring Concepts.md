### @Configuration annotation

해당 클래스를 스프링 설정 클래스로 지정
</br></br>
### @Bean annotation

스프링이 생성하는 객체를 빈(Bean) 객체라고 한다.</br>
@Bean annotation을 메서드에 붙이면 해당 메서드가 생성한 객체를 스프링이 관리하는 빈 객체로 등록한다. 그리고 메서드의 이름으로 빈 객체를 구분한다.
</br></br>
### AnnotationConfigApplicationContext

자바 설정에서 정보를 읽어와 빈 객체를 생성하고 관리한다.
</br></br>
### getBean()

AnnotationConfigApplicationContext가 자바 설정을 읽어와 생성한 빈(bean) 객체를 검색할 때 사용한다.</br></br>

getBean(String name, @Nullable Class<Greeter> requiredType)</br>
- name : @Bean annotation의 메서드 이름인 빈 객체의 이름</br>
- requiredType : 검색할 빈 객체의 타입 (@Bean 메서드의 리턴 타입).
</br></br>
### BeanFactory Interface

객체 생성과 검색에 대한 기능을 정의한다(ex. getBean()).</br>
AnnotationConfigApplicationContext 클래스의 가장 상위 인터페이스.
</br></br>
### Singleton(싱글톤) 객체

단일 객체를 의미하는 단어다.</br>
스프링은 기본적으로 한 개의 @Bean annotation에 대해 한 개의 Bean 객체를 생성한다. 
</br></br>
### 의존

한 클래스 A가 다른 클래스 B의 메서드를 실행할 때 "A 클래스가 B 클래스에 의존한다"고 표현한다.</br>
의존은 변경에 의해 영향을 받는 관계를 의미한다. 예를 들어, B 클래스의 메서드 이름을 변경하면 A 클래스의 코드도 변경된다.
</br></br>
### DI (Dependency Injection, 의존 주입)

의존하는 객체를 직접 생성하는 것이 아니라 의존 객체를 전달받는 것.</br>
원래 의존 객체가 MemberDao라는 객체였는데, 이 객체 대신에 MemberDao를 상속한 CachedMemberDao라는 객체를 사용해야 하는 경우가 생겼다고 하자. 이 때, 의존하는 객체를 직접 생성했다면 의존 객체를 사용하는 모든 코드에서 객체 생성 코드를 변경해주어야 하는 불편함이 있다. 하지만 DI를 사용하면 객체를 생성하는 코드만 바꿔주면 된다.
</br></br>
### Assembler

의존 객체를 생성하고 주입해주고, 특정 객체가 필요한 곳에 객체를 제공한다.
