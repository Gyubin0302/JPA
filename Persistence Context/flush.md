### flush
  - 영속성 컨텍스트의 변경내용을 데이터베이스에 반영
  - flush 발생시
    - entity manager의 entity 변경 감지가 되면 수정된 entity를 쓰기 지연 SQL 저장소에 등록
    - 쓰기 지연 SQL 저장소의 쿼리를 데이터베이스에 전송(등록, 수정, 삭제)
  - 영속성 컨텍스트를 flush하는 법
    - em.flush();
    - 트랙잭션 커밋 : flush 자동 호출
    - JPQL 쿼리 실행 : flush 자동 호출
  - flush mode
    - FLushModeType.AUTO : 커밋이나 쿼리를 실행할 때 flush(default)
    - FlushModeType.COMMIT : 커밋할 때만 flush
  - flush는 영속성 컨텍스트를 비우지 않고 변경내용을 데이터베이스에 동기화
  - 트랜잭션이라는 작업단위가 중요하기 때문에 커밋 직전에만 동기화 하면 됨
