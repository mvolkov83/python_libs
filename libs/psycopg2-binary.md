# psycopg2-binary

> The classic PostgreSQL adapter for Python

| | |
|---|---|
| **Website** | [psycopg.org/docs](https://www.psycopg.org/docs/) |
| **PyPI** | [pypi.org/project/psycopg2-binary](https://pypi.org/project/psycopg2-binary/) |
| **Status** | 🟢 Active (maintenance mode) |

## Why psycopg2

- Battle-tested, C-based PostgreSQL adapter
- De facto standard for synchronous PostgreSQL access in Python
- Supported by SQLAlchemy, Django, and virtually every Python ORM

## Limitations

- **No native async support** — requires thread-based workarounds
- `-binary` variant bundles libpq but is not recommended for production by the maintainer
- No connection pooling built-in (use PgBouncer or external pooler)

## Migration Path → psycopg (v3)

psycopg (v3) is a complete rewrite by the same author with:
- Native async/await support
- Built-in connection pooling
- Better performance in benchmarks
- Pipeline/batch mode for reduced round-trips
- Active development (v3.3+)

Django supports psycopg3 since 4.2, with connection pooling added in 5.1.

**Recommendation:** Continue using psycopg2 in existing sync projects. Use [psycopg (v3)](psycopg.md) for all new async work.
