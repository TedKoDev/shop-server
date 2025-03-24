##

# 🛍️ beko-shop - shop-server

NestJS 기반의 쇼핑몰 서버 프로젝트입니다. PostgreSQL과 Docker를 활용하여 로컬 개발 환경을 손쉽게 구성할 수 있도록 되어 있습니다.

---

## 📦 프로젝트 구조

shop-server/
├── docker-compose/
│ ├── build.sh # 초기 셋업용 쉘 스크립트
│ ├── Dockerfile # NestJS 서버용 Dockerfile
│ ├── init.sql # PostgreSQL 초기 데이터 및 테이블 생성 스크립트
│ └── postgres-compose.yml # PostgreSQL Docker Compose 설정 파일
├── node_modules/ # 의존성 모듈 (자동 생성됨)
├── src/ # NestJS 애플리케이션 소스 코드
├── test/ # 테스트 코드
├── .eslintrc.js # ESLint 설정
├── .gitignore # Git에서 제외할 파일 목록
├── .prettierrc # Prettier 코드 포맷 설정
├── nest-cli.json # NestJS CLI 설정
├── package.json # 프로젝트 의존성 및 스크립트 정의
├── pnpm-lock.yaml # pnpm 패키지 잠금 파일
├── tsconfig.build.json # TypeScript 빌드용 설정
├── tsconfig.json # TypeScript 기본 설정
└── README.md # 프로젝트 설명 문서

---

## 🐳 Docker를 사용한 개발 환경 세팅

### 1. Docker 네트워크 생성

PostgreSQL 컨테이너와 NestJS 컨테이너 간 통신을 위해 네트워크를 먼저 생성합니다:

```bash
docker network create yesnetwork
위 네트워크는 postgres-compose.yml에서 사용됩니다.

2. PostgreSQL 컨테이너 실행
docker-compose 디렉토리에서 다음 명령어 실행:

docker compose -f postgres-compose.yml up -d
컨테이너가 정상적으로 실행되면 PostgreSQL이 포트 5432에서 동작합니다.

3.  sh build.sh
도커 실행
```

4. prisma 설치 및 실생

pnpm add -D prisma typescript tsx @types/node

5. prisma 초기화
   npx prisma init
