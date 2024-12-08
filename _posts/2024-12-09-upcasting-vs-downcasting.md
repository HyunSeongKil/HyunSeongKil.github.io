---
layout: single
title: "[Tech - 멀티미디어]RTP vs RTSP 
# categories:[misc]
# tags:[기타]
---

# Upcasting vs Downcasting

| 구분 | upcasting                                    | downcasting                                  |
| ---- | -------------------------------------------- | -------------------------------------------- |
| 요약 | 하위 클래스 객체를 상위 클래스 타입으로 변환 | 상위 클래스 객체를 하위 클래스 타입으로 변환 |
| 특징 | 항상 안전, 명시적인 케스팅 불필요            | 명시적인 케스팅 필요, 항상 안전하지 않음     |

## casting

- 정의

  - 프로그래밍 언어에서 하나의 데이터 타입을 다른 데이터 타입으로 변환하는 것
  - 서브타입의 인스턴스를 수퍼타입의 변수로 접근하는 것
  - 자식(서브, 하위) 클래스가 부모(수퍼, 상위) 클래스 타입으로 캐스팅 되는 것

- 개념도
  ![개념도](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FkOsig%2FbtrLLXRW1cE%2FV9rilSShuWugrkaiYkbQYK%2Fimg.png)
  ※ 출처 : https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EC%97%85%EC%BA%90%EC%8A%A4%ED%8C%85-%EB%8B%A4%EC%9A%B4%EC%BA%90%EC%8A%A4%ED%8C%85-%ED%95%9C%EB%B0%A9-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0

## Upcasting

- 정의
  - 파생된 클래스 참조나 객체를 베이스 클래스 참조로 변환하는 과정/절차
  - 서브타입 인스턴스를 참조하는 수퍼타입 변수를 재참조 하는 것
  - 부모 클래스가 자식 클래스 타입으로 캐스팅되는 것
- 예시

```csharp
public class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog barks");
    }
}

public class Program
{
    public static void Main()
    {
        Dog myDog = new Dog();
        Animal myAnimal = myDog; // Upcasting
        myAnimal.Speak(); // Outputs: Animal speaks
    }
}
// ※ 출처: windows copilot
```

## Downcasting

- 정의: 베이스 클래스 참조나 객체를 파생된 클래스 참조로 변환하는 과정/절차
- 예시

```csharp
public class Animal
{
    public void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog barks");
    }
}

public class Program
{
    public static void Main()
    {
        Animal myAnimal = new Dog(); // Upcasting
        Dog myDog = (Dog)myAnimal; // Downcasting
        myDog.Bark(); // Outputs: Dog barks
    }
}
// ※ 출처: windows copilot
```
