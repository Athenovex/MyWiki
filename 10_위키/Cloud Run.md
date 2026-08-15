---
id: kb-cloud-run
type: product
status: canonical
aliases: []
domains: ["development"]
related: ["[[Streamlit]]", "[[Google Cloud Storage]]"]
sources: ["[[동국대_교육자료1]]", "[[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]]"]
created: 2026-08-15
updated: 2026-08-15
---

# Cloud Run

> Google Cloud의 완전관리형(서버리스) 컨테이너 플랫폼. 코드만 있으면 인프라 걱정 없이 몇 초 만에 전 세계에 배포할 수 있다.

## Cloud Run이란

인프라 관리 없이 컨테이너 애플리케이션을 자동으로 빌드·배포·확장한다.

## 주요 특징

- 서버리스: 서버 관리·패치·용량 계획 불필요
- 자동 확장: 트래픽에 따라 자동 확장/축소 (0 → N)
- 빠른 배포: 컨테이너 이미지 푸시 후 몇 초 만에 배포 완료
- 전 세계 제공: 엣지에서 빠르고 안전하게 서비스 제공

## 배포 흐름

코드 개발 → 컨테이너 이미지 빌드(Dockerfile) → 이미지 저장(Artifact Registry) → Cloud Run 배포(이미지 선택 후 배포 클릭) → 자동 확장&서빙(트래픽에 따라)

배포 예시:
```
docker build -t gcr.io/PROJECT_ID/my-app .
docker push gcr.io/PROJECT_ID/my-app
gcloud run deploy my-app \
  --image gcr.io/PROJECT_ID/my-app \
  --region asia-northeast3 \
  --platform managed \
  --allow-unauthenticated
```

## 장점

몇 초 만에 배포 완료, 트래픽 급증에도 자동 대응, 비용 절감(요청 없으면 0으로 축소), 운영 부담 최소화, 전 세계 빠른 응답.

## 주요 기능

동시 요청 처리, 리비전 관리(트래픽 분할/롤백), 환경변수·비밀 관리(Secret Manager 연동), VPC 연결, Cloud Monitoring, IAM 통합.

## 관련 지식

- [[Streamlit]] — Cloud Run에 배포할 수 있는 대표적 웹 앱 프레임워크
- [[Google Cloud Storage]] — 배포된 서비스가 연동하는 데이터/외부 서비스

## 출처

- [[동국대_교육자료1]] p.20 "Cloud Run 초고속 배포"
- [[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]] p.14 (동일 다이어그램)
