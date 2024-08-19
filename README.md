# ELK-stack

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
