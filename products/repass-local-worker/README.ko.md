# repass-local-worker

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](README.ko.md)

`repass-local-worker`는 Conalog desktop agent가 REPass 공동인증서 기반 수집을 로컬에서 실행할 때 사용하는 CLI입니다.

이 CLI는 stdin으로 로컬 실행 요청을 받고, 사용자 기기에서 RPS 수집을 수행한 뒤, 비밀정보가 아닌 결과 payload만 gateway에 업로드합니다.

## 링크

- Source repository: [Conalog/grant](https://github.com/Conalog/grant)
- Releases page: [Conalog/publish releases](https://github.com/Conalog/publish/releases)

## 설치

`repass-local-worker/vX.Y.Z` 릴리즈에서 `repass-local-worker_<version>_linux_amd64.tar.gz` asset을 내려받고, 압축을 푼 뒤 `repass-local-worker` 파일을 `desktop-agent` 옆이나 `PATH`에 둡니다.

지원 플랫폼:

- `linux/amd64`

## 삭제

설치 위치에서 `repass-local-worker` 실행 파일을 삭제합니다.

## 참고

릴리즈 asset은 source repository workflow가 배포합니다. 이 저장소는 배포 메타데이터와 release asset만 보관합니다.
