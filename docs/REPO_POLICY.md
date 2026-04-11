# Repository Policy

[![English](https://img.shields.io/badge/lang-English-0A66C2)](REPO_POLICY.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-BDBDBD)](REPO_POLICY.ko.md)

## 1. Repository Role

This repository is the company distribution hub for privately built binaries.

It exists to make released software easy to find, understand, and install. It does not replace the source code repository for a product.

The source code repository remains responsible for:

- build history
- detailed changelogs
- QA evidence and test logs
- signing, provenance, and supply-chain details
- compatibility guarantees and support policy

This repository is responsible for:

- human-friendly product discovery
- distribution metadata
- install and uninstall helpers
- lightweight documentation for released binaries
- release pages and links
- agent-facing operational instructions
- distribution status inside this hub

## 2. Top-Level Organization

The repository is organized by product, not by team and not by platform.

Use:

```text
products/<product-slug>/
```

Do not use team names as the primary hierarchy. Team ownership can change, but product identity should stay stable.

## 3. Product Slug Rules

Each product must have one stable slug.

Rules:

- use lowercase letters, numbers, and hyphens only
- keep the slug short and durable
- do not encode team names into the slug unless the product itself is team-scoped
- do not rename a slug without a migration decision

Examples:

- `agent-console`
- `docs-sync`
- `media-uploader`

## 4. Product Folder Rules

Each product folder should follow this shape:

```text
products/<product-slug>/
  README.md
  README.ko.md
  product.yaml
  docs/
  install/
  uninstall/
  pages/
  agents/
```

### Required Files

- `README.md`
- `README.ko.md`
- `product.yaml`

### Optional Directories

- `docs/`
- `install/`
- `uninstall/`
- `pages/`
- `agents/`

Only keep a directory if it has an actual role for that product. The template includes all directories so the intended shape is visible, but real products may remove unused ones.

### Content Boundaries

- `README.md`
  - explain what the product is
  - link to the source repository
  - link to the product releases page
  - explain the normal install path
- `README.ko.md`
  - provide the Korean companion for `README.md`
  - stay aligned with the English entrypoint
- `product.yaml`
  - store stable metadata used by humans or tooling
  - do not duplicate current version numbers from release assets
- `docs/`
  - release usage notes, migration notes, operator notes
- `install/`
  - scripts that help install or bootstrap the released binary
- `uninstall/`
  - scripts that remove installed files or undo setup
- `pages/`
  - static HTML or assets used as a distribution landing page
- `agents/`
  - instructions for agents that need to install, upgrade, verify, or roll back the product

## 5. Documentation Language Rules

English is the default language for canonical repository documentation.

Rules:

- keep the primary file in English using the normal `.md` name
- add a Korean companion file using the same base name with `.ko.md`
- place language switch badges or equivalent links at the top of both files
- if an English and Korean document disagree, the English document is the canonical source until both are reconciled
- human-facing guides should be provided in both English and Korean

Examples:

- `README.md` and `README.ko.md`
- `setup.md` and `setup.ko.md`
- `migration-guide.md` and `migration-guide.ko.md`

At minimum, provide both English and Korean for:

- repository or product entrypoint READMEs
- install and uninstall guides written for humans
- rollout, operator, and migration guides
- other human-facing guidance under `docs/` or `agents/`

## 6. Required Product Metadata

Each product should declare at least:

- stable product slug
- product display name
- maintainer or owning team
- upstream source repository
- releases page URL
- default release channel
- distribution status in this repository

Keep this in `product.yaml` so humans and tooling can find it quickly.

`distribution_status` is authoritative only for how this distribution hub should present the product. It does not replace the upstream product's support policy. If upstream support policy and this hub's distribution status differ, upstream support policy wins and the product README should explain the discrepancy.

## 7. Release Rules

Actual binary payloads should mainly be published as release assets rather than committed directly into git.

Release tags and attached release assets are the source of truth for released versions. Do not store `latest_version` or other current-version fields in `product.yaml`.

### Versioning

- use semantic versions unless a product has a clear reason not to
- stable releases should use `vX.Y.Z`
- prereleases may use `vX.Y.Z-beta.1`, `vX.Y.Z-rc.1`, and similar forms

### Tags

Use product-scoped tags:

```text
<product-slug>/vX.Y.Z
```

Examples:

- `agent-console/v1.4.0`
- `docs-sync/v0.9.2-beta.1`

This avoids collisions when multiple products share one repository.

### Release Titles

Use:

```text
<product-slug> X.Y.Z
```

### Asset Naming

Use a predictable asset name:

```text
<product-slug>_<version>_<os>_<arch>.<ext>
```

Examples:

- `agent-console_1.4.0_macos_arm64.tar.gz`
- `agent-console_1.4.0_linux_amd64.tar.gz`
- `docs-sync_0.9.2-beta.1_windows_amd64.zip`

### Canonical Tokens

Use only the following canonical tokens unless a documented exception is added to the product README.

- `os`: `macos`, `linux`, `windows`
- `arch`: `arm64`, `amd64`
- `ext`: `tar.gz`, `zip`, `dmg`, `pkg`, `msi`, `exe`

Do not mix synonyms such as `darwin` and `macos`, or `x86_64` and `amd64`, in published asset names.

### Channels

Use channels only when they have operational meaning.

- `stable`: default install target for normal users
- `beta`: preview builds for limited internal testing
- `rc`: release candidate before stable promotion

Do not create extra channels unless there is an actual rollout need.

### Minimum Release Note Fields

Each release should include at least:

- product name and version
- source repository link
- source commit, tag, or build reference
- build date or release date
- supported platforms
- signing status if relevant
- install or upgrade instructions
- rollback or uninstall reference when relevant

### Release Asset Requirements

Each published binary should satisfy all of the following:

- asset name matches the repository naming rule
- platform and architecture are unambiguous
- release note points to install guidance
- source reference can be traced back to the upstream product repository

## 8. Deprecation, Deletion, And Distribution Status

Each product should carry a simple `distribution_status` in `product.yaml`.

Recommended values:

- `active`
- `deprecated`
- `sunset`

Rules:

- `distribution_status` describes how this hub should present or distribute the product
- upstream support policy remains owned by the source repository
- deprecated products should explain the replacement or migration path in `README.md` or `docs/`
- sunset products may keep historical release links, but should not look like active install targets
- do not silently delete a product folder if releases are still referenced elsewhere
- if release assets are removed, leave an explicit tombstone note describing the removal and owner decision

## 9. What Should Not Be Stored Here

Avoid putting these into the repository tree:

- large versioned binary files committed repeatedly into git
- raw CI artifacts that only exist for debugging
- internal audit bundles
- long-lived copies of documents already owned by the source repository
- per-team temporary packaging experiments

If a file is only needed by a build pipeline, it probably belongs in the product repository, not here.

## 10. Recommended Onboarding Flow For A New Product

1. Create `products/<product-slug>/`.
2. Copy the structure from `products/_template/`.
3. Fill in `README.md`, `README.ko.md`, and `product.yaml`.
4. Add install or uninstall helpers only if the product needs them.
5. Publish binaries as release assets using the product-scoped tag format.
6. Link the releases page from the product README.
