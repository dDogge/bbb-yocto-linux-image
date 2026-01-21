# Contributing

## Requirements
- Linux host (Fedora recommended)
- Git
- Yocto/poky checkout (kept outside this repo or as a submodule)

## Setup
- Copy `.env.example` to `.env` if you want scripts to read variables.
- Run `scripts/setup-build.sh` to initialize a build directory.

## Guidelines
- Do not commit Yocto build output (`build*/`, `tmp*/`, `downloads*/`, `sstate-cache*/`).
- Keep docs updated when build steps change.
- Prefer small commits: one change = one commit.
