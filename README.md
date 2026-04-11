# Publish

Company-wide binary distribution repository.

This repository is a distribution hub for privately built products. It is not the canonical source of truth for engineering audit data, build history, or detailed QA records. Those remain in each product's source code repository.

## What Belongs Here

- product-level distribution metadata
- install and uninstall scripts
- lightweight end-user or operator documentation
- release landing pages or HTML entrypoints
- agent-facing rollout or usage guides
- links to release assets

## What Does Not Belong Here

- source code that should live in the product repository
- large binary histories committed directly into git
- detailed audit evidence, test reports, or signing pipelines
- team-specific private scratch files

## Structure

```text
products/
  <product-slug>/
    README.md
    product.yaml
    docs/
    install/
    uninstall/
    pages/
    agents/
```

- `README.md`: quick human-facing entrypoint for the product
- `product.yaml`: stable machine-readable metadata
- `docs/`: lightweight product and distribution docs
- `install/`: install helpers and wrapper scripts
- `uninstall/`: removal or cleanup helpers
- `pages/`: distribution HTML or static landing content
- `agents/`: guidance for agents or automation flows

## Release Model

- Treat each product as the primary release unit.
- Publish actual binaries mainly as release assets.
- Treat release tags and attached assets as the only source of truth for released versions.
- Keep this repository lightweight and easy to browse.

Detailed rules live in [docs/REPO_POLICY.md](/Users/cypark/Documents/work/publish/docs/REPO_POLICY.md).
