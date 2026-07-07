# REP Desktop Agent and Web SDK

[![English](https://img.shields.io/badge/lang-English-0A66C2)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-BDBDBD)](README.ko.md)

Desktop loopback agent and browser-facing web SDK for REP integrations.

Use this distribution entry to download released REP desktop agent binaries and web SDK packages built from the upstream source repository.

## Links

- Source repository: https://github.com/Conalog/rep
- Releases page: https://github.com/Conalog/publish/releases

## Desktop Agent

Download the latest `rep/vX.Y.Z` release asset for your platform:

- `rep-agent_<version>_macos_arm64.tar.gz`
- `rep-agent_<version>_macos_amd64.tar.gz`
- `rep-agent_<version>_windows_amd64.zip`
- `rep-agent_<version>_windows_386.zip`

Each archive extracts to `rep-agent/` and contains the executable as `rep-desktop-agent` on macOS or `rep-desktop-agent.exe` on Windows.

## Web SDK

Download one of the platform-independent web SDK assets:

- `rep-web-sdk_<version>_npm.tgz`: npm-installable package tarball
- `rep-web-sdk_<version>_browser.tar.gz`: browser distribution bundle

## Verification

Use `rep_<version>_SHA256SUMS.txt` from the same release to verify downloaded assets.

## Signing Status

Release assets are currently unsigned and not notarized. Follow the organization's device-management policy before deploying to end-user machines.

## Notes

Release assets are the source of truth for published versions. This product entry intentionally does not duplicate a latest version number.
