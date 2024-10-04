## geoserver 설치
- TBD

## PostgreSQL 설치
- TBD

## PostGIS 설치
- TBD

## shp파일을 PostgreSQL에 저장하는 방법
```
ogr2ogr -f "PostgreSQL" PG:"host=도메인or아이피 port=포트 dbname=디비명 user=사용자명 password=비밀번호" "shp파일경로"
```
