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
