# taskiq

> Async distributed task queue for Python

| | |
|---|---|
| **Website** | [taskiq-python.github.io](https://taskiq-python.github.io/) |
| **Repository** | [github.com/taskiq-python/taskiq](https://github.com/taskiq-python/taskiq) |
| **PyPI** | [pypi.org/project/taskiq](https://pypi.org/project/taskiq/) |
| **Status** | 🔵 Exploring |

## Why taskiq

- **Async-first** — built for asyncio from the ground up
- Inspired by Celery and Dramatiq, but modern and async
- Runs both sync and async functions
- FastAPI integration — reuse FastAPI dependencies in tasks
- Multiple brokers: Redis, NATS, RabbitMQ, Kafka
- 10x faster than RQ in load tests

## Key Features

| Feature | Description |
|---|---|
| Async tasks | Native async/await task execution |
| FastAPI DI | Reuse FastAPI dependencies inside tasks |
| Multiple brokers | Redis Streams, NATS, RabbitMQ, Kafka |
| Result backends | Redis, MongoDB, and more |
| Middleware | Pluggable task middleware system |
| Scheduling | Built-in periodic task scheduling |

## Ecosystem

| Package | Purpose |
|---|---|
| `taskiq-redis` | Redis broker and result backend |
| `taskiq-nats` | NATS broker |
| `taskiq-aio-pika` | RabbitMQ broker |
| `taskiq-fastapi` | FastAPI dependency injection integration |

## Compared to Celery

| Feature | Celery | taskiq |
|---|---|---|
| Async support | Bolted on | Native |
| FastAPI integration | Manual | First-class |
| Broker diversity | RabbitMQ, Redis, SQS | Redis, NATS, RabbitMQ, Kafka |
| Maturity | 10+ years | Newer, growing |
| Sync support | Native | Supported but async-first |

## Notes

- Does not work well for purely synchronous projects
- Use `taskiq-fastapi` to share request-scoped dependencies with task workers
- Redis Streams broker is more reliable than Redis list-based alternatives
