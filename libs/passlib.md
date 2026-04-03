# passlib

> Password hashing library for Python

| | |
|---|---|
| **Website** | [passlib.readthedocs.io](https://passlib.readthedocs.io/) |
| **PyPI** | [pypi.org/project/passlib](https://pypi.org/project/passlib/) |
| **Status** | 🟢 Active (⚠️ legacy) |

## Why passlib (historically)

- Unified interface for 30+ password hashing algorithms
- Automatic hash migration between schemes
- Widely used in FastAPI and Flask projects

## ⚠️ Maintenance Status

- **Last release:** 2020
- **Python 3.13+:** Broken due to removal of the `crypt` module
- **No active maintenance** — multiple issues and PRs unaddressed
- FastAPI official docs switched to pwdlib

## Migration Path → pwdlib

[pwdlib](pwdlib.md) is a modern replacement created by François Voron (fastapi-users author):
- Supports Argon2 and bcrypt
- Clean, minimal API
- Actively maintained
- Adopted by FastAPI documentation

**Recommendation:** Migrate to [pwdlib](pwdlib.md) for new projects and when upgrading to Python 3.13+.
