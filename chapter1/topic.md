## topic 

 - 다양한 데이터가 들어갈 수 있는 공간
 - 데이터베이스 테이블과 비슷한 원리 

![스크린샷 2023-10-26 오전 1 45 51](https://github.com/yunhwane/kafka-example/assets/147581818/6eade41d-7412-4d17-ba15-b3c0516d74ff)


## 내부 구조 
![스크린샷 2023-10-26 오전 1 47 21](https://github.com/yunhwane/kafka-example/assets/147581818/25e60cc4-20ab-471f-9bfd-3fa5b8403898)
- 토픽 데이터에 따라 명확한 이름을 통한 유지보수
- 하나의 파티션은 여러개의 파티션으로 구성됨


## QUEUE
![스크린샷 2023-10-26 오전 1 50 38](https://github.com/yunhwane/kafka-example/assets/147581818/abda8516-aa4d-419e-b90e-6b8976041989)
- Consumer가 record들이 삭제되지 않음
- 남은 데이터는 새로운 consumer가 붙었을 때 컨슈머 그룹이 다를 경우, auto.offset.reset = earliest 일 경우 동일 데이터를 두번 사용할 수 있음

## topic의 파티션 선택
![스크린샷 2023-10-26 오전 1 53 20](https://github.com/yunhwane/kafka-example/assets/147581818/73ef1135-0d60-4e9e-869c-a8b45db891b3)
1. 키가 null 이고 기본 파티셔너 사용할 경우 Round robin(파티션 0 -> 1 -> 0 -> 1)
2. 키가 있고, 기본 파티셔너 사용할 경우 키의 해시값을 구하고, 특정 파티션에 할당

## 파티션을 늘리는 이유 ?
- 데이터 처리를 분산시킬 수 있는 장점이 있기 때문
- 파티션을 늘리는 건 가능하지만 파티션을 줄일 수 없음

## 파티션의 record는 언제 삭제되는가?
- log.retention.ms : 최대 record 보존 시간
- log.rentention.byte : 최대 record 보존 크기
- 적절하게 데이터를 삭제하도록 할 수 있음


  
