# Repository Policy

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](REPO_POLICY.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](REPO_POLICY.ko.md)

## 1. 저장소 역할

이 저장소는 프라이빗하게 빌드된 바이너리를 회사 차원에서 배포하기 위한 허브입니다.

이 저장소의 목적은 릴리즈된 소프트웨어를 쉽게 찾고, 이해하고, 설치할 수 있게 만드는 것입니다. 제품의 소스 코드 저장소를 대체하지 않습니다.

소스 코드 저장소가 계속 책임지는 항목:

- 빌드 이력
- 상세 변경 이력
- QA 증적 및 테스트 로그
- 서명, provenance, 공급망 관련 정보
- 호환성 보장과 지원 정책

이 저장소가 책임지는 항목:

- 사람이 제품을 쉽게 찾을 수 있는 진입점
- 배포 메타데이터
- 설치 및 삭제 보조 스크립트
- 릴리즈 바이너리에 대한 가벼운 문서
- 릴리즈 페이지와 링크
- 에이전트용 운영 가이드
- 이 허브 안에서의 배포 상태

## 2. 최상위 구조

이 저장소는 팀 기준이 아니라 제품 기준으로 구성합니다. 플랫폼 기준으로도 나누지 않습니다.

사용 형식:

```text
products/<product-slug>/
```

팀 구조는 바뀔 수 있지만 제품 식별자는 오래 유지되어야 하므로, 팀명을 최상위 계층으로 사용하지 않습니다.

## 3. Product Slug 규칙

각 제품은 하나의 안정적인 slug를 가져야 합니다.

규칙:

- 소문자, 숫자, 하이픈만 사용
- 짧고 오래 유지할 수 있는 이름 사용
- 제품 자체가 팀 전용이 아닌 이상 팀명을 slug에 넣지 않음
- 별도 마이그레이션 결정 없이 slug를 바꾸지 않음

예시:

- `agent-console`
- `docs-sync`
- `media-uploader`

## 4. 제품 폴더 규칙

각 제품 폴더는 다음 구조를 따릅니다.

```text
products/<product-slug>/
  README.md
  README.ko.md
  product.yaml
  docs/
  install/
  uninstall/
  pages/
  agents/
```

### 필수 파일

- `README.md`
- `README.ko.md`
- `product.yaml`

### 선택 디렉터리

- `docs/`
- `install/`
- `uninstall/`
- `pages/`
- `agents/`

제품에 실제 역할이 있을 때만 디렉터리를 유지합니다. 템플릿에는 의도한 구조를 보이기 위해 모두 포함하지만, 실제 제품은 쓰지 않는 디렉터리를 제거해도 됩니다.

### 콘텐츠 경계

- `README.md`
  - 제품이 무엇인지 설명
  - 소스 저장소 링크 제공
  - 제품 릴리즈 페이지 링크 제공
  - 일반적인 설치 경로 설명
- `README.ko.md`
  - `README.md`의 한국어 짝 문서 제공
  - 영문 진입 문서와 내용을 맞춰 유지
- `product.yaml`
  - 사람과 도구가 쓰는 안정적인 메타데이터 저장
  - release asset에 이미 있는 현재 버전 숫자를 중복 저장하지 않음
- `docs/`
  - 사용 노트, 마이그레이션 노트, 운영자용 안내
- `install/`
  - 릴리즈된 바이너리 설치를 돕는 스크립트
- `uninstall/`
  - 설치 파일 제거 또는 되돌리기 스크립트
- `pages/`
  - 배포 랜딩 페이지용 정적 HTML 또는 자산
- `agents/`
  - 설치, 업그레이드, 검증, 롤백을 수행하는 에이전트용 안내

## 5. 문서 언어 규칙

정식 저장소 문서의 기본 언어는 영어입니다.

규칙:

- 기본 파일은 기존 `.md` 이름을 유지한 영문 문서로 둡니다
- 한국어 문서는 같은 베이스 이름에 `.ko.md`를 붙여 추가합니다
- 두 문서 모두 상단에 언어 전환 배지 또는 같은 수준의 링크를 둡니다
- 영문과 국문 문서가 어긋나면 두 문서를 다시 맞출 때까지 영문 문서를 기준으로 봅니다
- 사람이 읽는 가이드는 영어와 한국어를 모두 제공합니다

예시:

- `README.md` 와 `README.ko.md`
- `setup.md` 와 `setup.ko.md`
- `migration-guide.md` 와 `migration-guide.ko.md`

최소한 다음 문서는 영문과 국문을 모두 제공합니다.

- 저장소 또는 제품 진입용 README
- 사람이 읽는 설치/삭제 가이드
- 롤아웃, 운영, 마이그레이션 가이드
- `docs/` 또는 `agents/` 아래의 기타 사람이 읽는 가이드

## 6. 필수 제품 메타데이터

각 제품은 최소한 다음 정보를 가져야 합니다.

- 안정적인 product slug
- 제품 표시 이름
- 유지보수 담당자 또는 팀
- upstream 소스 저장소
- releases page URL
- 기본 릴리즈 채널
- 이 저장소 안에서의 distribution status

이 정보는 `product.yaml`에 두어 사람과 도구가 빠르게 찾을 수 있게 합니다.

`distribution_status`는 이 배포 허브에서 제품을 어떻게 노출하고 배포할지를 나타내는 값입니다. upstream 제품의 지원 정책을 대체하지 않습니다. upstream 지원 정책과 이 허브의 distribution status가 다르면 upstream 정책이 우선하며, 제품 README에 그 차이를 설명해야 합니다.

## 7. 릴리즈 규칙

실제 바이너리 payload는 git에 직접 커밋하기보다 주로 release asset으로 배포합니다.

릴리즈 버전의 기준은 release tag와 그에 연결된 asset입니다. `product.yaml`에 `latest_version` 같은 현재 버전 필드를 두지 않습니다.

### 버전 규칙

- 특별한 이유가 없으면 semantic version을 사용
- stable 릴리즈는 `vX.Y.Z` 사용
- prerelease는 `vX.Y.Z-beta.1`, `vX.Y.Z-rc.1` 같은 형식 사용 가능

### 태그

제품 범위 태그를 사용합니다.

```text
<product-slug>/vX.Y.Z
```

예시:

- `agent-console/v1.4.0`
- `docs-sync/v0.9.2-beta.1`

여러 제품이 한 저장소를 공유해도 태그 충돌을 피할 수 있습니다.

### 릴리즈 제목

다음 형식을 사용합니다.

```text
<product-slug> X.Y.Z
```

### Asset Naming

다음 형식으로 예측 가능한 파일명을 사용합니다.

```text
<product-slug>_<version>_<os>_<arch>.<ext>
```

예시:

- `agent-console_1.4.0_macos_arm64.tar.gz`
- `agent-console_1.4.0_linux_amd64.tar.gz`
- `docs-sync_0.9.2-beta.1_windows_amd64.zip`

### Canonical Token

제품 README에 별도 예외를 문서화하지 않는 한 다음 토큰만 사용합니다.

- `os`: `macos`, `linux`, `windows`
- `arch`: `arm64`, `amd64`
- `ext`: `tar.gz`, `zip`, `dmg`, `pkg`, `msi`, `exe`

공개된 asset 이름에서 `darwin`/`macos`, `x86_64`/`amd64` 같은 동의어를 섞어 쓰지 않습니다.

### 채널

실제 운영 의미가 있을 때만 채널을 사용합니다.

- `stable`: 일반 사용자 기본 대상
- `beta`: 제한된 내부 테스트용 미리보기 빌드
- `rc`: stable 승격 전 release candidate

명확한 롤아웃 필요가 없으면 채널을 늘리지 않습니다.

### 릴리즈 노트 최소 필드

각 릴리즈에는 최소한 다음이 들어가야 합니다.

- 제품 이름과 버전
- 소스 저장소 링크
- 소스 커밋, 태그, 또는 빌드 기준
- 빌드 일자 또는 릴리즈 일자
- 지원 플랫폼
- 필요 시 서명 상태
- 설치 또는 업그레이드 방법
- 필요 시 롤백 또는 삭제 방법

### Release Asset 요구사항

배포된 각 바이너리는 다음을 모두 만족해야 합니다.

- asset 이름이 저장소 naming 규칙을 따를 것
- 플랫폼과 아키텍처가 모호하지 않을 것
- 릴리즈 노트가 설치 가이드를 가리킬 것
- 소스 기준점을 upstream 제품 저장소까지 추적할 수 있을 것

## 8. Deprecated, 삭제, Distribution Status

각 제품은 `product.yaml`에 간단한 `distribution_status`를 가져야 합니다.

권장 값:

- `active`
- `deprecated`
- `sunset`

규칙:

- `distribution_status`는 이 허브에서 제품을 어떻게 노출하거나 배포할지 설명합니다
- upstream 지원 정책은 계속 소스 저장소가 책임집니다
- deprecated 제품은 `README.md`, `README.ko.md`, 또는 `docs/`에 대체 경로나 마이그레이션 경로를 설명해야 합니다
- sunset 제품은 과거 릴리즈 링크를 유지할 수 있지만 active처럼 보이면 안 됩니다
- 다른 곳에서 아직 릴리즈를 참조 중이면 제품 폴더를 조용히 삭제하지 않습니다
- release asset을 제거할 경우 제거 이유와 결정 주체를 설명하는 tombstone note를 남깁니다

## 9. 이 저장소에 넣지 말아야 하는 것

다음은 저장소 트리에 두지 않습니다.

- 반복적으로 누적되는 대용량 버전 바이너리
- 디버깅용 raw CI artifact
- 내부 감사 번들
- 이미 소스 저장소가 원본인 장기 보관 문서
- 팀별 임시 패키징 실험 결과물

파일이 빌드 파이프라인에서만 필요하다면, 대체로 이 저장소가 아니라 제품 저장소에 있어야 합니다.

## 10. 새 제품 온보딩 권장 절차

1. `products/<product-slug>/`를 생성합니다.
2. `products/_template/` 구조를 복사합니다.
3. `README.md`, `README.ko.md`, `product.yaml`을 채웁니다.
4. 필요한 경우에만 install/uninstall 보조 파일을 추가합니다.
5. 제품 범위 태그 형식에 맞춰 바이너리를 release asset으로 배포합니다.
6. 제품 README에서 releases page를 링크합니다.
