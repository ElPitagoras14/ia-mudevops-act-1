# Book Booker

Sistema de gestión de reservas de libros.

## Requisitos

- [Docker](https://docs.docker.com/get-docker/)
- [uv](https://docs.astral.sh/uv/getting-started/installation/)
- [pnpm](https://pnpm.io/installation)

## Inicio rápido

### 1. Base de datos

```bash
docker compose up -d
```

### 2. Backend

```bash
cd backend
cp .env.example .env
uv sync
uv run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

### 3. Frontend

```bash
cd frontend
pnpm install
pnpm run dev
```

El frontend corre en `http://localhost:3000` y el backend en `http://localhost:8000`.

## Credenciales de prueba

| Usuario | Contraseña | Rol |
|---------|-----------|-----|
| admin   | admin123  | Admin |
| user    | user123   | User |

## Tests

**Backend:**

```bash
cd backend
uv run pytest
```

**Frontend:**

```bash
cd frontend
pnpm test
```

## Tasks de VSCode

El proyecto incluye tareas preconfiguradas en `.vscode/tasks.json`:

| Tarea | Descripción |
|-------|-------------|
| `Docker: PostgreSQL up` | Levanta la base de datos |
| `Backend: dev server` | Inicia el servidor de FastAPI |
| `Frontend: dev server` | Inicia el servidor de Vite |
| `Run All` | Ejecuta todo en secuencia |

Abrí las tareas con `Ctrl+Shift+B` (o `Cmd+Shift+B` en macOS).
