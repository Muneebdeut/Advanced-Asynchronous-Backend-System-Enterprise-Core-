# Core-Auth

FastAPI auth API with JWT login, refresh tokens, Redis logout blacklist, and a simple web UI.

## Structure

```
app/
  main.py       # app entry + static frontend
  config.py     # .env settings
  database.py   # SQLAlchemy + Redis
  models.py     # User table
  schemas.py    # request/response types
  security.py   # passwords + JWT
  services.py   # users + token blacklist
  deps.py       # auth dependency
  routes.py     # API routes
frontend/       # HTML/CSS/JS UI
tests/
```

## Setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
uvicorn app.main:app --reload
```

Open http://localhost:8000 — API docs at http://localhost:8000/docs

## Tests

```bash
pytest
```

## API

| Method | Path | Auth |
|--------|------|------|
| POST | `/api/v1/auth/register` | no |
| POST | `/api/v1/auth/login` | no |
| GET | `/api/v1/auth/me` | yes |
| POST | `/api/v1/auth/refresh` | no |
| POST | `/api/v1/auth/logout` | yes |
| GET | `/api/v1/health` | no |
