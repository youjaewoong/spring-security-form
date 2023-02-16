# spring-security-form

InMemoryUser를 생성하여 role을 부여하여 인증/인가 테스트를 기본적으로 진행 할 수 있는  form 인증 방식의 기본 구성 프로젝트 입니다.

#### [SecurityConfig](https://github.com/youjaewoong/spring-security-form/blob/master/src/main/java/com/form/security/SecurityConfig.java)
```
설정 방식에 대한 구성을 기술하였습니다.
 - InMemoryUser 구성
 - 유저별 인가 정책
 - 로그인 인증 정책
  - 로그인 성공 후 핸들러
  - 로그인 실패 후 핸들러
 - 동시 세션 제어
 - 세션 고정보호
 - 세션 정책
 - 로그아웃 처리
 - rememberMe
 - 인증/인가 예외처리
 - throlad local 저장 전략 처리
```
```
throlad local 저장 전략 처리
   @Async를 사용한 서비스를 호출하는 경우
   쓰레드가 다르기 때문에 SecurityContext를 공유받지 못한다.
   SecurityContextHolder.setStrategyName(SecurityContextHolder.MODE_INHERITABLETHREADLOCAL);
   SecurityContext를 자식 쓰레드에도 공유하는 전략.
   @Async를 처리하는 쓰레드에서도 SecurityContext를 공유받을 수 있다
```
