### 스프링 프레임워크란
* 자바 엔터프라이즈 개발을 편하게 해주는 경량급 오픈소스 애플리케이션 프레임워크
* **Lightweight Java Application Framework**
    * 목표: **POJO 기반의** Enterprise Application 개발을 쉽고 편하게 할 수 있도록 한다.
    * Java Application을 개발하는데 필요한 하부구조(Infrastructure)를 포괄적으로 제공한다.
    * Spring이 하부구조를 처리하기 때문에 개발자는 Application 개발에 집중할 수 있다.
* 간단히 스프링(Spring)이라고도 불린다.
* 동적인 웹 사이트를 개발하기 위한 여러 가지 서비스를 제공한다.
* 대한민국 공공기관의 웹 서비스 개발 시 사용을 권장하고 있는 전자 정부 표준 프레임워크의 기반 기술

---

### Spring, Spring MVC, Spring Boot의 차이

| 구분 | Spring | Spring MVC | Spring Boot |
|------|--------|------------|-------------|
| **정의** | IoC/DI 컨테이너를 핵심으로 한 **코어 프레임워크** | Spring 위에서 동작하는 **웹 MVC 모듈** | Spring 기반 앱을 **빠르게 구축**하기 위한 도구 |
| **역할** | 객체 생명주기 관리, DI, AOP 등 기반 제공 | 웹 요청/응답 처리 (Controller → Service → View) | 자동 설정 + 내장 서버로 설정 최소화 |
| **설정** | XML 또는 Java Config 직접 작성 | DispatcherServlet, ViewResolver 등 수동 설정 | `@SpringBootApplication` 하나로 자동 설정 |
| **서버** | 외부 WAS(Tomcat 등)에 배포 필요 | 외부 WAS에 배포 필요 | 내장 Tomcat으로 **독립 실행 가능** |

* **Spring** — 가장 근본이 되는 프레임워크. IoC 컨테이너가 빈(Bean)을 관리하고, DI로 의존성을 주입한다.
* **Spring MVC** — Spring의 웹 계층 모듈. `DispatcherServlet`이 요청을 받아 `@Controller`에 위임하는 MVC 패턴을 제공한다.
* **Spring Boot** — Spring/Spring MVC를 쓸 때 필요한 복잡한 설정을 **자동화**한 것. 별도의 WAS 설치 없이 `java -jar`로 바로 실행할 수 있다.

> 한 줄 요약: **Spring Boot ⊃ Spring MVC ⊃ Spring** <br>
> Spring Boot는 Spring을 대체하는 것이 아니라, Spring을 **더 편하게 쓰기 위한 도구**다.
