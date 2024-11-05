---
layout: single
title: "[Tech - js]Map vs Set"
# categories:[misc]
# tags:[기타]
---

# Map vs Set

| 구분     | Map                    | Set                             |
| -------- | ---------------------- | ------------------------------- |
| 정의     | 키/값쌍의 모음(콜렉션) | 중복되지 않는 값의 모음(콜렉션) |
| 특징     | 키는 중복되지 않음     | 값은 중복되지 않음              |
| 출력순서 | 입력 순서와 동일       | 입력 순서와 동일                |

## Map 정의

- Map objects are collections of key/value pairs where both the keys and values may be arbitrary ECMAScript language values. A distinct key value may only occur in one key/value pair within the Map’s collection. Distinct key values are discriminated using the SameValueZero comparison algorithm. 출처: [ECMAScript 2015 Language Specification](https://262.ecma-international.org/6.0/#sec-map-objects)
- Map Object는 임의의 ECMAScript 언어 값일 수 있는 키/값 쌍의 모음(콜렉션)임. 고유의 키값은 Map의 모음안에서 유일한 값임(중복되지 않음). 고유의 키값은 SameValueZero 비교 알고리즘을 사용하여 차별되어 짐
- 요약 : 키/값 쌍의 모음. 키는 중복되지 않음

## Set 정의

- Set objects are collections of ECMAScript language values. A distinct value may only occur once as an element of a Set’s collection. Distinct values are discriminated using the SameValueZero comparison algorithm. 출처: [ECMAScript 2015 Language Specification](https://262.ecma-international.org/6.0/#sec-set-objects)
- Set Object는 ECMAScript 언어 값의 모음임. 구분된 값은 Set의 모음(콜렉션)안에서 유일한 값임(중복되지 않음). 유일값은 SameValueZero 비교 알고리즘을 사용하여 차별되어 짐
- 요약 : 모음의 값은 중복되지 않음

## Map vs 다른 언어

| 구분      | c#                                                                      | java                                                                                                                              |
| --------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 유사      | Dictionary or Hashtable Class                                           | Map Interface                                                                                                                     |
| 출력 순서 | 출력 순서는 입력 순서와 같지 않음<br/>OrderedDictionary: 키 순서로 출력 | 구현체에 따라 다름<br/> HashMap: 출력 순서 미보장<br/> LinkedHashMap : 입력 순서와 출력 순서 같음음<br/> TreeMap : 키 순서로 출력 |

## Set vs 다른 언어

| 구분      | c#                                                              | java                                                                                                                            |
| --------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| 유사      | HashSet Class                                                   | Set Interface                                                                                                                   |
| 출력 순서 | 출력 순서는 입력 순서와 같지 않음<br/>SortedSet: 값 순서로 출력 | 구현체에 따라 다름<br/> HashSet: 출력 순서 미보장<br/> LinkedHashSet : 입력 순서와 출력 순서 같음<br/> TreeSet : 키 순서로 출력 |
