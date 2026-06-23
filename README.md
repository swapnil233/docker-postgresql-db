# PostgreSQL Docker Template

A minimal PostgreSQL setup for local development using Docker.

## Requirements

* Docker Desktop

## Start the Database

```bash
docker compose up -d
```

## Stop the Database

```bash
docker compose down
```

## Configuration

Edit the values in `docker-compose.yml` as needed:

```yaml
POSTGRES_DB: example-db-name
POSTGRES_USER: user
POSTGRES_PASSWORD: password
```

Connection string:

```env
POSTGRES_URL=postgres://user:password@localhost:5432/example-db-name
```

## Useful Commands

Open a PostgreSQL shell:

```bash
docker compose exec db psql -U user -d example-db-name
```

View logs:

```bash
docker compose logs -f db
```

Delete all database data:

```bash
docker compose down -v
```

## Troubleshooting

If port `5432` is already in use, change:

```yaml
ports:
  - "5432:5432"
```

to:

```yaml
ports:
  - "5433:5432"
```

and update your connection string accordingly.
