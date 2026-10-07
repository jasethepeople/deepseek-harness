# DeepSeek Harness

**This is a fork** of [deepseek-ai/deepseek-harness](https://github.com/deepseek-ai/deepseek-harness), the open-source agent harness by DeepSeek AI, kept for local reference. The description below comes from the upstream project's own README and the files in this checkout.

DeepSeek Harness (`dsh`) uses an architecture where **everything is a plugin**, powered by [Cordis](https://github.com/cordiverse/cordis) (design described in [_A Programming Paradigm for Spatiotemporal Composability_](https://github.com/cordiverse/paper)).

## Features

- Plugin-based agent runtime: tools, providers, UIs, and workflows are all plugins.
- Web UI served locally (default `http://127.0.0.1:3080`).
- TypeScript + Python client packages (`packages/`, `python/`), example plugins (`examples/`), and native components (`native/`).
- Project website source in `website/`; full development and architecture docs in `docs/`.
- i18n documentation (English + Chinese: `README.zh.md`, `CONTRIBUTING.zh.md`).
- Third-party licenses disclosed in `THIRD_PARTY_NOTICES.md`.

## Tech stack

- pnpm workspaces, TypeScript, Vitest (unit, e2e, snapshot, web perf/stress configs).
- Cordis plugin framework; tsdown for builds; Lefthook for git hooks; Knip for unused-export checks.
- Python SDK under `python/` (`pytest.ini`).

## Getting started

Run from npm (no clone needed):

```sh
npx @deepseek-ai/dsh web
```

Run from source:

```sh
git clone https://github.com/deepseek-ai/deepseek-harness.git
cd deepseek-harness
pnpm install
pnpm run build
pnpm dsh web
```

Then open the Web UI guide at `docs/user/guide/index.md`. For contributors: see `CONTRIBUTING.md`; agent conventions are in `AGENTS.md`; development setup in `docs/development.md`.

## Project structure

```
├── apps/        # applications (including the web UI)
├── packages/    # core and plugin packages
├── python/      # Python SDK
├── native/      # native components
├── examples/    # example plugins
├── docs/        # development, architecture, user guides
├── website/     # project website
├── scripts/     # build/dev scripts
└── vendor/      # vendored dependencies
```

## Status

**Fork — developer preview.** Upstream warns the project is in developer preview and iterating rapidly, so **compatibility-breaking changes should be expected**. License: MIT.
