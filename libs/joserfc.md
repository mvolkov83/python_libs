# joserfc

> Modern JOSE implementation for Python

| | |
|---|---|
| **Website** | [jose.authlib.org](https://jose.authlib.org/) |
| **Repository** | [github.com/authlib/joserfc](https://github.com/authlib/joserfc) |
| **PyPI** | [pypi.org/project/joserfc](https://pypi.org/project/joserfc/) |
| **Status** | 🔵 Exploring |

## Why joserfc

- Full JOSE implementation: JWS, JWE, JWK, JWT
- By the Authlib author (Hsiaoming Yang) — well-maintained
- BSD licensed, extracted from Authlib for standalone use
- Provides migration guides from both python-jose and PyJWT
- Type-annotated, modern Python API

## Key Features

| Feature | Description |
|---|---|
| JWS | JSON Web Signature — signing and verification |
| JWE | JSON Web Encryption — encrypt/decrypt tokens |
| JWK | JSON Web Key — key management and JWK Sets |
| JWT | JSON Web Token — claims-based tokens |
| Registry | Extensible algorithm registry |

## Migrating from python-jose

```python
# python-jose (old)
from jose import jwt
token = jwt.encode(claims, key, algorithm="HS256")
data = jwt.decode(token, key, algorithms=["HS256"])

# joserfc (new)
from joserfc import jwt
token = jwt.encode({"alg": "HS256"}, claims, key)
data = jwt.decode(token, key)
```

Full guide: [jose.authlib.org/en/migrations/python-jose](https://jose.authlib.org/en/migrations/python-jose/)

## Notes

- Install: `pip install joserfc`
- Use `joserfc.jwk` for key generation and import/export
- Supports RSA, EC, OKP, and symmetric keys
