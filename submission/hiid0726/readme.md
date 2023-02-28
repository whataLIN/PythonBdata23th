# 이영미
*SI는 대부분 데이터베이스 중심 프로그래밍을 합니다.
뭔가 그럴듯한 이름을 붙이자면 Database Driven Development 입니다.
하지만 D.D.D. 라는 용어는 Domain Driven Development 와 약자가 동일하기도 하고, 사실 아무도 Database Driven Development 라고 부르지는 않습니다.
대신 현업에서는 "쿼리가 전부다" 라는 말은 많이 합니다.
데이터베이스 중심 프로그래밍이란 모든 비지니스 로직이 데이터베이스에 녹아있는 것 을 말합니다.

*자바 스프링을 쓰기는 하지만, 실제로 스프링에서는 거의 아무런 처리도 하지 않습니다.
그저 컨트롤러를 만들고, 서비스 인터페이스와 서비스 구현체를 습관적으로 연결하고, DAO를 호출한 다음, 마이바티스 XML에 쿼리를 작성합니다.
복잡한 비지니스 로직은 프로시져에 작성합니다.

*그래서 SI를 오래하신 분들은 왜 프로그램 설계가 필요한지 이해를 못하시는 분들도 많습니다.
ERD 를 보고 데이터베이스 스키마에 맞춰서 CRUD 연산만 하면 되니까요.
이렇게 데이터베이스 중심 프로그래밍을 하는 이유는 요구사항이 자주 변하기 때문입니다.
혹은 요구사항이 변하지 않는 프로젝트라고 하더라도, 많은 요구사항 변경을 경험했기에 이런 형태의 개발이 몸에 밴 것입니다.

조금 더 자세히 말해보겠습니다.

요구사항이 변경되면 높은 확률로 데이터베이스의 스키마가 변경되어야 합니다. 컬럼 한두개 추가로 끝나면 좋은데 외부 키(Foreign Key)로 연결된 관계(Relation)를 변경해야 하거나, 혹은 원래 연관관계가 없는 데이터를 강제로 연결해야 하는 때도 있습니다. 반대로 연관관계를 끊어야 할 수도 있지요. 따라서 데이터베이스 스키마 변경은 필수 가 됩니다.
만약에 비즈니스 로직이 자바 소스 코드에 녹아있다면, 자바 소스코드도 변경되어야 합니다.
DB 테이블과 1:1로 매핑되는 V.O(Value Object) 객체가 있다고 한다면 테이블 구조가 변경될 때마다 V.O 객체도 수정해야 합니다.
수정은 그렇다고 치더라도 자바 코드는 한번 변경되면 다시 빌드하고 배포하기가 꽤 번거롭습니다.
만약 운영 환경에도 함께 배포해야 한다면 문제는 더 커집니다.

readme.md는 폴더의 설명서이다.