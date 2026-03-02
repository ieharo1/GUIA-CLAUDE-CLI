# Guía Profesional de Claude CLI
[![Docker Ready](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)
[![Node.js 20](https://img.shields.io/badge/Node.js-20-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Idioma: Español](https://img.shields.io/badge/Idioma-Espa%C3%B1ol-blue)](#)
[![Status: Production Ready](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)](#)

Guía técnica para usar Claude CLI en local y en Docker, pensada para que el repositorio aporte valor real a un perfil técnico (Dev, DevOps y automatización).

## Objetivos

- Ejecutar Claude CLI en minutos.
- Estandarizar el entorno con Docker.
- Permitir prompts interactivos y automatización por scripts.
- Evitar fugas de secretos (API key fuera del código).

## Stack

- Claude CLI (`@anthropic-ai/claude-cli`)
- Node.js 20
- Docker / Docker Compose

## Estructura

```text
.
├── Dockerfile
├── docker-compose.yml
├── .env.example
├── entrypoint.sh
└── README.md
```

## Requisitos

- Docker Desktop o Docker Engine + Compose
- API key de Anthropic

## 1) Configurar entorno

Copia el archivo de ejemplo y carga tu clave:

```bash
cp .env.example .env
```

Edita `.env`:

```env
ANTHROPIC_API_KEY=tu_api_key_real
```

## 2) Construir imagen

```bash
docker compose build
```

## 3) Uso rápido

Mostrar ayuda:

```bash
docker compose run --rm claude --help
```

Consulta directa:

```bash
docker compose run --rm claude "Explica CQRS en 5 puntos"
```

Prompt interactivo:

```bash
docker compose run --rm claude
```

## 4) Analizar archivos del host

El compose monta `./workspace` dentro del contenedor en `/workspace`.

Ejemplo:

```bash
mkdir -p workspace
cp app.py workspace/
docker compose run --rm claude "Analiza /workspace/app.py y propone mejoras"
```

## 5) Uso en automatización

```bash
docker compose run --rm claude "Genera release notes para estos cambios"
```

Puedes integrarlo en CI con secretos del pipeline (`ANTHROPIC_API_KEY`).

## Seguridad

- No subas `.env` al repositorio.
- Rota la API key periódicamente.
- Usa una key por entorno (dev/staging/prod).
- Revisa logs antes de compartirlos.

## Solución de problemas

- `Missing ANTHROPIC_API_KEY`: revisa `.env`.
- Error de red/API: valida conectividad y cuota en Anthropic.
- Permisos con archivos montados: verifica rutas en `./workspace`.

## Licencia

MIT

