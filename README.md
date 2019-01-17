# DB-Study
DB 공부를 위한 Repository


# 1. index를 통한 DB 성능 향상
## 1) Index란?
- DB의 데이터 검색 속도 향상을 위해서 기존의 모든 record를 검색해서 찾아내는 방식이 아닌 index table을 별도로 둠으로 데이터 접근을 index를 통해 빠르게 하도록 한다. 
- ex) SELECT bookname from library where id="U231"일 때 모든 record에서 U231을 찾겠지만 index table을 이용하면 모든 데이터를 찾아보는 게 아니라 index 위치에서 데이터를 가져오기만 하면된다. - 엄청 빨라지겠군..
- index 생성 시 고려할 점 
  - 무조건 index 붙인다고 다 좋은 것은 아니다, 새로운 데이터 추가시 또 불필요한 index는 오히려 검색 속도를 fullscan(전체 찾아 보며 맞는 값 가져오는거)보다 안좋게함, 또 추가적 데이터 베이스 공간 차지 문제 등이 생김
  - 적잘한 index 사용이 중요함, 재작성 작업이 많은 경우 index 설정을 해놓으면, 그때 그때 index도 바꿔야하기에 안좋음
  - SELECT를 향상하는 것이지 UPDATE나 INSERT DELETE 등은 향상 효과 없음 오히려 더 작업 생김(index에 대해)
