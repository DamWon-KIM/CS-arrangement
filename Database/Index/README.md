### 인덱스란 무엇이고 장점과 단점은 무엇입니까?

인덱스란, 추가적인 쓰기 작업과 저장 공간을 활용하여 데이터베이스 테이블의 검색 속도를 향상시키기 위한 자료구조입니다. </br>
일반적으로, WHERE 조건절과 일치하는 열을 빨리 찾기 위해 사용하는데, </br>
```
장점은
테이블 조회 속도가 향상되고,
Search 시 Disk에서 record File을 읽어와야 하는데 Index file을 이용하여 읽어오는 용량을 줄일 수 있다는 점이 있습니다.
```

```
반면 단점의 경우, 
Index된 Filed에서 Data를 업데이트 하거나, Record를 추가 또는 삭제시 성능이 떨어지는 점,
인덱스 파일이 데이터베이스 공간을 차지해서 추가적인 공간이 필요해진다는 점입니다.
  * DB의 10퍼센트 내외의 공간이 추가로 필요합니다.
```
