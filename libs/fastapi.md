# FastAPI

> High-performance async web framework for building APIs with Python 3.8+

| | |
|---|---|
| **Website** | [fastapi.tiangolo.com](https://fastapi.tiangolo.com/) |
| **Repository** | [github.com/fastapi/fastapi](https://github.com/fastapi/fastapi) |
| **PyPI** | [pypi.org/project/fastapi](https://pypi.org/project/fastapi/) |
| **Status** | 🟢 Active |

## Why FastAPI

- Automatic OpenAPI and JSON Schema generation
- Native async/await support via Starlette (ASGI)
- Request validation and serialization powered by Pydantic v2
- Dependency injection system with auto-resolved hierarchies
- One of the fastest Python web frameworks available

## Core Stack

| Component | Role |
|---|---|
| [Starlette](https://www.starlette.io/) | ASGI toolkit — routing, middleware, WebSocket, background tasks |
| [Pydantic](https://docs.pydantic.dev/) | Data validation, serialization, settings management |
| [Uvicorn](https://www.uvicorn.org/) | ASGI server (production: with Gunicorn as process manager) |

## Key Use Cases

- REST API backends
- Microservices with async I/O
- Real-time applications (WebSocket support)
- ML model serving endpoints
- Backend-for-frontend (BFF) services

## Ecosystem & Extensions

| Library | Purpose |
|---|---|
| `fastapi-users` | Authentication & user management |
| `fastapi-cache2` | Response caching with Redis/in-memory backends |
| `fastapi-pagination` | Cursor and offset pagination |
| `fastapi-limiter` | Rate limiting |
| `sqlalchemy[asyncio]` | Async ORM integration |
| `alembic` | Database migrations |

## Notes

- Pair with `httpx` + `pytest-asyncio` for async testing
- Use `lifespan` context manager for startup/shutdown events
- Prefer `Annotated[Depends(...)]` pattern (FastAPI 0.95+) for cleaner signatures
