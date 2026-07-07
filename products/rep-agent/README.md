# REP Desktop Agent

[![English](https://img.shields.io/badge/lang-English-0A66C2)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-BDBDBD)](README.ko.md)

Desktop loopback agent for REP integrations.

Use this product entry to download released REP desktop agent binaries built from the upstream source repository.

## Links

- Source repository: https://github.com/Conalog/rep
- Releases page: https://github.com/Conalog/publish/releases
- Release tag pattern: `rep-agent/vX.Y.Z`

## Assets

Download the asset for your platform:

- `rep-agent_<version>_macos_arm64.tar.gz`
- `rep-agent_<version>_macos_amd64.tar.gz`
- `rep-agent_<version>_windows_amd64.zip`
- `rep-agent_<version>_windows_386.zip`

Each archive extracts to `rep-agent/` and contains the executable as `rep-desktop-agent` on macOS or `rep-desktop-agent.exe` on Windows.

## Verification

Use `rep-agent_<version>_SHA256SUMS.txt` from the same release to verify downloaded assets.

## Signing Status

Release assets are currently unsigned and not notarized. Follow the organization's device-management policy before deploying to end-user machines.

## Notes

`windows_386` is retained for legacy 32-bit Windows compatibility.
