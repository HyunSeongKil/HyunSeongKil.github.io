---
layout: single
title: "[Tech - c#] record vs class"
# categories:[misc]
# tags:[기타]
---

# c#에서 record(레코드) vs class(클래스)

## 결론

- record 키워드는 Immutable(불변) Reference Type 인스턴스를 생성

## 공통점

- 변수 선언, 함수 선언등 가능
- 데이터와 관련 기능을 캡슐화

## 차이점

| 구분    | record         | class       |
| ------- | -------------- | ----------- |
| 값 수정 | 초기화 후 불가 | 언제나 가능 |

## init 키워드

- c# 9.0에서 도입
- 속성을 정의할 때 set 대신에 사용
- 객체가 처음 초기화될때 만 속성을 변경할 수 있음
- init은 해당 속성을 Immutable 속성으로 만듦
- 예)

```c#
public record Person
{
  public string Id {get; init;}
  public string Name {get; init; }
}
```

## with 키워드

- 언제 사용? : record로 생성된 인스턴스에서 일부만 변경하고 싶을 때
- 예)

```c#
Person p1 = new Person
{
  Id = "aha1492",
  Name = "Hyun"
};

Person p2 = p1 with {Id = "gravity"};
```

## record 인스턴스 비교

- 값은 똑같기 때문에 Equals() 결과는 true
- 메모리 주소는 다르기 때문에 ReferenceEuals() 결과는 false
- 예)

```c#
Person p1 = new()
{
  Id = "aha1492",
  Name = "Hyun"
};

Person p2 = new()
{
  Id = "aha1492",
  Name = "Hyun"
};

bool b1 = p1.Equals(p2);  // true
bool b2 = ReferenceEquals(p1, p2);  // false
```
