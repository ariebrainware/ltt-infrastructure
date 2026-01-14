# LTT Infrastructure

This repository contains the microservices and supporting infrastructure required to run the LTT web application. It groups the backend APIs, frontend, databases, cache, and auxiliary services needed for the app to function end-to-end.

## Microservices & components

- `basis-data-ltt/` — Go API backend for core patient, therapist, treatment, token, and session management. See `basis-data-ltt/API_OVERVIEW.md` and `basis-data-ltt/README.md`.
- `basis-data-ltt-db/` — Database Dockerfile and deployment scripts for the core service database.
- `basis-data-ltt-fe/` — Frontend (Next.js) application, E2E tests, and UI. Includes `sample.env` and testing docs.
- `basis-redis/` — Redis configuration and Dockerfile used for sessions and caching.
- `ltt-file-service/` — File storage microservice for uploads and static assets; includes a small compose setup.
- `ltt-inventory-service/` — Inventory microservice providing inventory APIs for the app.
- `ltt-inventory-db/` — Database Dockerfile and assets for the inventory service.
- `docker/` — Helper Docker assets and compose fragments used by the top-level orchestrations.
- `docker-compose.yml` (repo root) — Top-level compose file intended to bring up the full local stack for development.

## Quickstart (local)

1. Ensure Docker (and Docker Compose) are installed and running.
2. Inspect service-specific env samples (for example `basis-data-ltt-fe/.env.sample`) and create any required `.env` files.
3. From the repository root run:

```bash
docker compose up --build
```

This will build and start the services defined in the root `docker-compose.yml`.

## Notes

- Each service contains its own `README.md`, configs, and docs — check the subfolders for service-specific setup (for example, `basis-data-ltt/`, `basis-data-ltt-fe/`).
- Use `basis-data-ltt/API_OVERVIEW.md` for details on the API endpoints exposed by the core backend service.

## Next steps

- If you want, I can commit this README update to a branch or open a PR. Reply with "commit changes" to proceed.
