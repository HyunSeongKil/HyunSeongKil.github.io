# geoserver vs java version
  - 참고 : https://docs.geoserver.org/latest/en/user/production/java.html
  - geoserver 2.21.1 은 java 15까지 정상동작 함


# postgresql에 postgis 설치하는 방법
  - 참고 : https://sihus.tistory.com/3
  - 요약 : postgresql 쿼리 실행창에서 아래 구문 실행
  ```
  create extension postgis;
  ```
    
  - 설치 후 테스트
  ```
  // 리턴 타입은 미터입니다
  SELECT 
	ST_DistanceSphere(
    	ST_GeomFromText('POINT(129.014525 35.13542)', 4326),
        ST_GeomFromText('POINT(129.014525 36.24553)', 4326)
    );
  ```
## postgis.md 파일도 확인하세요.
