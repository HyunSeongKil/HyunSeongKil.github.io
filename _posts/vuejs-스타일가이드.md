
# vuex convension
  모듈 이름은 짧고 간결할 수록 좋으며, 되도록이면 이름만으로 기능을 유추할 수 있어야 함
  
## State
  - 간략하게
  - 중첩되지 않게
  - 단어 구분은 언더바로
  - 예)
  ```
    categories_map
    selected_items
  ```    
    
## Getters
  - mutations를 제외하고 모든 정보는 getter를 통해 읽혀져야 함(actions 포함)
  - 데이터 타입이 boolean인 경우 is + 낙타법
  - 그 외에는 get + 낙타법 사용
  - 언더바나 하이픈은 사용하지 않음
  - 예)
  ```
    isUserLogined
    getUser
    getCurrentProduct
  ```
  
## Actions
  - 서버에서 데이터를 fetch해 오거나, 현재 모듈의 상태를 변경시키거나 하는 '움직임'을 담당
  - 대부분의 경우 Promise를 리턴함(비동기 처리)
  - 낙타법 사용
  예)
  ```
    fetchProduct
    findUser
    setUserId
    addProductId
  ```

## Mutations
  - state의 값을 변경할때는 하앙 mutation을 사용
  - action과는 동기식으로 사용하기 때문에 절대 Promise를 리턴하면 안됨
  - 비즈니스 로직을 구현하면 안됨
  - 가능하면 내부 action을 통해 호출되도록 함 (외부에서 호출하지 않음)
    - 참고 : https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fk.kakaocdn.net%2Fdn%2Fbyx9LD%2FbtqzP3PEjw1%2FsCAQXxSA04ykldfSgfvvGk%2Fimg.png
    - vuejs에서는... component에서 직접 mutation호출을 허용하고 있지만... 단순 처리가 아니라면 action을 통해 호출하는것을 추천함
  - 네이밍은 상수 케이스(모두 대문자, 단어 구분은 언더바)
  - 3가지 경우가 존재
    - SET_XXX : 대부분의 경우로 object, array를 쓴다(write)
    - ADD_XXX : array, map에 object를 추가한다
    - REMOVE_XXX : add 의 반대로 array, map에서 object를 제거한다
  - 예)
  ```
    ADD_PRODUCT
    ADD_USER
    SET_PRODUCT
    REMOVE_PRODUCT
  ```

# 출처
  2022-11-15
  https://velog.io/@nuxt/Vuex-%EB%AA%85%EB%AA%85-%EA%B7%9C%EC%B9%99
