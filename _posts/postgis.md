## geoserver
1. install

## postgresql
1. install
  

## postgis
- https://postgis.net
- install PostGIS
  - https://velog.io/@tett_77/PostGIS-설치
 
  - stack builder
    - check Spatial Extensions > PostGIS 3.4 Bundle for PostgreSQL 16(64bix) v3.4.0
  
  or
  ```
  sql> create extension postgis;  
  ```

  3. 확인
  ```
  sql> select * from pg_catalog.pg_extension;
  -- 목록에 postgis 존재하면 성공
  ```

### 참고
  - https://docs.aws.amazon.com/ko_kr/AmazonRDS/latest/UserGuide/Appendix.PostgreSQL.CommonDBATasks.PostGIS.html
  - 
