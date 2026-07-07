# repass-local-worker

[![English](https://img.shields.io/badge/lang-English-0A66C2)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-BDBDBD)](README.ko.md)

`repass-local-worker` is the local execution CLI used by the Conalog desktop agent for REPass certificate-based collection.

It receives a local execution request on stdin, runs the RPS collection on the user's machine, and uploads only the non-secret result payload to the gateway.

## Links

- Source repository: [Conalog/grant](https://github.com/Conalog/grant)
- Releases page: [Conalog/publish releases](https://github.com/Conalog/publish/releases)

## Install

Download the `repass-local-worker_<version>_linux_amd64.tar.gz` asset from a `repass-local-worker/vX.Y.Z` release, extract `repass-local-worker`, and place it next to `desktop-agent` or on `PATH`.

Supported platform:

- `linux/amd64`

## Uninstall

Remove the installed `repass-local-worker` binary from its install location.

## Notes

Release assets are published by the source repository workflow. This repository only stores distribution metadata and release assets.
