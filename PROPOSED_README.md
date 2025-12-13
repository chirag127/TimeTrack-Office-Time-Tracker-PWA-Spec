# TimeGuard Office Time Tracker PWA

[![Build Status](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/actions/workflows/ci.yml/badge.svg?branch=main&style=flat-square)](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/actions) [![Coverage Status](https://codecov.io/gh/chirag127/TimeGuard-Office-Time-Tracker-PWA/branch/main/graph/badge.svg?style=flat-square)](https://codecov.io/gh/chirag127/TimeGuard-Office-Time-Tracker-PWA) [![TypeScript](https://img.shields.io/badge/TypeScript-5.4-blue?style=flat-square)](https://www.typescriptlang.org/) [![Vite](https://img.shields.io/badge/Vite-5.0-646CFF?style=flat-square)](https://vitejs.dev/) [![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.0-38B2AC?style=flat-square)](https://tailwindcss.com/) [![Tauri](https://img.shields.io/badge/Tauri-2.0-FFC107?style=flat-square)](https://tauri.app/) [![Biome](https://img.shields.io/badge/Biome-1.9-5A9DF9?style=flat-square)](https://biomejs.dev/) [![License: CC BY‑NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey?style=flat-square)](https://creativecommons.org/licenses/by-nc/4.0/) [![Stars](https://img.shields.io/github/stars/chirag127/TimeGuard-Office-Time-Tracker-PWA?style=flat-square)](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/stargazers)

[⭐ Star this repo](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA)

---

## Table of Contents
- [Overview](#overview)
- [Architecture](#architecture)
- [Installation](#installation)
- [Scripts](#scripts)
- [Development Standards](#development-standards)
- [AI Agent Directives](#ai-agent-directives)
- [Contributing](#contributing)
- [License](#license)

---

## Overview
**BLUF**: TimeGuard empowers offices to accurately record work hours offline and sync in real‑time, providing managers with instant reporting dashboards. Built as a Progressive Web App with optional Tauri desktop capabilities, it ensures seamless cross‑platform availability.

---

## Architecture
mermaid
graph LR
    subgraph Frontend["Frontend (PWA)"
        UI["UI (TypeScript + Tailwind)" ] --> ServiceWorker["Service Worker (offline & sync)" ]
        UI --> Store["State Store (Pinia/Redux)"
    ]
    subgraph Backend["Backend (Tauri)"
        API["API Layer (Vite + Tauri)" ] --> DB[("IndexedDB / SQLite")]
        API --> Sync["Sync Service (WebSocket)"
    ]
    Frontend --> API
    API --> DB
    API --> Sync


---

## Installation
bash
# Clone the repository
git clone https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA.git
cd TimeGuard-Office-Time-Tracker-PWA

# Install dependencies (uses npm; pnpm or yarn are also supported)
npm ci


---

## Scripts
| Script | Description |
|--------|-------------|
| `dev` | Run the PWA in development mode with hot‑reloading |
| `build` | Produce a production‑ready bundle (PWA & Tauri) |
| `lint` | Run Biome linting and automatic fixes |
| `test` | Execute Vitest unit tests with coverage |
| `e2e` | Run Playwright end‑to‑end tests |
| `preview` | Preview the built PWA locally |

---

## Development Standards
- **SOLID**: Enforce single‑responsibility and interface segregation throughout the codebase.
- **DRY**: Reuse components and utilities; Biome will flag duplicated logic.
- **YAGNI**: Implement only what is needed for the MVP; avoid premature abstractions.
- **Feature‑Sliced Design (FSD)**: Organize code by feature domains (`src/features/<feature>/`).
- **Continuous Integration**: Every PR must pass lint, unit, and e2e pipelines before merge.

---

## AI Agent Directives
<details>
<summary>Click to expand AI Agent Directives</summary>

markdown
# SYSTEM: APEX TECHNICAL AUTHORITY & PRINCIPAL AI ARCHITECT (DECEMBER 2025 EDITION)

## 1. IDENTITY & PRIME DIRECTIVE
- **Product**: TimeGuard Office Time Tracker PWA
- **Goal**: Deliver a zero‑defect, high‑velocity, future‑proof time‑tracking solution with offline‑first capabilities.
- **Philosophy**: Zero‑Defect, High‑Velocity, Future‑Proof, AI‑Native.

## 2. TECH STACK DEFINITION
- **Language**: TypeScript (strict mode)
- **Build Tool**: Vite
- **UI Framework**: TailwindCSS (utility‑first styling)
- **Desktop Wrapper**: Tauri (provides native bridges & offline support)
- **Lint/Format**: Biome (fast, opinionated, auto‑fix)
- **Unit Testing**: Vitest (Jest‑compatible, native ESM)
- **E2E Testing**: Playwright (cross‑browser automation)
- **Package Manager**: npm (lockfile `package-lock.json`)
- **CI/CD**: GitHub Actions (workflow `ci.yml`)

## 3. ARCHITECTURAL PATTERNS
- **Feature‑Sliced Design (FSD)** – modular feature domains under `src/features/`.
- **SOLID** – enforce single‑responsibility, open‑closed, Liskov substitution, interface segregation, and dependency inversion.
- **DRY & YAGNI** – Biome will surface duplicated code; only implement needed features.

## 4. VERIFICATION COMMANDS
bash
# Lint & auto‑format
npm run lint

# Unit tests with coverage
npm run test

# End‑to‑end tests
npm run e2e

# Build production artifact
npm run build

# Run locally (development server)
npm run dev


## 5. OPERATIONAL GUIDELINES
- Run `npm audit` weekly and remediate vulnerabilities.
- Keep dependencies fresh with `npm outdated` + `npm update`.
- CI must succeed on every push; failures block merging.
- Use the provided `CEREBRAS_API_KEY` environment variable for any AI‑assisted tooling.


</details>

---

## Contributing
We welcome contributions! Please read our [CONTRIBUTING.md](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/blob/main/CONTRIBUTING.md) for guidelines on how to propose changes, report bugs, and submit pull requests.

---

## License
This project is licensed under the **Creative Commons Attribution‑NonCommercial 4.0 International (CC BY‑NC 4.0)**. See the [LICENSE](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/blob/main/LICENSE) file for details.
