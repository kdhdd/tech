### Bean이란

* **스프링 컨테이너가 생성하고 관리하는 객체**를 Bean이라 한다.
* `@Component`, `@Service`, `@Repository`, `@Bean` 등으로 등록하면 컨테이너가 객체를 대신 만들어주고, 필요한 곳에 주입(DI)해 준다.
* 개발자가 `new`로 직접 만든 객체는 Bean이 아니다 → 컨테이너가 모르는 객체이므로 DI, AOP 등이 적용되지 않는다.

---

### Bean 생명주기

```
컨테이너 시작 → 객체 생성 → 의존 주입(DI) → 초기화 콜백 → 사용 → 소멸 콜백 → 컨테이너 종료
```

* 스프링 컨테이너가 시작되면 Bean을 생성하고 의존성을 주입한 뒤, 초기화 콜백을 호출한다.
* 컨테이너가 종료되면 소멸 콜백을 호출한 뒤 Bean을 제거한다.

**초기화/소멸 콜백 지정 방법:**

| 방법 | 초기화 | 소멸 | 권장 여부 |
|------|--------|------|-----------|
| **어노테이션 (권장)** | `@PostConstruct` | `@PreDestroy` | ✅ 가장 간결하고 직관적 |
| 인터페이스 구현 | `InitializingBean.afterPropertiesSet()` | `DisposableBean.destroy()` | ❌ 스프링에 코드가 종속됨 |
| `@Bean` 속성 지정 | `@Bean(initMethod="init")` | `@Bean(destroyMethod="close")` | 외부 라이브러리에 사용 |

---

### Bean Scope

| Scope | 설명 |
|-------|------|
| **singleton** (기본) | 컨테이너에 **단 하나의 인스턴스**만 존재. 모든 주입에 같은 객체 사용 |
| **prototype** | 주입할 때마다 **매번 새 인스턴스** 생성. 컨테이너는 생성까지만 관여하고 소멸은 관리하지 않음 |
| request | HTTP 요청마다 하나의 Bean (웹 전용) |
| session | HTTP 세션마다 하나의 Bean (웹 전용) |
| application | ServletContext 당 하나의 Bean (웹 전용) |

> 실무에서는 대부분 **singleton**을 사용한다. prototype은 매번 새 객체가 필요한 특수한 경우에만 쓰인다.