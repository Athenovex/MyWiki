---
id: kb-vertex-ai
type: product
status: canonical
aliases: []
domains: ["AI", "development"]
related: ["[[Gemini]]", "[[Google Cloud Storage]]"]
sources: ["[[동국대_교육자료1]]", "[[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]]"]
created: 2026-08-15
updated: 2026-08-15
---

# Vertex AI

> ML 개발의 모든 단계를 하나로 통합한 Google Cloud의 완전관리형 AI 플랫폼. 데이터 준비부터 모델 학습, 배포, 예측, 모니터링까지 머신러닝 워크플로우의 전체 라이프사이클을 지원한다.

## 구조

1. **데이터 소스**: Cloud Storage, BigQuery, Pub/Sub·Dataflow, Cloud SQL/Spanner, 온프레미스 데이터
2. **Vertex AI 통합 ML 플랫폼**: 데이터 준비(라벨링/Feature Store) → 모델 개발(AutoML/커스텀 학습) → 모델 관리(버전 관리/레지스트리/실험 추적) → 모델 배포(엔드포인트/배치 예측/자동 스케일링) → 모니터링&관리(성능 모니터링/드리프트 감지)
   - 공통 기반: IAM&보안, VPC Service Controls, 암호화, 로깅&감사, 규정 준수
3. **활용(예측&운영)**: 실시간 예측 서비스, 배치 예측, 비즈니스 인사이트, 앱/서비스 통합

## 주요 장점

완전관리형 서비스(인프라 관리 불필요), 개발 속도 향상, 비용 최적화(사용한 만큼 지불), 보안&거버넌스, 확장성, Google Cloud 생태계 연동(BigQuery·Dataflow·Looker).

## 관련 지식

- [[Gemini]] — Vertex AI를 통해 배포·관리할 수 있는 모델 중 하나
- [[Google Cloud Storage]] — Vertex AI의 데이터 소스로 사용되는 저장소

## 출처

- [[동국대_교육자료1]] p.5 "Vertex AI란?"
- [[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]] p.3 (동일 다이어그램)
