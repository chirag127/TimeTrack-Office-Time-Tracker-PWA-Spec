# Contributing to TimeGuard-Office-Time-Tracker-PWA

Thank you for considering a contribution! This project follows the **Apex Technical Authority** standards to ensure a zero‑defect, high‑velocity codebase.

---

## Table of Contents
1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [Development Workflow](#development-workflow)
4. [Code Style & Formatting](#code-style--formatting)
5. [Testing](#testing)
6. [Commit Messages](#commit-messages)
7. [Pull Request Process](#pull-request-process)
8. [Issue Reporting](#issue-reporting)
9. [Security Reporting](#security-reporting)
10. [License](#license)
11. [Acknowledgements](#acknowledgements)

---

## Code of Conduct
All contributors are expected to follow the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/). By participating, you agree to uphold a respectful and collaborative environment.

---

## Getting Started
1. **Fork** the repository: <https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/fork>
2. **Clone** your fork:
   bash
   git clone https://github.com/<your-username>/TimeGuard-Office-Time-Tracker-PWA.git
   cd TimeGuard-Office-Time-Tracker-PWA
   
3. **Install Node.js** (v20+) and **pnpm** (or npm) if not already installed.
4. **Bootstrap the project**:
   bash
   pnpm install   # or npm ci
   
5. Create an `.env.local` file based on `.env.example` for any required environment variables (e.g., API endpoints for real‑time sync). Do **not** commit this file.

---

## Development Workflow
| Step | Command | Description |
|------|---------|-------------|
| Install deps | `pnpm install` | Install all dependencies. |
| Lint & format | `pnpm lint` | Runs **Biome** with `--apply` to automatically fix style issues. |
| Unit tests | `pnpm test` | Executes **Vitest** test suite. |
| E2E tests | `pnpm e2e` | Runs **Playwright** against the PWA in headless mode. |
| Development server | `pnpm dev` | Starts **Vite** with hot‑module replacement. |
| Build for production | `pnpm build` | Produces a PWA bundle and a Tauri desktop package. |

All scripts are defined in `package.json`. Refer to the `scripts` section for the exact commands.

---

## Code Style & Formatting
- **Language:** TypeScript (strict mode enabled).
- **Formatter & Linter:** **Biome** – configuration resides in `biome.json`.
- **Styling:** **TailwindCSS v4** – follow the project's utility‑first conventions.
- **Commit‑Hook:** The repo includes a `prepare` script that installs a `pre‑commit` hook using `husky` to run `pnpm lint` before each commit. Do **not** bypass it.

If you need to adjust lint rules, modify `biome.json` **only after discussion** with maintainers.

---

## Testing
### Unit Tests (Vitest)
- Place unit tests under `tests/unit/` mirroring the source folder structure.
- Use the `@vitest/coverage` plugin for coverage reports (`pnpm test --coverage`).
- Aim for **≥ 85 %** line coverage for new code.

### End‑to‑End Tests (Playwright)
- E2E tests live in `tests/e2e/`.
- Tests must run in a headless Chromium environment and cover critical user flows: offline mode, real‑time sync, manager reporting dashboard.
- Run with `pnpm e2e` and ensure no flaky tests. Use `await page.waitForLoadState('networkidle')` where appropriate.

All test suites must pass **CI** before merging (see **Pull Request Process**).

---

## Commit Messages
Follow the **Conventional Commits** specification:

<type>(<scope>): <subject>

<body>

<footer>

- **type**: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `chore`
- **scope**: optional, e.g., `core`, `ui`, `sync`, `tauri`
- **subject**: concise, ≤ 72 characters, written in imperative mood.
- **body**: Explain *what* and *why* (wrap at 72 characters).
- **footer**: Reference issues (`Closes #123`) and breaking changes (`BREAKING CHANGE:`).

Example:

feat(sync): add optimistic offline queue

Implement an offline queue that buffers time‑entries when the network is unavailable.
Closes #42


---

## Pull Request Process
1. **Create a feature branch**: `git checkout -b feat/<short-description>`.
2. **Develop** using the workflow above.
3. **Run all checks locally**:
   bash
   pnpm lint && pnpm test && pnpm e2e
   
4. **Push** your branch to your fork.
5. **Open a Pull Request** against `main`:
   - Title must follow the Conventional Commits format.
   - Description should include:
     - Motivation & related issue(s).
     - Summary of changes.
     - Screenshots or videos for UI/UX updates.
     - Test plan (what was added/updated).
6. **CI will run automatically** (GitHub Actions defined in `.github/workflows/ci.yml`). All checks must pass.
7. **Review**: At least one maintainer must approve. Address any feedback before merging.
8. **Merge**: Use **Squash and Merge** to keep a clean history.

---

## Issue Reporting
- Search existing issues before opening a new one.
- Use the provided **Bug Report** template (`.github/ISSUE_TEMPLATE/bug_report.md`).
- Include:
  - A clear title.
  - Steps to reproduce.
  - Expected vs. actual behavior.
  - Environment details (browser, OS, Node version).
  - Screenshots or logs if applicable.

---

## Security Reporting
If you discover a vulnerability, **do not** open a public issue. Follow the guidelines in [`SECURITY.md`](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/blob/main/SECURITY.md) and contact the maintainers via the email listed therein.

---

## License
This project is licensed under the **Creative Commons Attribution‑NonCommercial 4.0 International (CC BY‑NC 4.0)**. See the [`LICENSE`](https://github.com/chirag127/TimeGuard-Office-Time-Tracker-PWA/blob/main/LICENSE) file for full details.

---

## Acknowledgements
Thanks to all contributors, the Open‑Source community, and the Apex Technical Authority framework for providing architectural guidance.

---
