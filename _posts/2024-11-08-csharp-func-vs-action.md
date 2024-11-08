---
layout: single
title: "[Tech - c#]Func vs Action"
# categories:[misc]
# tags:[기타]
---

# c#에서 Func vs Action

| 구분     | Func                   | Action                 |
| -------- | ---------------------- | ---------------------- |
| 공통점   | 미리 정의된 delegate   | 미리 정의된 delegate   |
| 리턴값   | 있음                   | 없음                   |
| 매개변수 | 0~16개                 | 0~16개                 |
| 유사     | java의 Function과 유사 | java의 Consumer와 유사 |

## 대리자(delegate)

- 특정 메서드 시그니처(입력 매개변수와 반환 타입)와 일치하는 메서드를 참조할 수 있는 타입입니다.
- c 및 c++의 함수 포인트처럼 메서드를 안전하게 캡슐화하는 형식입니다. but, 형식 안전성(type-safe), 보안성(secure)이 더 좋습니다.
- 명명된 메서드나 무명/익명(anonymous) 메서드를 캡슐화하는 데 사용할 수 있는 참조 형식입니다.
- c#에서는 메소드를 매개 변수로 전달할 수 없습니다만, 이를 가능하게 하는 것이 대리자입니다.
- 대리자를 통해 메서드(함수)를 변수처럼 다룰 수 있습니다.

## 대리자 사용 이유

※ 대리자 사용 이유는 Func, Action 사용 이유와 같습니다.

- 콜백 메서드(Callback Methods)

  - 대리자는 매개 변수로 다른 메서드에 전달되는 것에 사용되어 집니다.
  - 이것은 콜백 메서드를 정의하는데 유용합니다.

- 이벤트 핸들링(Event Handling)

  - 대리자는 이벤트의 기반이 됩니다.
  - 이벤트를 정의할 때 본질적으로는 대리자는 정의하는 것입니다.

- 무명 메서드와 람다 표현식(Anonymous Methods and Lambda Expressions)

  - 코드를 보다 간결하고 읽기 쉽게 만듭니다.
  - 특히 LINQ 쿼리에서 유용합니다.

- 유연성과 디커플링(Flexibility and Decoupling)
  - 코드 분리하는 방법을 제공하는데, 깔끔하고 모듈식 설계를 잘 할 수 있도록 합니다.

## Func

- 미리 정의된 대리자입니다.
- 리턴값이 반드시 존재해야 합니다.
- 입력 매개 변수를 최대 16개까지 사용할 수 있습니다. (실제로 16개의 매개 변수를 사용하는 개발자가 있는지 궁금하네요.)

### 예시(Examples)

- 입력 매개 변수가 없는 경우

```c#
Func<int> getNumber = () => 42;
Console.WriteLine(getNumber()); // output : 42
```

- 입력 매개 변수가 1개인 경우

```c#
Func<string, int> getStringLength = s => s.Length;
Console.WriteLine(getStringLength("hello world"));  // 11
```

## Action

- 미리 정의된 대리자입니다.
- 리턴값이 없는게 Func와의 차이점입니다.
- 입력 매개 변수를 최대 16개까지 사용할 수 있습니다. (실제로 16개의 매개 변수를 사용하는 개발자가 있는지 궁금하네요.)

### 예시(Examples)

- 입력 매개 변수가 없는 경우

```c#
Action writeNumber = () => Console.WrtieLine("42");
writeNumber();
```

- 입력 매개 변수가 1개인 경우

```c#
Action<string> writeStringLength = s => Console.WriteLine(s.Length);
writeStringLength("hello world");
```
