# Prisma docker setting
Setting Prisma in Docker by docker-compose.

### env 파일 설정
같은 경로에 `.env` 파일 생성, 아래 내용 추가

```dosini
PRISMA_MANAGEMENT_API_SECRET=your-secret
PRISMA_PORT=4466 # default prisma port
PRISMA_VERSION=1.34 # recommend version is 1.34
POSTGRES_VERSION=11.4 # recommend version is 11.4
POSTGRES_USER=prisma
POSTGRES_PASSWORD=prisma
POSTGRES_PORT=5432 # default postgres port
```

### dump 파일 로컬 -> 컨테이너 복사
```dosini

docker cp my_dump.dump {container_id}:/my_dump.dump

```

### Postgres 컨테이너 접속
```dosini

docker exec -it {container_id} /bin/bash

```

### 컨테이너 안에 있는 dump 파일을 import
```dosini

pg_restore --verbose --clean --no-acl --no-owner -U prisma -d prisma my_dump.dump

```


### NodeJS 서버 이미지 빌드
```dosini

docker build --tag {image_name}:{image_tag}
ex > docker build --tag node_server:0.0.3 .

```

### 이미지 수정 후 docker-compose 재배포
```dosini

docker-compose up -d --force-recreate

```

