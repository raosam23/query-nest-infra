# QueryNest Infra 🔍

Docker Compose setup for running QueryNest locally.

> ⚠️ **Work in Progress** — This project is actively being developed.

## Repositories

- [querynest-backend](https://github.com/raosam23/query-nest-backend.git)
- [querynest-frontend](https://github.com/raosam23/query-nest-frontend.git)
- [querynest-infra](https://github.com/raosam23/query-nest-infra.git)

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

## Setup

**1. Clone all three repos into the same folder:**

```bash
mkdir querynest
cd querynest
git clone https://github.com/raosam23/query-nest-backend.git backend
git clone https://github.com/raosam23/query-nest-frontend.git frontend
git clone https://github.com/raosam23/query-nest-infra.git infra
```

**2. Add your environment variables:**

```bash
cd backend
touch .env
```

Add the following to `.env`:

```env
DATABASE_URL=your_neon_postgresql_url
JWT_SECRET=your_jwt_secret
JWT_ALGORITHM=HS256
JWT_EXPIRE_MINUTES=60
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
```

**3. Run:**

```bash
cd ../infra
docker compose up --build
```

**4. Open:**

- Frontend: http://localhost:3000
- Backend: http://localhost:8000/docs

## Services

| Service    | Port | Description   |
| ---------- | ---- | ------------- |
| `db`       | 5432 | PostgreSQL 16 |
| `backend`  | 8000 | FastAPI       |
| `frontend` | 3000 | NextJS        |

## Useful Commands

| Command                     | Description                    |
| --------------------------- | ------------------------------ |
| `docker compose up --build` | Build and start all containers |
| `docker compose up`         | Start all containers           |
| `docker compose down`       | Stop all containers            |
| `docker compose down -v`    | Stop and wipe the database     |
| `docker compose logs`       | View logs from all containers  |
