# Publish

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](README.ko.md)

사내 공용 바이너리 배포 저장소입니다.

이 저장소는 프라이빗하게 빌드된 제품을 배포하기 위한 허브이며, 엔지니어링 감사 데이터나 빌드 이력, 상세 QA 기록의 원본 저장소는 아닙니다. 이런 정보는 각 제품의 소스 코드 저장소가 계속 책임집니다.

저장소 정책 및 공식 문서의 기본 언어는 영어입니다. 사람이 읽는 가이드는 영어와 한국어 문서를 함께 제공해야 합니다.

## 이 저장소에 들어와야 하는 것

- 제품 단위 배포 메타데이터
- 설치 및 삭제 스크립트
- 가벼운 사용자용 또는 운영자용 문서
- 릴리즈 랜딩 페이지 또는 HTML 진입점
- 에이전트용 롤아웃/사용 가이드
- release asset 링크

## 이 저장소에 넣지 말아야 하는 것

- 제품 저장소에 있어야 하는 소스 코드
- git에 직접 누적되는 대용량 바이너리 히스토리
- 상세 감사 증적, 테스트 리포트, 서명 파이프라인
- 팀별 임시 작업 파일

## 구조

```text
products/
  <product-slug>/
    README.md
    README.ko.md
    product.yaml
    docs/
    install/
    uninstall/
    pages/
    agents/
```

- `README.md`: 제품의 기본 영문 진입 문서
- `README.ko.md`: 제품의 한국어 진입 문서
- `product.yaml`: 안정적인 기계 판독용 메타데이터
- `docs/`: 가벼운 제품/배포 문서
- `install/`: 설치 보조 스크립트
- `uninstall/`: 제거 또는 정리 스크립트
- `pages/`: 배포용 HTML 또는 정적 랜딩 콘텐츠
- `agents/`: 에이전트/자동화용 가이드

## 릴리즈 모델

- 각 제품을 기본 릴리즈 단위로 취급합니다.
- 실제 바이너리는 주로 release asset으로 배포합니다.
- released version의 기준은 release tag와 그에 연결된 asset입니다.
- 이 저장소 자체는 가볍고 탐색하기 쉽게 유지합니다.

상세 규칙은 [docs/REPO_POLICY.ko.md](docs/REPO_POLICY.ko.md)에 있습니다.
