---
id: kb-google-cloud-storage
type: product
status: canonical
aliases: ["GCS"]
domains: ["development"]
related: ["[[Vertex AI]]", "[[Cloud Run]]"]
sources: ["[[동국대_교육자료1]]", "[[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]]"]
created: 2026-08-15
updated: 2026-08-15
---

# Google Cloud Storage (GCS)

> Google Cloud에서 제공하는 확장성·내구성·가용성이 높은 객체 스토리지 서비스.

## 주요 특징

- 높은 내구성과 가용성 (99.999999999%, 11 9's)
- 무제한 확장성 (페타바이트 단위)
- 보안 및 접근 제어 (IAM, 암호화, 버킷 정책)
- 비용 효율성 (사용한 만큼 지불, 스토리지 클래스 선택)

## 구성 요소

- **버킷(Bucket)**: 데이터를 담는 최상위 컨테이너 (전역적으로 고유한 이름, 리전/멀티리전 위치 선택)
- **객체(Object)**: 버킷에 저장되는 개별 데이터 (파일+메타데이터, 고유한 이름(키)으로 식별)

## 스토리지 클래스

| 클래스 | 용도 |
|---|---|
| Standard | 자주 액세스하는 데이터 (높은 가용성, 짧은 지연시간) |
| Nearline | 월 1회 정도 액세스 |
| Coldline | 분기별 1회 정도 액세스 |
| Archive | 연 1회 미만 액세스 (가장 낮은 비용) |

## 활용 사례

백업 및 재해 복구, 미디어 저장 및 스트리밍, 데이터 레이크 및 분석, 정적 웹사이트 호스팅, 장기 보관. Compute Engine·BigQuery·Cloud Functions·Dataflow·Cloud Dataproc 등과 연동된다.

## 관련 지식

- [[Vertex AI]] — GCS를 데이터 소스로 활용하는 ML 플랫폼
- [[Cloud Run]] — 배포된 애플리케이션이 GCS와 연동해 데이터를 저장·조회할 수 있음

## 출처

- [[동국대_교육자료1]] p.6 "Google Cloud Storage란?"
- [[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]] p.3 (동일 다이어그램)
