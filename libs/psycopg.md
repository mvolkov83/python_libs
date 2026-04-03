# psycopg (v3)

> Next-generation PostgreSQL adapter for Python

| | |
|---|---|
| **Website** | [psycopg.org/psycopg3](https://www.psycopg.org/psycopg3/) |
| **Repository** | [github.com/psycopg/psycopg](https://github.com/psycopg/psycopg) |
| **PyPI** | [pypi.org/project/psycopg](https://pypi.org/project/psycopg/) |
| **Status** | 🔵 Exploring |

## Why psycopg v3

- Complete rewrite of psycopg2 by the same author
- **Native async/await** — first-class asyncio support without thread pools
- Built-in **connection pooling** (`psycopg_pool`)
- **Pipeline mode** — batch multiple queries in a single round-trip
- Significantly faster in benchmarks vs psycopg2
- Supports COPY operations with async streaming

## Key Differences from psycopg2

| Feature | psycopg2 | psycopg (v3) |
|---|---|---|
| Async support | No (thread workarounds) | Native async/await |
| Connection pooling | External (PgBouncer) | Built-in `ConnectionPool` |
| Pipeline mode | No | Yes |
| Binary protocol | Limited | Full support |
| Import | `import psycopg2` | `import psycopg` |

## Ecosystem

| Package | Purpose |
|---|---|
| `psycopg[binary]` | Pre-compiled C extension for performance |
| `psycopg[c]` | C extension built from source |
| `psycopg_pool` | Connection pool implementation |

## Notes

- SQLAlchemy supports psycopg v3 as async dialect: `postgresql+psycopg://`
- Django support since 4.2, connection pooling since 5.1
- Use `psycopg[binary]` for easy installation, `psycopg[c]` for production builds
- Migration guide: [psycopg.org/psycopg3/docs/basic/from_pg2.html](https://www.psycopg.org/psycopg3/docs/basic/from_pg2.html)
