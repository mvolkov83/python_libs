# SQLAlchemy

> Python SQL toolkit and Object-Relational Mapper

| | |
|---|---|
| **Website** | [sqlalchemy.org](https://www.sqlalchemy.org/) |
| **Repository** | [github.com/sqlalchemy/sqlalchemy](https://github.com/sqlalchemy/sqlalchemy) |
| **PyPI** | [pypi.org/project/sqlalchemy](https://pypi.org/project/SQLAlchemy/) |
| **Status** | 🟢 Active |

## Why SQLAlchemy

- Dual interface: high-level ORM and low-level Core for fine-grained SQL control
- Full async support (2.0+) with `asyncpg`, `aiomysql`, `aiosqlite`
- Database-agnostic — PostgreSQL, MySQL, SQLite, Oracle, MSSQL
- Mature migration ecosystem via Alembic
- Unit of Work pattern with identity map and automatic change tracking

## Core Concepts

| Concept | Role |
|---|---|
| Engine | Connection management and pooling |
| Session | Unit of Work — tracks objects, flushes changes, manages transactions |
| Declarative Base | Model definition with mapped columns and relationships |
| Core (select/insert/update) | SQL expression language without ORM overhead |
| Alembic | Schema versioning and migrations |

## Key Use Cases

- Async API backends (FastAPI, Starlette)
- Data-heavy applications with complex queries and joins
- Multi-database projects requiring dialect abstraction
- Applications needing fine-tuned connection pooling

## Ecosystem & Extensions

| Library | Purpose |
|---|---|
| `alembic` | Database migrations and schema versioning |
| `asyncpg` | High-performance async PostgreSQL driver |
| `sqlalchemy-utils` | Extra column types, listeners, aggregates |
| `sqlmodel` | SQLAlchemy + Pydantic hybrid models (by FastAPI author) |
| `factory_boy` | Test fixtures with SQLAlchemy integration |

## Notes

- Use `selectinload()` over `joinedload()` for collection relationships
- Default to `expire_on_commit=False` in async sessions
- Prefer `select()` style (2.0) over legacy `session.query()` syntax
- Connection pool tuning: `pool_size=20, max_overflow=10, pool_pre_ping=True`
