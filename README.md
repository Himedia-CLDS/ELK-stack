## Description
bottletalk을 사용하기 위한 로컬 Elasticsearch, Logstash, Kibana Docker-compose 레파지토리입니다.<br/>
Logstash는 product-api, feed-api의 사용자 액션 로그를 수집하여 Elasticsearch에 인덱싱하고<br/>
인덱싱된 다큐먼트는 Kibana를 통해서 조회할 수 있습니다.

## Run
1. git clone
```
  git clone https://github.com/Himedia-CLDS/ELK-stack.git
  cd ELK-stack
```

2. docker-compose.yml <br/>
로그스태시 로그 수집 경로 마운트 설정 -> 로컬환경에 맞게 수정 필요
```
37번 라인
     - type: bind
        source: <your project logs directory>
        target: /usr/share/logs
        read_only: false
```

3. Start
```
  docker-compose up
  docker ps
```

4. Elasticsearch(:9200) healthcheck 및 Kibana(:5601) 조회
```
  http://localhost:9200/_cat/indices?v
  http://localhost:5601/app/kibana
```

5. products 인덱스 bulk insert<br/>
product-api를 사용하기 위해서는 products 인덱스가 필요합니다.
```
  Invoke-RestMethod -Uri "http://localhost:9200/products/_bulk" -Method Post -ContentType "application/x-ndjson" -InFile "products_bulk.txt"
```
  ex) 상태
```
  took errors items
  ---- ------ -----
   467  False {@{index=}, @{index=}, @{index=}, @{index=}...}
```
