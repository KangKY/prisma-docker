# Prisma docker setting
Setting Prisma in Docker by docker-compose.

## env 파일 설정
- 같은 경로에 .env 파일 생성, 아래 내용 추가

PRISMA_MANAGEMENT_API_SECRET=your-secret
PRISMA_PORT=4466
PRISMA_VERSION=your prisma version
POSTGRES_VERSION=11.4
POSTGRES_USER=prisma
POSTGRES_PASSWORD=prisma
POSTGRES_PORT=5432