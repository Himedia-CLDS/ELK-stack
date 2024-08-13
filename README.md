# ELK-stack

1. git clone
```
  git clone <repository>
  cd ELK-stack
```

2. docker-compose.yml
로그스태시 로그 수집 경로 마운트 설정 -> 로컬환경에 맞게 수정 필요
```
    - type: bind
        source: <your project logs directory>
        target: /usr/share/logs
        read_only: false
```

3. Start
```
  docker-compose up
```

4. kibana products indexing
Product-service 사용 시 products 목업데이터 필요
```
POST products/_bulk
{ "index": { "_index": "products", "_id": "1000000292" } }
{ "product_id": "1000000292", "kor_name": "라프로익 셀렉트", "eng_name": "Laphroaig Select", "price": 125900, "img": "https://kihyatr7690.cdn-nhncommerce.com/data/goods/23/01/04/1000000292/pm-Laphroaig%20Select.png", "alcohol": "43%", "country": "스코틀랜드", "capacity": "700ml", "description": "좋아하거나 싫어하거나. 중간은 없을 것! 증류 기술은 아일랜드 수도승에 의해서 처음으로 라프로익이 위치한 아일라섬에 전해졌다고 합니다. 재미있는 점은 사실 이런 위스키가 처음에는 '약'의 탈을 쓰고 불법적으로 유통되었다는 것입니다. 이는 이 지역 위스키가 가지는 특징적인 피트감, 소위 '병원향'이 이런 속임수를 가능하게 했습니다.", "category": "싱글몰트 위스키", "tasting_notes": { "aroma": "피트, 건조함, 잘 익은 붉은 과일", "taste": "달콤한, 클래식한, 스모키, 피트", "finish": "마지팬, 라임, 꽃향기, 긴 여운" } }
{ "index": { "_index": "products", "_id": "1000001022" } }
{ "product_id": "1000001022", "kor_name": "발베니 더블우드 12년", "eng_name": "Balvenie Doublewood 12y", "price": 147900, "img": "https://kihyatr7690.cdn-nhncommerce.com/data/goods/23/09/37/1000001022/1000000901_detail_01.png", "alcohol": "40%", "country": "스코틀랜드", "capacity": "700ml", "description": "위스키 오픈런의 주인공 발베니 더블우드 12년은 수석 몰트 마스터 데이비드 스튜어트가 세계 최초로 설계한, 위스키를 버번 오크와 셰리 오크, 두 가지 오크통에서 숙성하는 캐스크 피니쉬의 개념을 도입한 싱글몰트 위스키입니다.", "category": "싱글몰트 위스키", "tasting_notes": { "aroma": "과일, 셰리, 꿀, 바닐라", "taste": "고소한, 시나몬, 셰리, 스파이스", "finish": "길고 따뜻한 여운" } }
{ "index": { "_index": "products", "_id": "1000000394" } }
{ "product_id": "1000000394", "kor_name": "1776 올드 페퍼 싱글 몰트", "eng_name": "1776 Old Pepper Single Malt", "price": 240000, "img": "https://kihyatr7690.cdn-nhncommerce.com/data/goods/23/03/10/1000000394/pm-1776%20Old%20Pepper%20Single%20Malt.png", "alcohol": "50%", "country": "미국", "capacity": "750ml", "description": "켄터키 싱글 몰트의 단맛! 제임스 페퍼 증류소에서 출시된 싱글 몰트는 기존 스카치 싱글 몰트 제품과 달리 새 오크통을 사용하여 3년 이상 숙성한 한정판 에디션 입니다. 새 오크통에서 숙성된 풍부한 켄터키 싱글 몰트의 단맛과 카라멜, 초콜렛, 시트러스를 기반으로 한 다채로운 향의 조화가 매력적인 제품 입니다.", "category": "싱글 몰트 위스키", "tasting_notes": { "aroma": "카라멜, 오크, 시트러스", "taste": "신선한 건초, 시트러스류, 초콜렛", "finish": "풀바디의 우아한 여운" } }
{ "index": { "_index": "products", "_id": "1000000120" } }
{ "product_id": "1000000120", "kor_name": "와일드터키 8년", "eng_name": "Wild Turkey 8y", "price": 72000, "img": "https://kihyatr7690.cdn-nhncommerce.com/data/goods/22/09/38/1000000120/pm-Wild%20Turkey%208y.png", "alcohol": "50.50%", "country": "미국", "capacity": "700ml", "description": "\"알고 마시면 더 맛있어요!\" 와일드 터키 8년은 기존에 전세계 중 일본에서 밖에 구하지 못했으나 현재는 한국에서도 정식 수입이 되고 있습니다. 한국과 일본에서만 한정판매 되는 제품으로 미국에서 오히려 역수입을 하는 경우가 많다고 합니다.", "category": "버번 위스키", "tasting_notes": { "aroma": "풍부한 꿀과 레몬, 버터스카치, 구운 오크", "taste": "달콤한 과일맛과 호밀의 강렬한 스파이스, 약한 시나몬, 팔각, 감초, 후추", "finish": "오크와 다크초콜렛의 긴 여운" } }
{ "index": { "_index": "products", "_id": "1000000152" } }
{ "product_id": "1000000152", "kor_name": "[기획] 조니워커 블루라벨 750ml", "eng_name": "Johnnie Walker Blue Label", "price": 432000, "img": "https://godomall.speedycdn.net/0aecb35d97566a7153dd46c4ee5a1641/goods/1000000152/image/detail/1000000152_detail_021.png", "alcohol": "40%", "country": "스코틀랜드", "capacity": "700ml", "description": "특별한 날을 위한 특별한 위스키, '조니워커 블루라벨' 조니워커 블루 라벨은 조니워커사에서 판매되는 위스키 중 가장 최고급 클래스 제품으로 스코틀랜드에서도 가장 진귀한 위스키 원액을 엄선하여 블렌드한 시그니처 위스키입니다.", "category": "블렌디드 위스키", "tasting_notes": { "aroma": "오렌지, 꿀, 헤이즐넛", "taste": "다크초콜릿, 말린 과일, 생강", "finish": "부드러운 스모크향, 균형잡힌, 오렌지 껍질의 상큼 쌉싸름, 여운 있는" } }
{ "index": { "_index": "products", "_id": "1000000409" } }
{ "product_id": "1000000409", "kor_name": "산토리 가쿠빈", "eng_name": "Suntory Whisky Kakubin", "price": 49000, "img": "https://kihyatr7690.cdn-nhncommerce.com/data/goods/23/03/11/1000000409/pm-Suntory%20Whisky%20Kakubin.png", "alcohol": "40%", "country": "일본", "capacity": "700ml", "description": "‘산토리 하이볼’ 하이볼의 대명사, 산토리 가쿠빈 산토리 가쿠빈은 1937년 출시 이후 일본의 가장 유명하고 인기가 많은 브랜드 중 하나로 세계적으로도 많은 사랑을 받고 있습니다.", "category": "재패니즈 위스키", "tasting_notes": { "aroma": "배, 곡물, 바닐라", "taste": "과일, 스파이시", "finish": "깨끗한, 드라이한" } }
```
