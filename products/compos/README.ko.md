# Compos CLI

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](README.ko.md)

Compos 워크스페이스용 명령줄 클라이언트입니다.

이 배포 항목은 upstream 소스 저장소에서 빌드한 `compos` CLI 릴리즈 바이너리를 내려받기 위한 진입점입니다.

## 링크

- 소스 저장소: https://github.com/Conalog/compos
- 릴리즈 페이지: https://github.com/Conalog/publish/releases

## 설치

최신 `compos/vX.Y.Z` 릴리즈에서 플랫폼에 맞는 asset을 내려받습니다:

- `compos_<version>_linux_amd64.tar.gz`
- `compos_<version>_linux_arm64.tar.gz`
- `compos_<version>_macos_amd64.tar.gz`
- `compos_<version>_macos_arm64.tar.gz`
- `compos_<version>_windows_amd64.tar.gz`

압축을 푼 뒤 다음 명령으로 확인합니다:

```sh
bin/compos version
```

## 삭제

압축을 푼 디렉터리를 제거하거나 PATH에 설치한 `compos` 바이너리를 삭제합니다.

## 참고

published version의 기준은 release asset입니다. 이 제품 항목에는 latest version 값을 중복해서 저장하지 않습니다.
