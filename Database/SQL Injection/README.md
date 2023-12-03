### SQL Injection과 방어 방법에 대해 설명해주세요.

SQL Injection은 공격자가 악의적인 의도를 갖는 SQL 쿼리를 주입하고 실행하여 데이터베이스를 비정상으로 조작하는 공격 기법입니다. </br>
이 기법은 주로 개인정보를 탈취하거나 데이터를 변경할 때 많이 사용됩니다. </br>

SQL Injection의 종류에서는 </br>
논리적인 에러를 이용한 SQL Injection, Union 명령어를 이용한 SQL Injection, </br>
Blind SQL Injection 그리고 Stored Procedure SQL Injection 과 Mass SQL Injection이 있습니다. </br>

이를 대응하고 방어하기 위해선 입력값 검증, Prepared Statement 구문 사용, 그리고 Error Message 감추기 방법이 있습니다. </br>
그 외에도 데이터베이스 사용자에게 최소한의 권한만을 부여하는 Least Privilege 원칙 적용과 Stored Procedure 적용, 그리고 Escape 문자를 사용하여 </br>
특수문자를 필터링하는 Escape 사용이 있습니다.
