# NiceGUI

> Create web-based user interfaces with Python. The nice way.

| | |
|---|---|
| **Website** | [nicegui.io](https://nicegui.io/) |
| **Repository** | [github.com/zauberzeug/nicegui](https://github.com/zauberzeug/nicegui) |
| **PyPI** | [pypi.org/project/nicegui](https://pypi.org/project/nicegui/) |
| **Status** | 🟢 Active |

## Why NiceGUI

- Build full web UIs in pure Python — no HTML/JS/CSS required
- Declarative layout using Python's `with` statement
- Automatic data binding keeps UI in sync with application state
- Native desktop mode (Electron-like) for standalone apps
- Built on FastAPI — seamlessly mix REST APIs with interactive UI
- Tailwind CSS and Quasar components out of the box

## Core Stack

| Component | Role |
|---|---|
| [FastAPI](https://fastapi.tiangolo.com/) | ASGI backend, routing, API endpoints |
| [Vue.js](https://vuejs.org/) / [Quasar](https://quasar.dev/) | Frontend rendering and component library |
| [Uvicorn](https://www.uvicorn.org/) | ASGI server |
| [Tailwind CSS](https://tailwindcss.com/) | Utility-first styling (enabled by default) |

## Key Use Cases

- Internal tools and admin dashboards
- IoT control panels and robotics interfaces
- Data visualization and monitoring dashboards
- ML/AI demo apps and prototypes
- Desktop applications via native mode

## Notable Features

| Feature | Description |
|---|---|
| Data binding | Two-way binding between UI elements and Python objects |
| Refreshable decorator | `@ui.refreshable` for reactive UI sections |
| Native mode | `ui.run(native=True)` for desktop window |
| 3D scenes | Built-in 3D scene rendering |
| Jupyter support | Run NiceGUI inside notebooks |
| On Air | `on_air=True` for temporary remote access without deployment |

## Ecosystem & Extensions

| Library | Purpose |
|---|---|
| `nicegui-tabulator` | Advanced table component with pandas integration |
| `nicegui-highcharts` | Highcharts integration for data visualization |
| `pywebview` | Powers the native desktop mode |

## Notes

- Use `storage_secret` parameter in `ui.run()` for persistent browser storage
- Supports hot-reload during development by default
- Deploy with Docker or Google Cloud Run; use Redis for multi-instance scaling
- Combine with FastAPI routes for hybrid API + UI applications
