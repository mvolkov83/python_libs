# python-jose

> JOSE implementation for Python (JWS, JWE, JWK, JWT)

| | |
|---|---|
| **Repository** | [github.com/mpdavis/python-jose](https://github.com/mpdavis/python-jose) |
| **PyPI** | [pypi.org/project/python-jose](https://pypi.org/project/python-jose/) |
| **Status** | 🟢 Active (⚠️ abandoned) |

## Why python-jose (historically)

- Full JOSE stack — JWS, JWE, JWK, JWT in one package
- Multiple cryptographic backends (cryptography, pycryptodome)
- Recommended by FastAPI docs (until 2024)

## ⚠️ Maintenance Status

- **Last release:** 2021
- **Unpatched CVEs** and open security issues
- FastAPI officially migrated documentation to PyJWT
- No response to PRs or issues from maintainer

## Migration Options

| Library | Scope | Notes |
|---|---|---|
| [joserfc](joserfc.md) | Full JOSE (JWS, JWE, JWK, JWT) | From Authlib author, actively maintained |
| PyJWT | JWT only (JWS + JWT) | Simpler, if you only need JWT encode/decode |

**Recommendation:** Use [joserfc](joserfc.md) for full JOSE support, PyJWT if you only need JWT.
