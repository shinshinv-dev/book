# NestJS로 배우는 백엔드 프로그래밍

# CHAP1. Hello NestJS
## 1.1 NestJS의 장점
- CQRS, 인터셉터, 미들웨어
---
from. sunman
- Express(main), Fastify를 래핑
- Express의 단점
  - 일정하지 않은 소프트웨어 품질
  - 라이브러리 검색 부담
- NestJS의 특징
  - 모듈/컴포넌트 기반, IoC, DI, AOP, Typescript
---
```
- CQRS
CQRS는 Command Query Responsibility Segregation의 약자로, 명령(Command)과 조회(Query)의 책임을 분리하는 아키텍처 패턴입니다. 아래는 CQRS의 주요 특징과 장점입니다:

책임 분리: 명령과 조회를 분리하여 각 역할에 맞는 최적화된 모델을 사용할 수 있습니다.

Command: 데이터 변경 작업을 처리하며, 복잡한 비즈니스 로직을 포함할 수 있습니다.

Query: 데이터 조회 작업을 처리하며, 읽기 전용 모델로 단순화할 수 있습니다.

확장성: 읽기와 쓰기 작업을 독립적으로 확장할 수 있어 성능과 확장성이 향상됩니다.

유연성: 서로 다른 저장소나 데이터베이스를 사용할 수 있어, 요구사항에 따라 유연하게 시스템을 구성할 수 있습니다.

복잡한 도메인 로직 처리: 복잡한 비즈니스 로직을 명령 모델에 집중시켜 관리할 수 있습니다.

CQRS는 특히 복잡한 도메인 로직을 처리하거나 성능과 확장성이 중요한 시스템에서 유용하게 사용됩니다.
```

## 1.2 Express가 좋을까, NestJS가 좋을까
```
- SSR
SSR은 Server-Side Rendering의 약자로, 서버에서 HTML을 렌더링하여 클라이언트에 제공하는 방식입니다. 아래는 SSR의 주요 특징과 장점입니다:

초기 로드 시간 단축: 서버에서 완전히 렌더링된 HTML을 제공하기 때문에 클라이언트 측에서 JavaScript를 다운로드하고 실행할 필요 없이 빠르게 화면을 표시할 수 있습니다.

SEO: 검색 엔진 크롤러는 JavaScript를 실행하지 않거나 실행이 제한적이기 때문에, SSR을 사용하면 검색 엔진에 최적화된 컨텐츠를 제공할 수 있습니다.

일관된 사용자 경험: 서버에서 렌더링된 HTML을 제공하므로, 사용자가 콘텐츠를 빠르게 볼 수 있고, JavaScript 번들 로딩과 실행이 완료된 후에 클라이언트 측에서 추가적인 상호작용을 처리할 수 있습니다.

복잡한 앱에 적합: 데이터가 많은 애플리케이션이나 SEO가 중요한 애플리케이션에 적합합니다.

SSR을 구현하는 대표적인 프레임워크로는 Next.js(React 기반), Nuxt.js(Vue.js 기반) 등이 있습니다.
```

## 1.3 NestJS 설치
> npm i -g @nestjs/cli

> nest new project-name

> nset start --watch

## 1.4 책에서 만들 애플리케이션: 유저 서비스
---
from. sunman
- 환경 변수 설정, 요청 유효성 검사, 인증
- 로깅, 헬스 체크, CQRS, 클린 아키텍쳐, 단위 테스트
---

# CHAP2. 웹 개발 기초 지식

## 2.1 웹 프레임워크
---
from. sunman
- 자주 사용되는 동작을 정해진 방법과 추상화된 인터페이스로 제공
---
```
SPA는 Single Page Application의 약자로, 단일 HTML 페이지로 구성된 웹 애플리케이션을 의미합니다. 아래는 SPA의 주요 특징과 장점입니다:

빠른 로드 시간: 첫 페이지 로드 후 추가적인 페이지 요청 없이 애플리케이션이 동작하므로, 페이지 전환 시 빠른 응답 속도를 보입니다.

향상된 사용자 경험: 페이지 전환 시 전체 페이지를 다시 로드하지 않고 필요한 부분만 갱신하여 부드럽고 일관된 사용자 경험을 제공합니다.

클라이언트 측 라우팅: JavaScript를 사용하여 클라이언트 측에서 라우팅을 처리하므로, 서버 요청 없이도 URL 변경이 가능합니다.

상태 관리: 클라이언트 측에서 애플리케이션 상태를 관리할 수 있으며, Redux나 Vuex 같은 라이브러리를 통해 이를 최적화할 수 있습니다.

SEO 문제: JavaScript를 사용하여 콘텐츠를 렌더링하므로 검색 엔진 최적화에 어려움이 있을 수 있습니다. 이를 해결하기 위해 SSR(Server-Side Rendering)을 함께 사용할 수 있습니다.

SPA를 구현하는 대표적인 프레임워크로는 React, Vue.js, Angular 등이 있습니다.
```
## 2.2 Node.js
- 단일 스레드에서 구돵되는 논블로킹 I/O 이벤트 기반 비동기 방식
- 우리는 팟 하나에 4개의 인스턴스
---
from. sunman
- Nodejs 2009년 릴리즈
- 2008년 크롬 브라우저 자바스크립트 엔진 V8 이후 JS 성능 개선
---
## 2.3 이벤트 루프
- 타이머 > 대기콜백 > 유휴,준비 > 폴 > 체크 > 종료 콜백
---
from. sunman
- 이벤트 루프는 커널에서 가능한 작업은 커널에 이관
#### ✅ 타이머 단계

- `setTimeout`, `setInterval` 과 같은 함수들을 큐에 넣고 실행
- `now - registeredTime >= delta` 인 타이머들이 큐에 들어감

#### ✅ 대기 콜백 단계

- pending 큐에 들어 있는 콜백들은 현재 돌고 있는 루프 이전의 작업에서 큐에 들어온 콜백

#### ✅ 유휴, 중비 단계

- 유휴 단계는 매 틱마다 실행
- 준비 단계는 매 폴링 직전에 실행

---

#### ✅ 폴 단계 (가장 중욯나 단계)

- watch 큐
- 새로운 I/O 이벤트르 ㄹ가져와서 관련 콜백 수행

#### ✅ 체크 단계

- setImmediate의 콜백만을 위한 단계

#### ✅ 종료 콜백 단계

- `close`나 `destroy` 이벤트 타입의 콜백이 처리

### 🎁 [자바스크립트 비동기와 이벤트 루프](https://inpa.tistory.com/entry/%F0%9F%94%84-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A3%A8%ED%94%84-%EA%B5%AC%EC%A1%B0-%EB%8F%99%EC%9E%91-%EC%9B%90%EB%A6%AC)
---
## 2.4 패키지 의존성 관리
- package.json 1.2.3-beta ([Major].[Minor].[Patch]-[label]
- package-lock.json : package.json에 선언된 패키지들이 설치될 떼 정확한 버전과 서로간의 의존성을 표현
## 2.5 타입스크립트
---
from. sunman
- 정적 프로그램 분석
- 함수 타입 (일급 함수)
  - 함수를 변수에 할당
  - 다른 함수의 인수로 함수 전달
  - 함수의 결과로 함수 반환
---
## 2.6 데커레이터
- 횡단 관심사 적용
- 자바 어노테이션과 유사
- 데커레이터 합성
  - 1) 각 데커레이터의 표현은 위에서 아래로 평가(evluate)
  - 2) 그런 다음 결과는 아래에서 위로 함수로 호출(call)
- 클래스 데커레이터
- 메서드 데커레이터
  - 1) 정적 멤버가 속한 클래스의 생성자 함수이거나 인스턴스 멤버에 대한 클래스의 프로토타입
  - 2) 멤버의 이름
  - 3) 멤버의 속성 설명자. PropertyDescriptor 타입을 가짐
- 접근자 데커레이터
- 속성 데커레이터
- 메게변수 데커레이터

---
from. sunman
- 횡단 관심사를 분리, 관점 지향 프로그래밍

---

#### ✅ 인수 없는 데코레이터 기본 예시

```ts
function deco(
  target: any,
  propertyKey: string,
  discriptor: PropertyDescriptor
) {
  console.log("run deco");
}

class TestClass {
  @deco
  test() {
    console.log("run test");
  }
}

const t = new TestClass();
t.test();
```

---

#### ✅ 인수 있는 데코레이터 기본 예시

```ts
function deco(value: string) {
  console.log("run deco");
  return function (
    target: any,
    propertyKey: string,
    discriptor: PropertyDescriptor
  ) {
    console.log(value);
  };
}

class TestClass {
  @deco("HELLO")
  test() {
    console.log("run test");
  }
}

const t = new TestClass();
t.test();
```

---

#### ✅ 데커레이터 합성

1. 각데커레이터는 위에서 아래로 평가
2. 결과는 아래에서 위로 함수를 호출

---

#### ✅ 데커레이터 합성 예시

```ts
function first(value: string) {
  // second
  console.log("first evaluated"); // second
  return function (
    target: any,
    propertyKey: string,
    discriptor: PropertyDescriptor
  ) {
    console.log("first called"); // second
  };
}

class TestClass {
  @first()
  @second()
  test() {
    console.log("run test");
  }
}

// first evaluated
// second evaluated
// second callsed
// first callsed
// run test
```

---

#### ✅ 클래스 데커레이터

```ts
function reportableClassDecorator<T extends {new (...args: any[]): {}}>(constructor:T){
    return class extends constructor [ // 생성자를 리턴
        reportingURL = "http://www.naver.com"
    ]
}

@reportableClassDecorator
class BugReport {
    type="report"
    title: string;
    constructor(t:string){
        this.title = t;
    }
}

const bug = new BugReport("Needs dark mode")
console.log(bug)
// {type: 'report', title: "Needs dark mode", reportingURL: "http://www.naver.com"}
```

---

#### ✅ 메서드 데커레이터

- 갖는 세 개의 인수

  1. 정적 멤버가 속한 클래스의 생성자 함수이거나 인스턴스 멤버에 대한 클래스의 프로토타입
  2. 멤버의 이름
  3. 멤버의 속성 설명자. PropertyDescriptor 타입을 가짐

---

#### ✅ 메서드 데커레이터 예시

```ts
function HandleError() {
  return function (
    target: any,
    propertyKey: string,
    descriptor: PropertyDescriptor
  ) {
    const method = descriptor.value;
    descriptor.value = function () {
      try {
        method();
      } catch (e) {
        // 에러 핸들링 로직 구현
        console.log(e);
      }
    };
  };
}

class Greetor {
  @HandleError()
  hello() {
    throw new Error("Test");
  }
}

const t = new Greetor();
t.hello();
```

---

#### ✅ 접근자 데커레이터

```ts
function Enumerable(enumerable: boolean) {
  return function (target, propertyKey, descriptor) {
    descriptor.enumerable = enumerable;
  };
}

class Person {
  constructor(private name: string) {}

  @Enumerable(true)
  get getName() {
    return this.name;
  }

  @Enumerable(false)
  set setName(name: string) {
    this.name = name;
  }
}

const person = new Person("james");
for (let key in person) {
  console.log(`${key}: ${person[key]}`);
  // name, getName 출력 - setName은 미출력
}
```

---

#### ✅ 속성 데커레이터

- 갖는 두 개의 인수

  1. 정적 멤버가 속한 클래스의 생성자 함수이거나 인스턴스 멤버에 대한 클래스의 프로토타입
  2. 멤버의 이름

---

#### ✅ 속성 데커레이터 예시

```ts
function format(formatString: boolean) {
  return function (target, propertyKey) {
    let value = target[propertyKey];

    function getter() {
      return `${formatString} ${value}`;
    }

    function setter(newVal: string) {
      value = newVal;
    }

    return {
      get: getter,
      set: setter,
      enumerable: true,
      configurable: true,
    };
  };
}

class Greeter {
  @format("Hello")
  greeting: string;
}

const t = new Greeter();
t.greeting = "World";
console.log(t.greeting()); // Hello World
```

---

#### ✅ 매개변수 데커레이터

- 갖는 두 개의 인수

  1. 정적 멤버가 속한 클래스의 생성자 함수이거나 인스턴스 멤버에 대한 클래스의 프로토타입
  2. 멤버의 이름
  3. 매개변수가 함수에서 몇 번째 위치에 선언되었는지를 나타내는 인덱스

---

#### ✅ 매개변수 데커레이터 예시

```ts
import {BadRequestException} from "@nestjs/common"

function MinLength(min: number){
    return funtion (target, propertyKey, parameterIndex){
        target.validators = {
            minLength: function (args: string[]){
                return args[parameterIndex].length >= min
            }
        }
    }
}

function Validate(target, propertyKey, descriptor){
    const method = descriptor.value

    descriptor.value = function(...args){
        Object.keys(target.validators).forEach(key => {
            if (!target.validators[key](args)){
                throw new BadRequestException()
            }
        })
        method.apply(this.args)
    }
}

class User {
    private name: string;

    @Validate
    setName(@MinLength(3) name: string){
        this.name = name
    }
}

const t = new User();
t.setName('123456')
console.log('---')
t.setName('12')
```
---
알아보기
덕타이핑
자바스크립트 원시/참조

# CHAP3. 애플리케이션의 관문: 인터페이스
## 3.1 컨트롤러
- 컨트롤러 : 들어오는 요청을 받고 처리된 결과를 응답ㅎ으로 돌려주는 인터페이스 역할
  - 엔드포인트 라우팅 매커니증을 통해 각 컨트롤러가 받을 수 있는 요청을 분류
### 3.1.1 라우팅
- @Controller 데커레이터 사용
### 3.1.2 와일드카드 사용
- @Get('He*lo') 가능
### 3.1.3 요청 객체
- @Req 데커레이터 사용 : request 내용을 확인할수 있음
### 3.1.4 응답
### 3.1.5 헤더
### 3.1.6 리다이렉션
- @Redirect
### 3.1.7 매개변수
- @Param
### 3.1.8 하위 도메인 라우팅
### 3.1.9 페이로드 다루기

## 3.2 유저 서비스의 인터페이스

# CHAP4. 핵심 도메인 로직을 포함하는 프로바이더
## 4.1 프로바이더
- 비즈니스 로직을 수행하는 역할
- 프로바이더는 service, repository, factory, helper 등 여러가지 형태로 구현
- Nest에서 제공하는 프로바더의 핵심은 의존성 주입(DI)
- @Injectable() 데코레이터로 다른 Nest 컴포넌트에서 주입할 수 있는 프로바이더가 됨
- 별도의 스코프를 지정해 주지 않으면 싱글턴 인스턴스가 생성됨
  - 별도의 스코프?
 
## 4.2 프로바이더 등록과 사용
### 4.2.1 프로바이더 등록
```
@Module({
  imports: [
    MongooseModule.forFeature(models, MongoConnections.SERVICE),
    ElasticSearchUtilModule.forFeature([IndexNames.DEMO]),
  ],
  controllers: [],
  exports: [DemoService],
  providers: [DemoResolver, DemoService, DemoMongodbRepository, DemoElasticsearchRepository, DemoRedisRepository],
})
export class DemoModule {}
```
### 4.2.2 속성 기반 주입
![IMG_2872](https://github.com/user-attachments/assets/274a12bf-bd07-4374-bcc3-6990bae37689)
```
@Inject(ServiceA) private readonly serviceA: ServiceA;
```


