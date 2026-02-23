# Repository Cleanup Notes

## Date
- 2026-02-23

## Initial Findings
- Branch: `cleanup` (clean working tree at start).
- Existing structure was already close to target: root + `backend/` + `packages/` pnpm workspace + `docs/`.
- `packages/` is the active frontend monorepo (`pnpm-workspace.yaml` targets `packages/*`), so it remains canonical instead of forcing a risky move to `frontend/`.
- No duplicate code directories were found that could be safely removed.
- No tracked generated artifacts were found (`node_modules`, `dist`, `__pycache__`, `.pytest_cache`, logs, DB files, media exports).
- Root had two documentation files that fit better under `docs/`: `NOTES.md` and `career co pilot.md`.

## Executed Changes
- Moved root docs into `docs/` with history-preserving moves:
  - `NOTES.md` -> `docs/scaffolding-notes.md`
  - `career co pilot.md` -> `docs/career-co-pilot.md`
- Kept one canonical root `README.md`; retained package-level `NOTES.md` files because they are package-scoped.
- Expanded `.gitignore` to cover Node, Python, OS/editor, DB/local data, secrets, and Playwright artifacts.
- Updated root `README.md` with repository layout and local run/build commands.

## Decisions and Rationale
- Kept `packages/` as-is to avoid breaking workspace scripts and Docker/frontend build paths.
- Avoided deleting any uncertain content; no `archive/` move was needed based on current repo state.

## Validation Run
- `docker compose config` -> passed (compose configuration resolves correctly after cleanup).
- `docker compose build` -> blocked (Docker daemon socket unavailable at `~/.docker/run/docker.sock` in this environment).
- `npm run build` -> blocked (`pnpm` not installed in environment).
- `npx pnpm@9 --version` -> blocked (network/DNS to `registry.npmjs.org` unavailable).
- `python3 -m pytest backend/tests` -> blocked (`pytest` not installed in environment).
- `python3 -m compileall backend/app backend/tests` -> passed (backend source compiles without syntax errors).

## Follow-ups
- Install `pnpm` (or enable Corepack) and rerun frontend workspace checks.
- Start Docker daemon and rerun `docker compose build && docker compose up -d`.
- Create backend venv, install `backend/requirements.txt`, and rerun `python3 -m pytest backend/tests`.
- If docs taxonomy should be stricter, consider grouping package-scoped notes under `docs/packages/` in a future refactor.
