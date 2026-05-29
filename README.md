# RootIQ

An enterprise-grade, production-ready full-stack platform for **real-time error monitoring, AI-powered root cause analysis, and intelligent incident management**.

---

## Architecture Overview

```
Client Applications
       │
       ▼
   Nginx (Reverse Proxy)
       │
       ├── /api/v1/*  ──►  FastAPI Backend  ──►  PostgreSQL
       │                        │
       │                        ├──►  Redis Queue
       │                        │         │
       │                        │         ▼
       │                        │    Log Worker ──► OpenRouter AI
       │                        │
       │                        └──►  WebSocket (Real-time)
       │
       └── /*  ──►  React Frontend (SPA)
```

### Technology Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | FastAPI + Python 3.12 |
| **Database** | PostgreSQL 16 (async via asyncpg) |
| **ORM** | SQLAlchemy 2.0 (async) |
| **Queue** | Redis (list-based async queue) |
| **AI Engine** | OpenRouter (OpenAI-compatible, model-configurable) |
| **Frontend** | React 18 + TypeScript + Vite |
| **State** | Zustand + TanStack Query |
| **Charts** | Recharts |
| **Styling** | Tailwind CSS v3 |
| **Real-time** | WebSocket (FastAPI native) |
| **Auth** | JWT (PyJWT — access + refresh tokens) + bcrypt |
| **Email** | SMTP with TLS (HTML incident alerts) |
| **Container** | Docker + Docker Compose |
| **Proxy** | Nginx |

<img width="2990" height="1678" alt="8775DCCB-BB01-4255-8A19-68C7EBBBD19E" src="https://github.com/user-attachments/assets/216ac0cd-395e-436d-b01a-31469d24be85" />

<img width="2990" height="1702" alt="2393B303-618E-48E7-BDE8-DDE0F05CAD41" src="https://github.com/user-attachments/assets/412e6c49-d1ea-4a03-894d-47fdec1c828f" />

