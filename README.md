# TimeGuard Office Time Tracker PWA

![TimeGuard Logo](https://raw.githubusercontent.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/main/assets/logo.png)

[![Build Status](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/actions/workflows/ci.yml/badge.svg?branch=main&style=flat-square)](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/actions)
[![Coverage Status](https://codecov.io/gh/chirag127/TimeGuard-Office-Time-Tracker-PWA/branch/main/graph/badge.svg?style=flat-square)](https://codecov.io/gh/chirag127/TimeGuard-Office-Time-Tracker-PWA)
[![Tech Stack](https://img.shields.io/badge/Tech-Typescript%20%7C%20Vite%20%7C%20TailwindCSS%20%7C%20Tauri-blue?style=flat-square)](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA)
[![Lint](https://img.shields.io/badge/Lint-Biome-5f5f5f?style=flat-square)](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey?style=flat-square)](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/blob/main/LICENSE)
[![Stars](https://img.shields.io/github/stars/chirag127/TimeGuard-Office-Time-Tracker-PWA?style=flat-square)](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/stargazers)

---

## ⭐️ Star this Repo
If you find TimeGuard useful, please give it a star to show your support! ★

---

## 🎯 Quick Pitch (BLUF)
**TimeGuard** is a Progressive Web App that lets employees log work hours effortlessly, even offline, while providing managers real‑time sync and detailed reporting. Built with TypeScript, Vite, TailwindCSS, and Tauri, it delivers a seamless, cross‑platform experience.

---

## 📐 Architecture Overview
mermaid
graph TD;
    subgraph Client
        UI[UI (Vite + TailwindCSS)] --> ServiceWorker[Service Worker (offline sync)]
        UI --> Tauri[Tauri Native Bridge]
    end;
    subgraph Backend
        Sync[Realtime Sync Service] --> DB[Database]
        Sync --> Report[Manager Reporting API]
    end;
    ServiceWorker --> Sync;
    Tauri --> Sync;
    Report --> UI;


---

## 📑 Table of Contents
- [Quick Pitch](#-quick-pitch-bluf)
- [Architecture Overview](#-architecture-overview)
- [AI Agent Directives](#-ai-agent-directives)
- [Development Standards](#-development-standards)
- [Contributing](#-contributing)
- [License](#-license)

---

<details>
<summary>🤖 AI Agent Directives</summary>

**Tech Stack Definition**
- **Language:** TypeScript (strict mode)
- **Build Tool:** Vite
- **Styling:** TailwindCSS v4
- **Desktop Bridge:** Tauri v2 (provides native capabilities & PWA fallback)
- **Lint/Format:** Biome (fast, auto‑fix)
- **Testing:** Vitest (unit) & Playwright (E2E)
- **Package Manager:** npm (or pnpm) with lockfile

**Architectural Patterns**
- **Feature‑Sliced Design (FSD):** Organize `src/` by feature domains (`src/features/timeEntry`, `src/features/reporting`, etc.).
- **SOLID & DRY:** Enforce interface segregation and single‑responsibility for service layers.
- **Offline‑First:** Service Worker caches API payloads; sync layer resolves conflicts on reconnection.
- **Continuous Delivery:** GitHub Actions CI runs lint, tests, builds, and publishes a preview on Vercel/Netlify.

**Verification Commands**
bash
# Install dependencies
npm ci

# Run lint & auto‑fix
npm run lint

# Run unit tests
npm run test:unit

# Run end‑to‑end tests
npm run test:e2e

# Build for production
npm run build


These commands are the canonical entry points for any autonomous agent interacting with the repo.

</details>

---

## 🛠 Development Standards

### Setup
bash
# Clone the repo
git clone https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA.git
cd TimeGuard-Office-Time-Tracker-PWA

# Install dependencies (uses lockfile for reproducibility)
npm ci


### Available Scripts
| Script | Description |
|--------|-------------|
| `dev` | Starts Vite dev server with hot‑module reload |
| `build` | Produces a production‑ready bundle |
| `lint` | Runs Biome linting and auto‑fixes |
| `test:unit` | Executes Vitest unit tests |
| `test:e2e` | Launches Playwright end‑to‑end suite |
| `preview` | Serves the built app locally for QA |

### Core Principles
- **SOLID** – Keep modules extensible and maintainable.
- **DRY** – Reuse components and utility functions across features.
- **YAGNI** – Implement only what the product needs today.
- **Zero‑Defect** – CI enforces 100 % test coverage and lint passing before merge.

---

## 🤝 Contributing
We welcome contributions! Please read our [CONTRIBUTING.md](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/blob/main/CONTRIBUTING.md) for guidelines on how to propose enhancements, report bugs, and submit pull requests.

---

## 📄 License
This project is licensed under the **Creative Commons Attribution‑NonCommercial 4.0 International (CC BY‑NC 4.0)**. See the full text in the [LICENSE](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/blob/main/LICENSE) file.
