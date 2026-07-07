# REP Distribution Overview

[![English](https://img.shields.io/badge/lang-English-0A66C2)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-BDBDBD)](README.ko.md)

Desktop loopback agent and browser-facing web SDK for REP integrations.

REP distribution is split into component-scoped release products. Use the component entries below for new downloads.

## Links

- Source repository: https://github.com/Conalog/rep
- Releases page: https://github.com/Conalog/publish/releases
- Desktop agent product: ../rep-agent/
- Web SDK product: ../rep-web-sdk/

## Desktop Agent

Download desktop agent binaries from `rep-agent/vX.Y.Z`:

- `rep-agent_<version>_macos_arm64.tar.gz`
- `rep-agent_<version>_macos_amd64.tar.gz`
- `rep-agent_<version>_windows_amd64.zip`
- `rep-agent_<version>_windows_386.zip`

Each archive extracts to `rep-agent/` and contains the executable as `rep-desktop-agent` on macOS or `rep-desktop-agent.exe` on Windows.

## Web SDK

Download platform-independent web SDK assets from `rep-web-sdk/vX.Y.Z`:

- `rep-web-sdk_<version>_npm.tgz`: npm-installable package tarball
- `rep-web-sdk_<version>_browser.tar.gz`: browser distribution bundle

## Verification

Use the component checksum file from the same release:

- `rep-agent_<version>_SHA256SUMS.txt`
- `rep-web-sdk_<version>_SHA256SUMS.txt`

## Signing Status

Release assets are currently unsigned and not notarized. Follow the organization's device-management policy before deploying to end-user machines.

## Notes

Release assets are the source of truth for published versions. The older combined `rep/vX.Y.Z` releases are retained as historical releases; new releases use `rep-agent/vX.Y.Z` and `rep-web-sdk/vX.Y.Z`.
