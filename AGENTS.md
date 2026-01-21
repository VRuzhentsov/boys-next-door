# Infra Guide for Agents

## Overview

Infra-first repository focused on running services via on the private server.

## Scope

Infra/service config, compose-first, no lint/test/build workflows.
Use small, targeted changes; avoid sweeping reformatting.

## Service Model

- Most services are image-based; update by changing tags and pulling.
- Some services build from local Dockerfiles; keep paths stable.
- Treat submodule functionality as external images, not source checkouts.

## Overrides and Env

- Use `docker-compose.override.yml` for local-only changes.
- Keep `.env` secrets uncommitted; provide `.env.example` placeholders.
- Avoid inline secrets in Compose files.

## Data and Networking

- Prefer named volumes for persistent data; back up before destructive changes.
- Keep bind-mount paths stable and documented.
- Expose only required ports; note UDP ranges carefully.
