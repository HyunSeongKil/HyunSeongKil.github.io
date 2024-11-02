---
layout: single
title: "[Tech - c#] struct vs class"
# categories:[misc]
# tags:[기타]
---

# c#에서 struct(구조체) vs class(클래스)

## 공통점

- 변수 선언, 함수 선언등 가능
- 데이터와 관련 기능을 캡슐화

## 차이점

| 구분        | struct     | class          |
| ----------- | ---------- | -------------- |
| 메모리 할당 | stack      | heap           |
| 초기화      | 없음       | new()          |
| type?       | value type | reference type |
| GC          | N/A        | 대상           |
| 상속        | 불가       | 가능           |

## 언제 struct를 사용하면 좋을까?

- 인스턴스 크기가 16바이트 이하일 때
- 기본 형식(int, double, ...)과 유사한 단일 값을 사용할 때
- 반복문 안에서 임시로 값 할당할 때?
  - stack 메모리 사용하기 때문에 빠름
  - scope 끝나면 자동으로 stack 메모리의 값 해제됨

### 기타

- 굳이 heap에 할당하지 않아도 되는건 stack 메모리에 저장하면 성능 향상 있음
- stack 메모리는 용량 한계 때문에 저장 제한 있음
