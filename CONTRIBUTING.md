# Contributing

Thanks for your interest in contributing!

This repository contains a custom Yocto layer and supporting configuration/scripts for building a BeagleBone Black (BBB) Linux image. The goals are reproducibility and excellent documentation.

## Ground rules
- **Do not commit Yocto build output** (e.g. `build*/`, `tmp*/`, `downloads*/`, `sstate-cache*/`).
- Keep changes small and reviewable.
- Update documentation whenever build steps or behavior changes.

## Changelog and decisions (required)
- **Update `CHANGELOG.md` on every push** (at minimum the `Unreleased` section).
- If you make a major decision (tooling, layer strategy, image contents, boot approach), **add/update an ADR** in `docs/decisions/`.

## Prerequisites
- Linux host (Fedora recommended)
- `git`, `bash`
- A Yocto/poky checkout available locally (often kept **outside** this repo)
- Basic familiarity with BitBake/Yocto

## Repository layout
- `meta-edge/` — custom Yocto layer (recipes, classes, configs)
- `configs/` — sample `local.conf` / `bblayers.conf`
- `scripts/` — helper scripts (setup build dir, sanity checks)
- `docs/` — build/flash/debug documentation
- `.github/` — CI workflows (intentionally lightweight)

## Getting started
1. Clone this repository.
2. Optional: copy env example for scripts:
   ```bash
   cp .env.example .env
   ```
3. Initialize a build directory (if script exists):
   ```bash
   ./scripts/setup-build.sh
   ```
4. Follow the documentation:
   - `docs/build.md`
   - `docs/flash.md`
   - `docs/debug.md`

## Making changes

### Layer changes (recipes, bbappends, classes)
- Keep recipes focused and minimal.
- Prefer explicit versions and checksums where appropriate.
- Document why a new recipe exists (short note in the recipe or an ADR).

### Configuration changes
- If you change sample configs, update `docs/build.md` accordingly.
- Avoid machine-specific absolute paths.

### Scripts
- Prefer safe bash defaults where appropriate:
  - `set -euo pipefail`
- Keep scripts idempotent when possible.
- Add usage/help text for scripts that take arguments.

### Documentation
- Keep docs accurate and practical.
- Add an ADR under `docs/decisions/` for major changes.

## Quality checks
CI is intentionally lightweight. If you add shell scripts, run:
```bash
shellcheck scripts/*.sh
```

## Commit message guidelines
Use concise, imperative messages:
- "Add setup script for build directory"
- "Document flashing steps for SD card"

## Pull requests
- Describe what changed and why.
- Link related issues.
- Include verification steps (especially for build/flash changes).
