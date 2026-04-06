# Backend Foundation

## Overview
This directory contains the initial FastAPI backend foundation for SalesTool.

## Local development
1. Copy `.env.example` to `.env`
2. Install dependencies
3. Run the API with Uvicorn
4. Run Alembic migrations

## Commands
Start the API:

```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Create a migration:

```bash
alembic revision -m "create foundation"
```

Run migrations:

```bash
alembic upgrade head
```
