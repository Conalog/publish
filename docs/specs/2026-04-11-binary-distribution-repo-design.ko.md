# Binary Distribution Repo Design

[![English](https://img.shields.io/badge/lang-English-BDBDBD)](2026-04-11-binary-distribution-repo-design.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-0A66C2)](2026-04-11-binary-distribution-repo-design.ko.md)

## 목표

프라이빗하게 빌드된 바이너리를 회사 차원에서 배포하기 위한 간단한 구조를 정의하되, 이 저장소가 엔지니어링 감사 시스템의 원본이 되지 않도록 합니다.

## 결정

이 저장소는 제품 중심의 배포 허브입니다.

- 제품이 기본 조직 단위입니다.
- 빌드 이력, 변경 이력, QA 증적, provenance, 호환성 보장은 각 제품의 소스 코드 저장소가 원본으로 유지합니다.
- 이 저장소는 다음과 같은 배포 관점 자산을 담당합니다.
  - 릴리즈 메타데이터와 링크
  - 설치 및 삭제 스크립트
  - 가벼운 제품 문서
  - 랜딩 페이지 또는 HTML 진입점
  - 설치나 롤아웃 작업에 필요한 에이전트용 가이드

## 이유

이 구조는 저장소를 탐색하기 쉽고 운영 비용도 낮게 유지합니다.

- 사람들이 바이너리를 찾는 방식과 제품 중심 구조가 잘 맞습니다.
- 바이너리를 release asset으로 두면 git 히스토리가 비대해지는 것을 막을 수 있습니다.
- 팀 중심 구조는 단기적으로는 소유권이 편해 보여도 회사 전체 기준 탐색성은 떨어집니다.
- 규정 준수나 감사 수준의 책임은 실제로 소프트웨어를 빌드하는 제품 저장소에 남겨두는 것이 맞습니다.

## 저장소 형태

저장소는 `products/` 아래에 제품별 안정적인 폴더를 노출합니다.

각 제품은 다음을 가질 수 있습니다.

- `README.md`
- `README.ko.md`
- `product.yaml`
- `docs/`
- `install/`
- `uninstall/`
- `pages/`
- `agents/`

## 릴리즈 규칙

- 각 제품은 하나의 안정적인 product slug를 사용합니다.
- 제품 범위 버전 태그는 `product-slug/vX.Y.Z` 형식을 사용합니다.
- 바이너리는 일반 git blob이 아니라 주로 release asset으로 배포합니다.
- prerelease 채널은 `alpha`, `beta`, `rc` 정도로 제한합니다.
- stable 릴리즈는 사람이 쉽게 찾고 설치할 수 있어야 합니다.

## 비목표

- 이 저장소에서 전체 감사 이력을 관리하는 것
- 이 저장소에서 상세 QA 또는 호환성 리포트를 관리하는 것
- 대용량 바이너리 히스토리를 git에 직접 누적하는 것
