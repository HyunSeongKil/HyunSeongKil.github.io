# DTO(Data Transfer Object)
- 계층간 데이터 교환을 위한 객체 (Layer간 통신 용도로 오고가는 객체)
- 비즈니스 로직 없음
- 순수한 데이터 객체
- getter/setter만 존재
- setter존재하는 경우 가변 객체로 활용
- setter없는 경우 불변 객체로 활용(생성자를 이용하는 경우)
- 
- toEntity() 메서드를 통해 DTO에서 필요한 부분을 이용하여 Entity로 생성
- JSON 직렬화에 사용됨


# VO(Value Object)
- 값 자체를 표현하는 객체
- VO는 DTO와 동일한 개념이지만 read only속성을 갖음(setter 없음)
- VO는 특정한 비즈니스 값을 담는 객체
- 값 비교를 위해 equals(), hashCode() 오버라이딩 필요


# Entity Class
- 실제 DB의 테이블과 매칭되는 클래스
- @Entity, @Column, @Id등을 이용
- Domain Logic만 가지고 있어야 하고 Presentation Logic가지고 있으면 안됨
- DB의 테이블과 1:1로 매핑
- 테이블에 존재하는 컬럼만 필드로 가져야 함
- setter가 없어야 함(∵ setter가 있다는 것은 불편하지 않다는 것이 됨. 객체의 불변성 보장을 위해)
- setter대신 생성자(Constructor) 또는 빌더(Builder)를 사용
- EntityManager에 의해 생명주기(LifeCycle) 관리됨
- 비즈니스 로직 가질 수 있음


# Entity Class와 DTO를 분리하는 이유
- View Layer와 DB Layer의 역할을 철저하게 분리
- Domain Model내에 Presentation을 위한 필드나 로직을 추가하는 경우, 모델링의 순수성을 깨지게 함
- DTO는 Domain Model을 복사한 형태로, 다양한 Presentation Logic을 추가한 형태로 사용
- Domain Model은 Persistent만을 위해 사용


