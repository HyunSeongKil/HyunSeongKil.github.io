---
layout: single
title: "[Tech - 공통]Helper class vs Utility class"
# categories:[misc]
# tags:[기타]
---

# Helper class vs Utility class

| 구분       | Utility                                           | Helper                              |
| ---------- | ------------------------------------------------- | ----------------------------------- |
| 공통점     | 편의성 제공. core 기능 아님                       | 편의성 제공. core 기능 아님         |
| 생성자     | 존재                                              | 미존재(외부에서 인스턴스 생성 불가) |
| 인스턴스화 | 가능. 여러 개의 Helper class의 인스턴스 존재 가능 | 불가능                              |
| 메소드     | 모든 메소드가 정적이지 않음                       | 모두 정적 메소드                    |

## Helper class

- [위키피디아 정의](https://en.wikipedia.org/wiki/Helper_class)
- Helper class의 인스턴스는 Helper Object로 불림

## Utility Class

- helper class의 특별한 경우(special case)

※ 참고

- https://minsone.github.io/programming/what-is-helper-class
