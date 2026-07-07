# REP 배포 개요

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](README.ko.md)

REP 연동을 위한 데스크톱 루프백 에이전트와 브라우저용 Web SDK입니다.

REP 배포는 컴포넌트 단위 release product로 분리됩니다. 신규 다운로드는 아래 컴포넌트 항목을 기준으로 사용하세요.

## 링크

- 소스 저장소: https://github.com/Conalog/rep
- 릴리즈 페이지: https://github.com/Conalog/publish/releases
- 데스크톱 에이전트 제품: ../rep-agent/
- Web SDK 제품: ../rep-web-sdk/

## 데스크톱 에이전트

데스크톱 에이전트 바이너리는 `rep-agent/vX.Y.Z`에서 내려받습니다:

- `rep-agent_<version>_macos_arm64.tar.gz`
- `rep-agent_<version>_macos_amd64.tar.gz`
- `rep-agent_<version>_windows_amd64.zip`
- `rep-agent_<version>_windows_386.zip`

각 archive는 `rep-agent/` 디렉터리로 풀리며, macOS에서는 `rep-desktop-agent`, Windows에서는 `rep-desktop-agent.exe` 실행 파일을 포함합니다.

## Web SDK

플랫폼에 관계없이 사용할 수 있는 Web SDK asset은 `rep-web-sdk/vX.Y.Z`에서 내려받습니다:

- `rep-web-sdk_<version>_npm.tgz`: npm 설치용 package tarball
- `rep-web-sdk_<version>_browser.tar.gz`: 브라우저 배포용 bundle

## 검증

같은 릴리즈의 컴포넌트별 checksum 파일로 다운로드한 asset을 검증합니다:

- `rep-agent_<version>_SHA256SUMS.txt`
- `rep-web-sdk_<version>_SHA256SUMS.txt`

## 서명 상태

릴리즈 asset은 현재 unsigned 상태이며 notarization도 적용되어 있지 않습니다. 최종 사용자 기기에 배포하기 전 조직의 디바이스 관리 정책을 따르세요.

## 참고

published version의 기준은 release asset입니다. 기존 통합 `rep/vX.Y.Z` 릴리즈는 historical release로 유지하고, 신규 릴리즈는 `rep-agent/vX.Y.Z`와 `rep-web-sdk/vX.Y.Z`를 사용합니다.
