# polyfactory

> Type-driven mock data generation for Python

| | |
|---|---|
| **Website** | [polyfactory.litestar.dev](https://polyfactory.litestar.dev/) |
| **Repository** | [github.com/litestar-org/polyfactory](https://github.com/litestar-org/polyfactory) |
| **PyPI** | [pypi.org/project/polyfactory](https://pypi.org/project/polyfactory/) |
| **Status** | 🔵 Exploring |

## Why polyfactory

- Generates mock data **directly from type hints** — no manual field definitions
- Supports Pydantic models, dataclasses, TypedDict, msgspec, SQLAlchemy, Beanie
- Uses Faker internally for realistic values
- Part of the Litestar ecosystem, actively maintained
- Formerly `pydantic-factories` — evolved to support multiple model types

## Key Features

| Feature | Description |
|---|---|
| Auto-generation | Infers field values from type annotations |
| Model support | Pydantic, dataclasses, TypedDict, attrs, msgspec, SQLAlchemy |
| Faker integration | Customizable fake data with locale support |
| Nested models | Automatically generates nested/related objects |
| Overrides | Mix auto-generated and explicit values |

## Compared to Factory Boy + Faker

| Feature | Factory Boy + Faker | polyfactory |
|---|---|---|
| Setup | Manual field-by-field definition | Auto from type hints |
| Pydantic support | Requires custom integration | Native |
| SQLAlchemy support | Built-in | Built-in |
| Nested models | Manual | Automatic |
| Type safety | None | Type-aware generation |

## Usage

```python
from polyfactory.factories.pydantic_factory import ModelFactory
from pydantic import BaseModel

class User(BaseModel):
    name: str
    email: str
    age: int

class UserFactory(ModelFactory):
    __model__ = User

user = UserFactory.build()  # Fully populated User instance
```

## Notes

- Ideal for Pydantic-heavy codebases where Factory Boy feels verbose
- Can coexist with Factory Boy — use polyfactory for Pydantic models, Factory Boy for ORM models
- Supports batch generation: `UserFactory.batch(size=10)`
