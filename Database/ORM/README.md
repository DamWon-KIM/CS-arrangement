### ORM의 사용 이유와 장단점

ORM : Object Relational Mapping '객체로 연결을 해준다'는 의미 </br>

어플리케이션과 데이터베이스 연결 시 SQL언어가 아닌 어플리케이션 개발언어로 데이터베이스를 접근할 수 있게 해주는 Framework
* SQL문법 대신 어플리케이션의 개발언어를 그대로 사용할 수 있게 함으로써, 개발 언어의 일관성과 가독성을 높여준다
  * django ORM
  * Hibernate
  * EclipseLink
  * DataNucleus
```
  자바 ORM 기술에 대한 표준 사양
  [spring에 해당하는 ORM : JPA] - 객체와 데이터베이스 테이블 간의 매핑을 처리
```
장점
1. <mark>**추상화**</mark> </br>
   객체지향적인 코드로 인해 더 직관적이고 로직에 집중할 수 있도록 도와준다.
    * SQL문이 아닌 클래스의 메서드를 통해 데이터베이스를 조작할 수 있으므로 개발자가 객체 모델만 이용해서 프로그래밍을 하는 데 집중할 수 있다.
    * 객체마다 코드를 별도로 작성하기 때문에 코드의 가독성이 높아진다.
    * SQL의 절차적이고 순차적인 접근이 아닌 객체지향적인 접근으로 인해 생산성을 높여준다.
    * 선언문, 할당, 종료 같은 부수적인 코드가 없거나 줄어든다.
      
2. <mark>**유지보수**</mark> </br>
   재사용 및 유지보수의 편리성이 증가한다.
    * ORM은 독립적으로 작성되어 있고, 해당 객체들을 재활용할 수 있다.
    * 매핑 정보가 명확하여, ERD를 보는 것에 대한 의존도를 낮출 수 있다.

3. <mark>**데이터베이스의 독립성**</mark> </br>
   DBMS에 대한 종속성이 줄어든다.

4. <mark>**생산성**</mark> </br>
   SQL 쿼리를 직접 작성하지 않아도 된다.
</br>
</br>

단점
1. <mark>**복잡성**</mark> </br>
   완벽한 ORM으로만 서비스를 구현하기가 어렵다.
   * 사용하기는 편하지만 설계는 매우 신중하게 해야한다.
   * 프로젝트의 복잡성이 커질 경우, 난이도 또한 올라갈 수 있다.
   * 일부 자주 사용되는 대형 쿼리는 속도를 위해 SP를 쓰는 등 별도의 튜닝이 필요한 경우가 있다.
   * DBMS의 고유 기능을 이용하기 어렵다.
     
2. <mark>**성능**</mark> </br>
   프로시저가 많은 시스템에선 ORM의 객체 지향적인 장점을 활용하기 어렵다.
   * 이미 프로시저가 많은 시스템에선 다시 객체로 바꿔야 하며, 그 과정에서 생산성 저하나 리스크가 많이 발생할 수 있다.


[참고사이트](https://eun-jeong.tistory.com/31)
[참고사이트2](https://www.gdschongik.com/backend-study/subject/6)
