# A student-management API with operational evidence

The project combines an authenticated student-management API with small concurrency
and design-pattern demonstrations. Its useful engineering story is the API's complete
path from validated request to transaction, audit event and observable response.

FastAPI routers delegate to services and SQLAlchemy repositories. PostgreSQL is the
deployment database, Alembic tracks schema changes, and version-checked updates guard
against lost writes. JWT roles separate readers from administrators. Structured logs,
request IDs, health checks and Prometheus metrics make behaviour inspectable.

The committed CI workflow checks formatting, types, tests and coverage, PostgreSQL
integration, migration consistency and container building. See the workflow's latest
run for current results; README coverage numbers describe a recorded snapshot.

The deliberate limit is a reproducible single-service deployment. The in-memory
rate limiter, lack of token revocation and absence of packaged monitoring dashboards
are documented next steps, rather than capabilities the project already claims.
