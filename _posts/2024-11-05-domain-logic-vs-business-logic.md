---
layout: single
title: "[Tech - 공통]도메인 로직 vs 비즈니스 로직"
# categories:[misc]
# tags:[기타]
---

# domain logic vs business logic

| 구분       | domain logic                             | business logic |
| ---------- | ---------------------------------------- | -------------- |
| 차이       | 비즈니스에 중요한 의사결정을 내리는 코드 | 그 주변 코드   |
| 코드(로직) | 변경되지 않음                            | 변경될 수 있음 |

## 설명

- 은행 어플리케이션을 예로 들어 보겠음
- **도메인 로직**
  - 1만원을 출금하려고 함. 통장 잔액이 1만원보다 많으면 출금 가능, 그렇지 않으면 출금 불가
    - 어느 시대, 어느 국가를 막론하고 이 로직은 변하지 않음(잔액보다 많은 돈을 출금시켜 주는 국가가 있나???(마이너스 통장 제외) 그럼, 난 그 국가로 이민가겠음)
- **비즈니스 로직**
  - 통장 잔액 정보는 Open API를 이용하여 클라우드 어딘가에 저장되어 있는 정보를 조회
    - Open API를 이용할 수도 있고, Socket을 이용할 수도 있고, batch job으로 전날 처리해 놓을 수도 있고, ... 다양한 케이스 존재. 필요에 따라 선택/구축하면 됨
    - 정보는 클라우드에 저장될 수도 있고, 데이터베이스에 저장될 수도 있고, 그냥 로컬에 파일로 저장할 수도 있고, ... 다양한 케이스 존재. 필요에 따라 선택/구축하면 됨
- 차이점이 보이는가?

## 로직 분리 이유

- 관심사의 분리
- 유지보수성 향상
- unit test 용이성 향상
- 응집도 향상

## 어떤 로직의 unit test가 어렵다면???

- domain logic과 business logic이 섞여 있을 가능성 높음
- logic을 잘 분리해야 함(물론, 말처럼 쉽지는 않을 것임)

## 참고

- 클린 아키텍처
