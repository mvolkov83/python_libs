# Python Libraries & Frameworks

A curated catalog of Python ecosystem libraries I use or plan to adopt.

**Status:** 🟢 Active · 🔵 Exploring · ⚪ Planned

## Contents

- [Web Frameworks & Servers](#web-frameworks--servers)
- [Async & Concurrency](#async--concurrency)
- [Database & ORM](#database--orm)
- [Data Validation & Settings](#data-validation--settings)
- [Authentication & Security](#authentication--security)
- [HTTP Clients](#http-clients)
- [Serialization & Data Formats](#serialization--data-formats)
- [AWS & Cloud](#aws--cloud)
- [Task Queues & Scheduling](#task-queues--scheduling)
- [Caching](#caching)
- [Logging & Monitoring](#logging--monitoring)
- [CLI & Terminal](#cli--terminal)
- [Testing](#testing)
- [Code Quality](#code-quality)
- [gRPC](#grpc)
- [Data Processing](#data-processing)
- [Documentation](#documentation)
- [Image & Media](#image--media)
- [Internationalization](#internationalization)
- [Templating](#templating)
- [Utilities](#utilities)

---

## Web Frameworks & Servers

### [FastAPI](https://fastapi.tiangolo.com/) 🟢

> Async web framework · `web` `api` `async`

High-performance API framework with automatic validation, serialization, and OpenAPI documentation. Built on Starlette (ASGI) and Pydantic.

[Details →](libs/fastapi.md)

### [NiceGUI](https://nicegui.io/) 🟢

> Python-based web UI framework · `web` `ui` `dashboard`

Declarative UI framework for building web apps, dashboards, and internal tools entirely in Python. Built on FastAPI + Vue.js/Quasar, with native desktop mode and automatic data binding.

[Details →](libs/nicegui.md)

### [Flask](https://flask.palletsprojects.com/) 🟢

> Lightweight WSGI web framework · `web` `api`

Micro-framework with a simple core and rich extension ecosystem. Synchronous, WSGI-based. Mature and well-documented, but lacks native async support.

### [Tornado](https://www.tornadoweb.org/) 🟢

> Async networking library & web framework · `web` `async` `networking`

Non-blocking web server and framework with its own event loop. Pre-ASGI era — primarily useful for legacy projects and long-lived connections. For new projects, prefer FastAPI/Starlette.

### [Uvicorn](https://www.uvicorn.org/) 🟢

> ASGI server · `server` `async`

Lightning-fast ASGI server built on uvloop and httptools. The standard way to run FastAPI, Starlette, and other ASGI applications.

### [Gunicorn](https://gunicorn.org/) 🟢

> WSGI/ASGI process manager · `server` `deployment`

Pre-fork worker model HTTP server. Used as process manager for Uvicorn workers in production (`gunicorn -k uvicorn.workers.UvicornWorker`).

---

## Async & Concurrency

### [asyncpg](https://github.com/MagicStack/asyncpg) 🟢

> Fast async PostgreSQL driver · `database` `async` `postgresql`

High-performance, native async PostgreSQL client. Significantly faster than psycopg2 for async workloads. Used as SQLAlchemy async dialect backend.

### [aiofiles](https://github.com/Tinche/aiofiles) 🟢

> Async file I/O · `async` `filesystem`

Async-compatible file operations for use with asyncio. Drop-in replacement for Python's built-in `open()` in async contexts.

### [aiomisc](https://github.com/aiokitchen/aiomisc) 🟢

> Async miscellaneous utilities · `async` `utilities`

Collection of utilities for asyncio: thread pools, periodic tasks, service management, logging, and signal handling.

### [aiosqlite](https://github.com/omnilib/aiosqlite) 🟢

> Async SQLite driver · `database` `async` `sqlite`

Async interface for SQLite using a background thread. Useful for development, testing, and lightweight async applications.

### [websockets](https://websockets.readthedocs.io/) 🟢

> WebSocket client & server · `async` `websocket` `networking`

Production-ready async WebSocket library. Clean API for building both WebSocket servers and clients.

---

## Database & ORM

### [SQLAlchemy](https://www.sqlalchemy.org/) 🟢

> Python SQL toolkit & ORM · `database` `orm` `async`

The most widely adopted Python ORM with both high-level ORM and low-level Core interfaces. Full async support since 2.0 via `asyncpg`/`aiomysql`.

[Details →](libs/sqlalchemy.md)

### [Alembic](https://alembic.sqlalchemy.org/) 🟢

> Database migrations · `database` `migrations`

Schema migration tool for SQLAlchemy. Supports auto-generation of migrations from model changes, branching, and async engines.

### [Beanie](https://beanie-odm.dev/) 🟢

> Async MongoDB ODM · `database` `mongodb` `async`

Async ODM for MongoDB built on Motor and Pydantic. Provides document models with validation, migrations, and an expressive query builder.

### [Motor](https://motor.readthedocs.io/) 🟢

> Async MongoDB driver · `database` `mongodb` `async`

Official async driver for MongoDB. Wraps PyMongo for asyncio and Tornado compatibility.

### [PyMongo](https://pymongo.readthedocs.io/) 🟢

> MongoDB driver · `database` `mongodb`

Official synchronous Python driver for MongoDB. Foundation for Motor (async) and Beanie (ODM).

### [psycopg2-binary](https://www.psycopg.org/docs/) 🟢

> PostgreSQL adapter · `database` `postgresql`

The classic PostgreSQL adapter for Python. Synchronous, C-based, widely used. **For new async projects, consider migrating to psycopg (v3).**

[Details →](libs/psycopg2-binary.md)

### [psycopg](https://www.psycopg.org/psycopg3/) 🔵

> Next-gen PostgreSQL adapter · `database` `postgresql` `async`

Complete rewrite of psycopg2 with native async support, connection pooling, and improved performance. The future of PostgreSQL in Python.

[Details →](libs/psycopg.md)

---

## Data Validation & Settings

### [Pydantic](https://docs.pydantic.dev/) 🟢

> Data validation & settings · `validation` `serialization` `settings`

The standard for data validation in Python. V2 rewritten in Rust for 5-50x speedup. Powers FastAPI request/response handling, settings management, and schema generation.

### [pydantic-settings](https://docs.pydantic.dev/latest/concepts/pydantic_settings/) 🟢

> Settings management · `settings` `config` `env`

Pydantic-based settings with .env file loading, environment variable parsing, and nested configuration support. Extracted from Pydantic v1 core.

---

## Authentication & Security

### [passlib](https://passlib.readthedocs.io/) 🟢

> Password hashing · `auth` `security`

Password hashing library with support for bcrypt, argon2, and many other schemes. ⚠️ **Stalled maintenance, broken on Python 3.13+.** Migrate to pwdlib for new projects.

[Details →](libs/passlib.md)

### [pwdlib](https://github.com/frankie567/pwdlib) 🔵

> Modern password hashing · `auth` `security`

Lightweight passlib replacement by the fastapi-users author. Supports Argon2 and bcrypt. Adopted by FastAPI docs as recommended hashing library.

[Details →](libs/pwdlib.md)

### [python-jose](https://github.com/mpdavis/python-jose) 🟢

> JOSE implementation (JWS, JWE, JWK, JWT) · `auth` `jwt` `security`

JavaScript Object Signing and Encryption implementation. ⚠️ **Abandoned since 2021.** FastAPI migrated to PyJWT. For full JOSE support, use joserfc.

[Details →](libs/python-jose.md)

### [joserfc](https://jose.authlib.org/) 🔵

> Modern JOSE implementation · `auth` `jwt` `security`

Full JOSE implementation (JWS, JWE, JWK, JWT) from the Authlib author. Actively maintained, with migration guides from python-jose and PyJWT.

[Details →](libs/joserfc.md)

### [bcrypt](https://github.com/pyca/bcrypt) 🟢

> Bcrypt hashing · `auth` `security`

Modern Python bcrypt implementation maintained by PyCA. Fast, reliable, used by passlib and pwdlib under the hood.

### [cryptography](https://cryptography.io/) 🟢

> Cryptographic primitives · `security` `crypto`

Comprehensive cryptography library by PyCA. Provides both high-level recipes (Fernet, X.509) and low-level interfaces (OpenSSL). Foundation for many auth libraries.

---

## HTTP Clients

### [HTTPX](https://www.python-httpx.org/) 🟢

> Async/sync HTTP client · `http` `async` `api`

Modern HTTP client with both sync and async APIs, HTTP/2 support, and a requests-compatible interface. The go-to choice for async applications.

### [Requests](https://requests.readthedocs.io/) 🟢

> HTTP client · `http` `api`

The classic Python HTTP library. Actively maintained (v2.33+), synchronous only. For async workloads or HTTP/2, use HTTPX.

---

## Serialization & Data Formats

### [orjson](https://github.com/ijl/orjson) 🟢

> Fast JSON library · `json` `serialization` `performance`

Fastest Python JSON library (written in Rust). Native support for dataclasses, datetime, numpy, and UUID. Drop-in replacement for `json.dumps`/`json.loads`.

### [msgpack](https://github.com/msgpack/msgpack-python) 🟢

> MessagePack serialization · `serialization` `binary`

Binary serialization format — faster and more compact than JSON. Ideal for inter-service communication and caching payloads.

### [PyYAML](https://pyyaml.org/) 🟢

> YAML parser · `yaml` `config`

Standard YAML parser/emitter. Used for configuration files, CI/CD definitions, and Kubernetes manifests. Always use `safe_load()`.

---

## AWS & Cloud

### [Boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html) 🟢

> AWS SDK · `aws` `cloud`

Official AWS SDK for Python. Covers all AWS services — S3, DynamoDB, SQS, Lambda, and more.

### [aioboto3](https://github.com/terrycain/aioboto3) 🟢

> Async AWS SDK wrapper · `aws` `cloud` `async`

Async wrapper around Boto3 for use with asyncio. Provides async context managers for S3, DynamoDB, and other AWS services.

---

## Task Queues & Scheduling

### [Celery](https://docs.celeryq.dev/) 🟢

> Distributed task queue · `queue` `workers` `scheduling`

Mature, battle-tested distributed task queue. Sync-first architecture with broad broker support (RabbitMQ, Redis, SQS). Heavy but feature-complete. **For async-native projects, consider arq or taskiq.**

[Details →](libs/celery.md)

### [arq](https://arq-docs.helpmanual.io/) 🟢

> Async task queue · `queue` `async` `redis`

Lightweight async job queue built on Redis. Native asyncio support, simple API, ideal for FastAPI projects.

### [Temporalio](https://docs.temporal.io/develop/python) 🟢

> Workflow orchestration · `workflow` `orchestration` `distributed`

Durable workflow execution engine. Handles long-running, stateful workflows with automatic retries, versioning, and observability. Different category from task queues — orchestrates complex business processes.

### [taskiq](https://taskiq-python.github.io/) 🔵

> Async distributed task queue · `queue` `async` `workers`

Modern async-first alternative to Celery. Native asyncio support, FastAPI integration, multiple brokers (Redis, NATS, RabbitMQ, Kafka). 10x faster than RQ in benchmarks.

[Details →](libs/taskiq.md)

---

## Caching

### [aiocache](https://github.com/aio-libs/aiocache) 🟢

> Async cache manager · `cache` `async` `redis`

Asyncio-native caching library with multiple backends (memory, Redis, Memcached), decorator-based caching, pluggable serializers, and a plugin system.

[Details →](libs/aiocache.md)

### [cachetools](https://github.com/tkem/cachetools) 🟢

> In-process caching · `cache` `utilities`

Extensible memoizing collections and decorators. Provides TTLCache, LRUCache, LFUCache — synchronous, for single-process use. Complements aiocache for non-async caching.

---

## Logging & Monitoring

### [structlog](https://www.structlog.org/) 🟢

> Structured logging · `logging` `observability`

Structured logging library that makes logs machine-parseable and human-readable. Integrates with stdlib logging, outputs JSON, and supports async-safe processors.

### [Sentry SDK](https://docs.sentry.io/platforms/python/) 🟢

> Error tracking & performance monitoring · `monitoring` `errors` `observability`

Official Sentry client. Captures exceptions, performance traces, and breadcrumbs. Integrations for FastAPI, Celery, SQLAlchemy, and more.

---

## CLI & Terminal

### [Typer](https://typer.tiangolo.com/) 🟢

> CLI framework · `cli` `terminal`

Modern CLI framework built on Click with type hint-based argument parsing. By the FastAPI author — same DX philosophy. Preferred over Click for new projects.

### [Click](https://click.palletsprojects.com/) 🟢

> CLI framework · `cli` `terminal`

Composable CLI toolkit. Foundation for Typer, Flask, and many other tools. More verbose than Typer but offers finer control over CLI behavior.

### [Rich](https://rich.readthedocs.io/) 🟢

> Terminal formatting · `cli` `terminal` `ui`

Rich text, tables, progress bars, syntax highlighting, and tracebacks in the terminal. Makes CLI tools beautiful with minimal effort.

---

## Testing

### [pytest](https://docs.pytest.org/) 🟢

> Testing framework · `testing`

The standard Python testing framework. Fixtures, parametrize, plugins, and a massive ecosystem. Foundation for all testing workflows.

### [respx](https://lundberg.github.io/respx/) 🟢

> HTTPX mock transport · `testing` `mocking` `http`

Mock library for HTTPX requests. Pattern-based request matching, assertion helpers, and async support. The `responses`/`requests-mock` equivalent for HTTPX.

### [Factory Boy](https://factoryboy.readthedocs.io/) 🟢

> Test data factories · `testing` `fixtures`

Fixtures replacement for generating test objects. Supports SQLAlchemy, Django ORM, and Mongoengine. Declarative factory definitions with traits and sequences.

### [Faker](https://faker.readthedocs.io/) 🟢

> Fake data generation · `testing` `fixtures`

Generates realistic fake data (names, emails, addresses, etc.) with locale support. Used standalone or within Factory Boy. **For Pydantic-centric projects, see polyfactory.**

### [polyfactory](https://polyfactory.litestar.dev/) 🔵

> Type-driven test data factories · `testing` `fixtures` `pydantic`

Generates mock data directly from type hints — Pydantic models, dataclasses, TypedDict, SQLAlchemy models. Uses Faker internally but adds automatic model-aware generation.

[Details →](libs/polyfactory.md)

### [moto](https://docs.getmoto.org/) 🟢

> AWS mocking · `testing` `aws` `mocking`

Mock library for Boto3. Simulates AWS services (S3, DynamoDB, SQS, Lambda, etc.) in tests without hitting real AWS.

### [mongomock-motor](https://github.com/michaelkryukov/mongomock-motor) 🟢

> Async MongoDB mocking · `testing` `mongodb` `mocking`

Mock library for Motor (async MongoDB driver). Enables testing MongoDB operations without a running MongoDB instance.

---

## Code Quality

### [Ruff](https://docs.astral.sh/ruff/) 🟢

> Linter & formatter · `linting` `formatting` `quality`

Extremely fast Python linter and formatter written in Rust. Replaces Flake8, isort, Black, pyupgrade, and dozens of plugins. 10-100x faster than alternatives.

### [mypy](https://mypy-lang.org/) 🟢

> Static type checker · `typing` `quality`

Reference implementation of Python static type checking. Use with `--strict` mode for maximum type safety.

### [Black](https://black.readthedocs.io/) 🟢

> Code formatter · `formatting` `quality`

Opinionated code formatter. ⚠️ **Ruff's formatter is a drop-in replacement, 30x faster.** Consider migrating — ruff covers both linting and formatting in one tool.

---

## gRPC

### [gRPC Python](https://grpc.io/docs/languages/python/) 🟢

> RPC framework · `grpc` `rpc` `microservices`

Google's high-performance RPC framework. `grpcio` for runtime, `grpcio-tools` for protobuf code generation. Used for inter-service communication in microservice architectures.

---

## Data Processing

### [pandas](https://pandas.pydata.org/) 🟢

> Data analysis & manipulation · `data` `analytics` `dataframes`

The standard for tabular data manipulation, analysis, and transformation in Python.

### [openpyxl](https://openpyxl.readthedocs.io/) 🟢

> Excel file handling · `data` `excel`

Read/write Excel 2010+ (xlsx/xlsm) files. Used for report generation, data import/export, and spreadsheet automation.

---

## Documentation

### [MkDocs](https://www.mkdocs.org/) 🟢

> Static site generator for docs · `docs` `markdown`

Project documentation with Markdown. Paired with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) for a modern, feature-rich theme with search, navigation, and code highlighting.

---

## Image & Media

### [Pillow](https://pillow.readthedocs.io/) 🟢

> Image processing · `image` `media`

The maintained fork of PIL. Image manipulation — resize, crop, filter, format conversion. Foundation for most Python image processing.

---

## Internationalization

### [Babel](https://babel.pocoo.org/) 🟢

> Internationalization & localization · `i18n` `l10n`

Locale data, date/number formatting, and message extraction for i18n. Integrates with Jinja2 and Flask.

### [pycountry](https://github.com/pycountry/pycountry) 🟢

> ISO country/language/currency data · `i18n` `data`

ISO databases for countries (3166), languages (639), currencies (4217), and subdivisions.

### [phonenumbers](https://github.com/daviddrysdale/python-phonenumbers) 🟢

> Phone number parsing & validation · `i18n` `validation`

Python port of Google's libphonenumber. Parse, format, and validate international phone numbers.

---

## Templating

### [Jinja2](https://jinja.palletsprojects.com/) 🟢

> Template engine · `templating` `web`

The standard Python template engine. Powers Flask, FastAPI templates, Ansible, and many other tools. Template inheritance, macros, auto-escaping.

---

## Utilities

### [python-dateutil](https://dateutil.readthedocs.io/) 🟢

> Date/time utilities · `datetime` `utilities`

Powerful extensions to the datetime module — relative deltas, flexible parsing, timezone handling, and recurrence rules.

### [python-slugify](https://github.com/un33k/python-slugify) 🟢

> URL slug generation · `text` `utilities`

Generate URL-safe slugs from Unicode strings. Handles transliteration and custom character mappings.

### [python-dotenv](https://github.com/theskumar/python-dotenv) 🟢

> .env file loading · `config` `env`

Reads key-value pairs from `.env` files into environment variables. Used with pydantic-settings and standalone.

### [email-validator](https://github.com/JoshData/python-email-validator) 🟢

> Email validation · `validation` `utilities`

Robust email address validation with DNS checking. Used by Pydantic for `EmailStr` field type.

### [validators](https://github.com/python-validators/validators) 🟢

> Data validation functions · `validation` `utilities`

Simple validation functions for URLs, emails, IPs, UUIDs, and more. Lightweight, no dependencies.

### [uuid6 / uuid7](https://github.com/oittaa/uuid6-python) 🟢

> Modern UUID generation · `uuid` `utilities`

UUIDv6 and UUIDv7 implementations. UUIDv7 is time-ordered and database-index-friendly — preferred over UUIDv4 for primary keys.
