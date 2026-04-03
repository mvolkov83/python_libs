# Celery

> Distributed task queue for Python

| | |
|---|---|
| **Website** | [docs.celeryq.dev](https://docs.celeryq.dev/) |
| **Repository** | [github.com/celery/celery](https://github.com/celery/celery) |
| **PyPI** | [pypi.org/project/celery](https://pypi.org/project/celery/) |
| **Status** | 🟢 Active |

## Why Celery

- Battle-tested distributed task queue (10+ years)
- Broad broker support: RabbitMQ, Redis, SQS, Kafka
- Feature-complete: scheduling (Beat), result backends, task chains/groups/chords
- Massive ecosystem and community

## Limitations

- **Sync-first architecture** — async support is bolted on, not native
- Heavy dependency footprint
- Complex configuration for advanced patterns
- Worker startup overhead

## Async-Native Alternatives

| Library | Approach | Best For |
|---|---|---|
| [arq](https://arq-docs.helpmanual.io/) | Lightweight async queue (Redis) | Simple FastAPI background jobs |
| [taskiq](taskiq.md) | Async Celery-like (multi-broker) | Full-featured async task queue |
| [Temporalio](https://docs.temporal.io/develop/python) | Workflow orchestration engine | Complex stateful workflows |

## When to Use Celery

- Existing sync codebases (Flask, Django)
- Need for RabbitMQ or SQS as broker
- Complex task orchestration (chains, groups, chords)
- Mature monitoring (Flower)

## When to Use Alternatives

- Async-first projects (FastAPI) → arq or taskiq
- Long-running stateful workflows → Temporalio
- Simple background jobs → arq

## Notes

- Use `celery[redis]` or `celery[rabbitmq]` extras
- Monitor with Flower: `celery -A app flower`
- For FastAPI integration, consider arq or taskiq first — native async is cleaner than wrapping Celery
