# Architecture

## Overview
This repo contains a custom Yocto layer and documentation to build a BBB image used by the larger telemetry system.

## Key goals
- Reproducible builds (documented inputs and versions)
- Minimal image + room to add an agent service
- Clear flashing + debug instructions

## Components
- Custom layer (`meta-edge`)
- Build configuration samples (`configs`)
- Setup scripts (`scripts`)
- Documentation (`docs`)

## Outputs
- Yocto image artifacts (generated locally): not committed
- A runnable OS image for BBB
