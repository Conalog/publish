# REP SDK

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](README.ko.md)

REP 연동을 위한 브라우저용 SDK입니다.

이 제품 항목은 upstream 소스 저장소에서 빌드한 REP SDK 패키지를 내려받기 위한 진입점입니다.

## 링크

- 소스 저장소: https://github.com/Conalog/rep
- 릴리즈 페이지: https://github.com/Conalog/publish/releases
- npm package: `@conalog/rep-sdk`
- 릴리즈 태그 패턴: `rep-sdk/vX.Y.Z`

## Asset

플랫폼에 관계없이 사용할 수 있는 SDK asset 중 하나를 내려받습니다:

- `rep-sdk_<version>_npm.tgz`: npm 설치용 package tarball
- `rep-sdk_<version>_browser.tar.gz`: 브라우저 배포용 bundle

## 검증

같은 릴리즈의 `rep-sdk_<version>_SHA256SUMS.txt`로 다운로드한 asset의 체크섬을 검증합니다.

## 참고

SDK asset은 플랫폼에 독립적이므로 OS 또는 architecture token을 사용하지 않습니다.
