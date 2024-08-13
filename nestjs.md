# NestJS로 배우는 백엔드 프로그래밍

# CHAP1. Hello NestJS
## 1.1 NestJS의 장점
- CQRS, 인터셉터, 미들웨어

## 1.2 Express가 좋을까, NestJS가 좋을까

## 1.3 NestJS 설치
> npm i -g @nestjs/cli

> nest new project-name

> nset start --watch

## 1.4 책에서 만들 애플리케이션: 유저 서비스

# CHAP2. 웹 개발 기초 지식

## 2.1 웹 프레임워크
## 2.2 Node.js
- 단일 스레드에서 구돵되는 논블로킹 I/O 이벤트 기반 비동기 방식
## 2.3 이벤트 루프
- 타이머 > 대기콜백 > 유휴,준비 > 폴 > 체크 > 종료 콜백
## 2.4 패키지 의존성 관리
- package.json 1.2.3-beta ([Major].[Minor].[Patch]-[label]
- package-lock.json : package.json에 선언된 패키지들이 설치될 떼 정확한 버전과 서로간의 의존성을 표현
## 2.5 타입스크립트
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

# CHAP3. 애플리케이션의 관문: 인터페이스