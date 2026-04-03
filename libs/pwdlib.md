# pwdlib

> Modern password hashing helper for Python

| | |
|---|---|
| **Website** | [frankie567.github.io/pwdlib](https://frankie567.github.io/pwdlib/) |
| **Repository** | [github.com/frankie567/pwdlib](https://github.com/frankie567/pwdlib) |
| **PyPI** | [pypi.org/project/pwdlib](https://pypi.org/project/pwdlib/) |
| **Status** | 🔵 Exploring |

## Why pwdlib

- Created as a modern passlib replacement by the fastapi-users author
- Supports **Argon2** and **bcrypt** — the two recommended hashing algorithms
- Minimal, clean API — hash and verify in one line
- Actively maintained and compatible with Python 3.13+
- Adopted by FastAPI official documentation

## Usage

```python
from pwdlib import PasswordHash

ph = PasswordHash.recommended()
hashed = ph.hash("my_password")
verified = ph.verify("my_password", hashed)
```

## Compared to passlib

| Feature | passlib | pwdlib |
|---|---|---|
| Algorithms | 30+ | Argon2, bcrypt |
| Python 3.13+ | ❌ Broken | ✅ |
| Maintenance | Stalled (2020) | Active |
| API complexity | High | Minimal |
| Hash migration | Built-in | Manual |

## Notes

- Install with extras: `pwdlib[argon2]` or `pwdlib[bcrypt]`
- Does not support passlib's hash migration — handle scheme upgrades manually if migrating
- Recommended by fastapi-users for password hashing
