# Binary Distribution Repo Design

[![English](https://img.shields.io/badge/lang-English-0A66C2)](2026-04-11-binary-distribution-repo-design.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-BDBDBD)](2026-04-11-binary-distribution-repo-design.ko.md)

## Goal

Define a simple, company-wide structure for distributing privately built binaries without turning this repository into the canonical engineering audit system.

## Decision

This repository is a product-first distribution hub.

- Products are the primary unit of organization.
- Source code repositories remain the source of truth for build history, changelogs, QA evidence, provenance, and compatibility guarantees.
- This repository owns distribution-facing assets:
  - release metadata and links
  - install and uninstall scripts
  - lightweight product documentation
  - landing pages or HTML entrypoints
  - agent-facing guidance for installation or rollout tasks

## Rationale

This structure keeps the repository easy to browse and cheap to operate.

- Product-first organization matches how users look for binaries.
- Keeping binaries in release assets avoids git history bloat.
- Team-first organization would make ownership easier short-term but would hurt company-wide discoverability.
- Compliance-heavy requirements should stay with the product repositories that actually build the software.

## Repository Shape

The repo should expose one stable folder per product under `products/`.

Each product may contain:

- `README.md`
- `README.ko.md`
- `product.yaml`
- `docs/`
- `install/`
- `uninstall/`
- `pages/`
- `agents/`

## Release Rules

- Use one stable product slug per product.
- Use product-scoped version tags in the form `product-slug/vX.Y.Z`.
- Publish binaries primarily as release assets, not regular git blobs.
- Use prerelease channels only for `alpha`, `beta`, or `rc` style builds.
- Stable releases should remain easy for humans to identify and install.

## Non-Goals

- Full audit trail in this repository
- Deep QA or compatibility reporting in this repository
- Committing large binary histories directly into git
