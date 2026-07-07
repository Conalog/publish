# REP 데스크톱 에이전트

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](README.ko.md)

REP 연동을 위한 데스크톱 루프백 에이전트입니다.

이 제품 항목은 upstream 소스 저장소에서 빌드한 REP 데스크톱 에이전트 바이너리를 내려받기 위한 진입점입니다.

## 링크

- 소스 저장소: https://github.com/Conalog/rep
- 릴리즈 페이지: https://github.com/Conalog/publish/releases
- 릴리즈 태그 패턴: `rep-agent/vX.Y.Z`

## Asset

플랫폼에 맞는 asset을 내려받습니다:

- `rep-agent_<version>_macos_arm64.tar.gz`
- `rep-agent_<version>_macos_amd64.tar.gz`
- `rep-agent_<version>_windows_amd64.zip`
- `rep-agent_<version>_windows_386.zip`

각 archive는 `rep-agent/` 디렉터리로 풀리며, macOS에서는 `rep-desktop-agent`, Windows에서는 `rep-desktop-agent.exe` 실행 파일을 포함합니다.

## 검증

같은 릴리즈의 `rep-agent_<version>_SHA256SUMS.txt`로 다운로드한 asset의 체크섬을 검증합니다.

## 서명 상태

릴리즈 asset은 현재 unsigned 상태이며 notarization도 적용되어 있지 않습니다. 최종 사용자 기기에 배포하기 전 조직의 디바이스 관리 정책을 따르세요.

## 참고

`windows_386`은 레거시 32-bit Windows 호환성을 위해 유지합니다.
