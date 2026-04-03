# aiocache

> Asyncio cache manager for Redis, Memcached, and memory

| | |
|---|---|
| **Repository** | [github.com/aio-libs/aiocache](https://github.com/aio-libs/aiocache) |
| **PyPI** | [pypi.org/project/aiocache](https://pypi.org/project/aiocache/) |
| **Status** | 🟢 Active |

## Why aiocache

- Native async/await support — built for asyncio from the ground up
- Multiple backends: in-memory, Redis, Memcached
- Decorator-based caching (`@cached`, `@multi_cached`) for async functions
- Pluggable serializers (JSON, Pickle, custom)
- Plugin system for metrics, logging, and custom behavior
- Part of the `aio-libs` ecosystem

## Backends

| Backend | Class | Use Case |
|---|---|---|
| Memory | `SimpleMemoryCache` | Development, single-process apps |
| Redis | `RedisCache` | Production, multi-process/distributed |
| Memcached | `MemcachedCache` | Legacy systems, simple key-value caching |

## Key Features

| Feature | Description |
|---|---|
| `@cached` | Cache function results with TTL, custom keys, and serializers |
| `@multi_cached` | Batch cache multiple results from a single call |
| Serializers | `JsonSerializer`, `PickleSerializer`, or custom implementations |
| Plugins | `HitMissRatioPlugin`, `TimingPlugin` for observability |
| Key builders | Customizable cache key generation from function arguments |

## Key Use Cases

- Caching expensive async API calls or database queries
- Response caching in FastAPI/Starlette applications
- Distributed caching with Redis in multi-instance deployments
- Rate limiting and throttling with TTL-based keys

## Notes

- Use `PickleSerializer` to store complex Python objects in Redis
- Always use cache as async context manager: `async with redis_client, redis_cache:`
- Set `namespace` to avoid key collisions between different caches
- Combine with `@cached(ttl=N)` for automatic expiration
