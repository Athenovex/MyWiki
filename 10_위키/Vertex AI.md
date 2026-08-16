---
id: kb-vertex-ai
type: product
status: canonical
aliases: []
domains: ["AI", "development"]
related: ["[[Gemini]]", "[[Google Cloud Storage]]"]
sources: ["[[동국대_교육자료1]]", "[[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]]"]
created: 2026-08-15
updated: 2026-08-16
---

# Vertex AI

> ML 개발의 모든 단계를 하나로 통합한 Google Cloud의 완전관리형 AI 플랫폼. 데이터 준비부터 모델 학습, 배포, 예측, 모니터링까지 머신러닝 워크플로우의 전체 라이프사이클을 지원한다.

## 개요

Vertex AI는 Google Cloud가 제공하는 완전관리형 AI/ML 플랫폼으로, 데이터 준비부터 모델 학습·배포·예측·모니터링까지 머신러닝 워크플로우의 전체 라이프사이클을 하나의 콘솔·API 아래로 통합한다. [[Gemini]] 같은 생성형 AI 모델도 Vertex AI를 통해 API 형태로 호출하거나, 자체 커스텀 모델을 올려 함께 관리할 수 있다. "완전관리형"이라는 말은 서버 프로비저닝·패치·스케일링 같은 인프라 작업을 Google이 대신 처리한다는 뜻으로, 팀이 인프라가 아니라 모델·데이터 자체에 집중할 수 있게 해준다.

## 구조

[[동국대_교육자료1]] p.5 인포그래픽 "Google Cloud — Vertex AI란? — ML 개발의 모든 단계를 하나로 통합한 Google Cloud의 완전관리형 AI 플랫폼"의 3단 구조를 그대로 옮기면 다음과 같다.

1. **데이터 소스**:
   - Cloud Storage (파일, 이미지, 동영상 등)
   - BigQuery (구조화 데이터)
   - Pub/Sub, Dataflow (실시간 스트리밍 데이터)
   - Cloud SQL, Spanner 등 (데이터베이스)
   - 온프레미스 데이터 (Cloud VPN / Interconnect)
2. **Vertex AI – 통합 ML 플랫폼**: 5개 열로 구성된 파이프라인이 하나의 플랫폼 안에 있다.
   - **데이터 준비**: 데이터 라벨링(AutoML Data Labeling), 데이터셋 관리(Feature Store)
   - **모델 개발**: AutoML(자동 모델 생성), 커스텀 학습(TensorFlow, XGBoost 등), 분산 학습 지원
   - **모델 관리**: 모델 버전 관리, 모델 레지스트리, 실험 추적(Experiments)
   - **모델 배포**: 엔드포인트 배포(온라인 예측), 배치 예측, 스케일 자동 조정
   - **모니터링 & 관리**: 성능 모니터링, 데이터 드리프트 감지, 모델 성능 검증
   - 이 5개 열 전체를 감싸는 **공통 기반**: IAM & 보안, VPC Service Controls, 암호화, 로깅 & 감사, 규정 준수
3. **활용(예측 & 운영)**:
   - 실시간 예측 서비스 (웹/모바일 앱, API)
   - 배치 예측 결과 (보고서, 대시보드)
   - 비즈니스 인사이트 (의사결정 지원)
   - 앱 및 서비스 통합 (Workflow, Chatbot 등)

슬라이드 하단의 **활용 예시**: 고객 이탈 예측, 수요 예측, 이미지/문서 분석, 챗봇/상담 자동화, 이상 탐지, 추천 시스템, "...and more!"

> 참고(일반 배경지식, 출처 자료에 없음): AutoML은 코드를 거의 작성하지 않고 데이터만 넣으면 적절한 모델 구조·하이퍼파라미터를 자동으로 탐색해주는 방식이고, 커스텀 학습은 TensorFlow/PyTorch 등으로 직접 학습 코드를 작성해 Vertex AI 인프라 위에서 실행하는 방식이다. 빠른 검증에는 AutoML, 세밀한 튜닝이 필요하면 커스텀 학습을 선택하는 식으로 갈린다.

아래는 이 플랫폼을 코드 수준에서 보여주기 위해 편집 과정에서 작성한 예시로, 원본 자료의 실제 코드는 아니다.

```python
# Vertex AI SDK로 배포된 모델에 예측 요청 — 편집자 작성
from google.cloud import aiplatform

aiplatform.init(project="my-project-id", location="asia-northeast3")

endpoint = aiplatform.Endpoint("projects/.../locations/.../endpoints/ENDPOINT_ID")
response = endpoint.predict(instances=[{"feature_1": 0.5, "feature_2": 1.2}])
print(response.predictions)
```

## 주요 장점

[[동국대_교육자료1]] p.5 슬라이드 하단 "Vertex AI의 주요 장점" 6가지를 원문 그대로 옮긴다.

- **완전관리형 서비스**: "인프라 관리 없이 ML에 집중"
- **개발 속도 향상**: "AutoML, 도구 통합으로 빠른 모델 개발"
- **비용 최적화**: "필요한 리소스만 사용, 자동 스케일링"
- **보안 & 거버넌스**: "기업 수준의 보안, 컴플라이언스 지원"
- **확장성**: "대규모 데이터와 트래픽도 안정적 처리"
- **Google Cloud 생태계 연동**: "BigQuery, Dataflow, Looker 등과 자연스럽게 통합"

## 비교: Vertex AI vs 자체 구축 ML 인프라 (참고)

> 출처 자료에 없는 일반적 비교로, 이해를 돕기 위해 편집 과정에서 추가했다.

| 항목 | Vertex AI(관리형) | 자체 구축(온프레미스/직접 K8s 등) |
|---|---|---|
| 초기 구축 속도 | 빠름 (콘솔·API로 바로 시작) | 느림 (인프라·MLOps 파이프라인 직접 구축) |
| 운영 부담 | Google이 서버·확장 관리 | 팀이 직접 서버·스케일링·장애 대응 |
| 비용 구조 | 사용량 기반, 소규모에 유리 | 초기 투자 후 대량 처리 시 단가 유리할 수 있음 |
| 커스터마이징 | 플랫폼 제약 내에서 가능 | 제약 없이 완전 자유 |

인프라 인력이 부족한 스타트업·소규모 팀에는 Vertex AI 같은 관리형 플랫폼이 유리하고, 이미 대규모 자체 인프라·전담 MLOps 팀이 있는 조직은 비용·커스터마이징 이유로 자체 구축을 택하기도 한다.

## 관련 지식

- [[Gemini]] — Vertex AI를 통해 배포·관리할 수 있는 모델 중 하나
- [[Google Cloud Storage]] — Vertex AI의 데이터 소스로 사용되는 저장소

## 출처

- [[동국대_교육자료1]] p.5 "Vertex AI란?" — poppler 시각 렌더링으로 인포그래픽 전체(데이터 소스/통합 ML 플랫폼/활용, 주요 장점, 활용 예시)를 확인, 원문 인용
- [[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]] p.2 (동일 다이어그램)

> 처리 메모: 이전 판에서 캠퍼스타운 자료가 "p.3"으로 인용되어 있었으나, 실제로 이 문서의 Vertex AI 다이어그램은 p.2에 있다(p.3은 Google Cloud Storage 다이어그램). 시각 확인 후 p.2로 정정했다.
