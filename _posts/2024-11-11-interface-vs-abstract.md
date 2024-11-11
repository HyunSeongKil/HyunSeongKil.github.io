---
layout: single
title: "[Tech - c#]interface vs abstract class"
# categories:[misc]
# tags:[기타]
---

# interface vs abstract class

| 구분          | interface                            | abstract class                                  |
| ------------- | ------------------------------------ | ----------------------------------------------- |
| 정의          | 상호간의 약속이다                    | 직접 인스턴스화하지 마세요. 자식에게 양보하세요 |
| modifier      | 모든 것이 public                     | 다양하게 사용 가능. 기본값은 private            |
| overriding    | 상속받는 클래스에 overriding을 강제  |                                                 |
| 구현부        | 없음/있음                            | 있음                                            |
| 상속          | 클래스는 여러개의 interface상속 가능 | 클래스는 1개의 클래스만 상속 가능               |
| 인스턴스 생성 | 불가                                 | 불가                                            |
| upcasting     | 가능                                 | 가능                                            |

## interface

### 인스턴스 생성은 할 수 없지만 참조는 만들 수 있다.

```c#
interface IAnimal
{
  void Bark();
}

class Dog : IAnimal
{
  public void Bark()
  {
    Console.WriteLine("멍멍");
  }
}

class Cat : IAnimal
{
  public void Bark()
  {
    Console.WriteLine("야옹");
  }
}


IAnimal animal = new Dog();
animal.Bark();  // 멍멍

```

### 다른 interface를 상속할 수 있다.

```c#
interface IBicycle
{
  void Riding();
}

interface IMotercycle : IBicycle
{
  void TurnOnTheEngine();
}

```

#### 다른 interface를 상속하는 이유

- 위의 예시에서... 다른 코드에서 이미 IBicycle을 사용하고 있는중에 IBicycle에 메소드를 추가하게 되면 이미 사용중인 클래스에서는 모두 신규로 추가된 메소드를 구현해야 함(기존 코드 수정해야 함)
- 해결 방안
  - 구현부를 가지는 interface 사용
  - interface 참조로 upcasting시에만 사용 가능
  - 이런 기능은 java에도 존재. default keyword 참고

```c#
// 기존
interface IFace
{
  void Method1();
}

class Face1 : IFace
{
  public void Method1()
  {
    ...
  }
}

class Face2 : IFace
{
  public void Method1()
  {
    ...
  }
}

// 구현 메소드 사용
interface IFace
{
  void Method1();
  void Method2()
  {
    Console.WriteLine("추가된 메소드");
  }
}

class Face1 : IFace
{
  public void Method1()
  {
    ...
  }

  // 여기서 Method2() 구현하지 않아도 됨
}

class Face2 : IFace
{
  public void Method1()
  {
    ...
  }

  // 여기서 Method2() 구현하지 않아도 됨
}
```

<br/>

- 사용 예시 - interface 참조

```c#
IFace face = new Face1();
face.Method1(); // 호출 성공
face.Method2(); // 호출 성공
```

<br/>

- 사용 예시 - class 참조

```c#
Face1 face = new Face1();
face.Method1(); // 호출 성공
face.Method2(); // 컴파일 오류. Face1 class에는 Method2() 없음
```

## abstract class

### 특징

#### abstract method를 가질 수 있다.

- 상속받는 class는 반드시 abstract method를 구현해야 한다.

#### method의 기본 modifier(접근한정자)는 private이다.

- 이상하다. abstract method는 상속받는 class에서 반드시 구현해야 하는데, 기본값이 private이라니...
- 그래서, 컴파일러는 abstract method의 경우 public, protected, internal, procted internal중 하나로 설정될 것을 강제한다.

#### 상속

- abstract class는 다른 abstract class를 상속할 수 있다. 이 경우에는 abstract method를 구현하지 않아도 된다.

---

BUT,
여전히 궁금하다.
그래서, abstract class는 왜 사용하는건데???
