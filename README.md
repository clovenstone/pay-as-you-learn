# Pay As You Learn Backend

Spring Boot backend for AI-powered 11+ grammar school exam question generation.

## Tech Stack

- Java 21
- Spring Boot (Web + Spring Data JPA)
- Gradle
- PostgreSQL (Docker)
- Liquibase (schema migrations)

## What this repository contains

This repo now contains only the backend service:

- REST API foundation
- PostgreSQL containerized runtime via Docker Compose
- Liquibase changeset-driven schema management

## React UI repository

As requested, the React frontend should live in a **separate repository**. Keep this repository focused on backend APIs and persistence.

Suggested split:

- `pay-as-you-learn-backend` (this repo)
- `pay-as-you-learn-ui` (separate React app repo)

## Local run flow

When you run the backend with Gradle:

1. `composeUp` starts `postgres:16-alpine` from `docker-compose.yml`.
2. Spring Boot starts and connects to Postgres.
3. Liquibase applies `db/changelog/db.changelog-master.yaml` before app startup is completed.
4. On process exit, `composeDown` is called.

Run:

```bash
gradle bootRun
```

Health endpoint:

```text
GET http://localhost:8080/api/health
```

## Database migrations

- Master changelog: `src/main/resources/db/changelog/db.changelog-master.yaml`
- Initial changeset: `src/main/resources/db/changelog/changes/001-initial-schema.yaml`

## Next suggested backend steps

1. Add JPA entities that match Liquibase tables.
2. Add `/api/v1/questions/generate` endpoint.
3. Integrate LLM provider abstraction.
4. Add validation and safety checks for 11+ content.
