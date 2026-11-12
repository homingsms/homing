# Homing

Homing turns Android phones into an SMS gateway you control: send and receive SMS and MMS through an API, get delivery reports and inbound messages as webhooks, and manage a fleet of phones from one console.

## Repository layout

This root repository only holds this README and `.gitignore`. Each surface is its own Git repository, cloned into a folder of the same name from its long-lived branch:

| Folder | Branch | What it is |
| --- | --- | --- |
| `android/` | `android` | The Homing Android app (Kotlin, Jetpack Compose) with its built-in local API server |
| `backend/` | `backend` | Homing Cloud API (NestJS 11, PostgreSQL, Redis). Owns the shared API contracts in `packages/contracts/` |
| `frontend/` | `frontend` | Homing Cloud web console (Next.js) |

## Getting the code

```bash
git clone --branch main --single-branch <remote> homing
cd homing
git clone --branch android --single-branch <remote> android
git clone --branch backend --single-branch <remote> backend
git clone --branch frontend --single-branch <remote> frontend
```

Each surface README lists its own setup, commands and checks.
