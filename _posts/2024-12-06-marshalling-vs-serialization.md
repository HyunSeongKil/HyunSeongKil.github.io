---
layout: single
title: "[Tech - 공통]MarshallingP vs Serialization
# categories:[misc]
# tags:[기타]
---

마샬링과 직렬화는 비슷한 개념이지만 차이점은 존재한다.

마샬링 - 변환하는 과정 자체를 의미. 직렬화보다 큰 개념

- 정의 : 객체의 메모리를 저장하거나 전송할 목적으로 표현방식을 저장 또한 전송에 적합한 데이터 형식으로 변환하는 과정이며 서로 다른 프로그램간에 데이터를 전달할 필요성이 있는 경우 사용
- .NET에서는 참조 마샬링(MBR), 값 마샬링(MBV)을 지원
  직렬화 - Byte Stream으로의 변환을 의미. 마샬링중 하나의 기술
- 정의 : 객체의 상태를 저장하기 위해 Byte Stream으로 변환하는 작업을 의미하며 객체에 저장된 데이터를 Stream에 쓰기 위해서 연속적 데이터로 변환하는 것

## Reference

- https://ssvip.tistory.com/47
