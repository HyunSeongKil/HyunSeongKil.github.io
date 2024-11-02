---
layout: single
title: "[Tech - 공통]js에서 array vs []"
# categories:[misc]
# tags:[기타]
---

# js에서 Array vs []

- 결론 : 일반적으로 []이 간단한고 안전

## js에서 배열을 선언하는 방법

- Array()
- []

## 성능

- new Array()는 배열의 크기를 미리 정의할 수 있어 성능에 도움이 됨
- []는 동적으로 할당하기에 성능이 약간 떨어질 수 있음

## 안전성

- []이 더 안전함
- Array() 생성시 인수로 초기 배열값을 숫자로 전달할 수 있음. 숫자가 아닌 다른 값 전달시 예기치 않은 결과 초래할 수 있음

```
예)
var arr1 = new Array(5) // 5개의 배열 생성
var arr2 = new Array('5') // 문자 5를 가지는 배열 생성
```
