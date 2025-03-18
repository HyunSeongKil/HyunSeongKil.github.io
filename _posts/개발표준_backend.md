# 개발표준 - backend

- author : HyunSeongKil
- since : 2024-12-06

## "팀으로 개발한다면 팀 코드 스타일 반드시 필요"

### 로깅

- aop or filter(java) or interceptor(java)로 해결
- 로그인/아웃 로그는 반드시 별도 테이블에서 관리

### 사용자 정보 관리

- 개인정보는 암호화해서 디비에 저장
- 비번 변경 이력 관리
- 비번은 반드시 hash function의 결과물을 디비에 저장(512bit or 1024bit)
- 주기적으로 비번 변경할 수 있도록 사용자에게 alert
- 사용자가 입력하는 아이디를 PK로 사용하지 않음

### MVC(Model, View, Controller) 적용

```
// 기본 디렉터리 구조
...
  - web
  - service
    - impl
  - repository
  - entity
  - dto

```
