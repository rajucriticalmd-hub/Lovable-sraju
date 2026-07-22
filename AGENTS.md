# AGENTS.md

## Cursor Cloud specific instructions

### Current repository state

As of this setup, the repository contains **no application code** — only `README.md`
(`# Lovable-sraju`). There is nothing to install, build, run, or test yet.

This repo is named after a [Lovable](https://lovable.dev) project. Lovable projects use a
Vite + React + TypeScript + Tailwind CSS + shadcn/ui stack. The generated code has not yet
been synced/pushed from Lovable to this GitHub repository. Until that happens, there is no
dev environment to run.

### Once application code is present

When the Lovable project code lands (expect a `package.json`, a lockfile, and `src/`):

- Install deps with the package manager matching the committed lockfile
  (`package-lock.json` → `npm ci` / `npm install`, `bun.lockb` → `bun install`,
  `pnpm-lock.yaml` → `pnpm install`). The update script already runs `npm install`
  whenever a `package.json` exists.
- Typical Lovable/Vite scripts (verify against `package.json` when it exists):
  - Dev server: `npm run dev` (Vite, default port `8080` for Lovable, `5173` for stock Vite)
  - Lint: `npm run lint`
  - Build: `npm run build`
  - Preview production build: `npm run preview`
- The Vite dev server binds to a port; when testing in this environment, confirm the port
  from the Vite startup log rather than assuming.

Node `v22` and npm `10` are available in this environment.
