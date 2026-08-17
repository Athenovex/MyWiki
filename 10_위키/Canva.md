---
id: kb-canva
type: tool
status: canonical
aliases: []
domains: ["AI", "content", "productivity"]
related: ["[[Claude]]", "[[MCP]]", "[[AI 카피라이팅]]", "[[SNS 콘텐츠 마케팅]]"]
sources: ["[[Claude x Canva 마스터클래스 (2026)]]"]
created: 2026-08-17
updated: 2026-08-17
---

# Canva

> 디자인 제작 플랫폼. [[Claude]]의 Canva 커넥터를 연결하면 채팅창에서 "이런 거 만들어줘" 한 줄로 Claude가 사용자의 Canva 계정에 직접 들어가 디자인을 만들고 수정·내보내기까지 수행한다.

## 개요

기존에는 Claude(또는 ChatGPT)에서 카피를 쓰고 Canva로 이동해 템플릿을 찾고 텍스트·폰트·색·사이즈를 손으로 맞추는 데 콘텐츠 하나당 최소 30분이 걸렸다. Canva 커넥터는 이 과정을 하나의 Claude 대화창 안으로 합친다 — 기획·디자인·수정·다운로드·SNS 업로드까지 채팅으로 끝난다. Canva 무료 계정으로도 기본 사용이 가능하고, 사이즈 조정 등은 Pro, 브랜드 키트·템플릿 자동 채우기는 Enterprise가 필요하다.

## 연결 방법 (3번 클릭)

1. claude.ai 또는 Claude 데스크톱 앱 → 프로필 아이콘 → Settings → Connectors
2. "Browse Connectors" 옆 + 버튼 → Canva 검색 → Connect → Canva 로그인 및 권한 승인 (개인/업무 계정 중 브랜드 키트가 있는 쪽으로 연결)
3. 아무 대화창에서 "Use Canva to..." + 원하는 내용을 입력하면 자동으로 작동

## 가능한 작업

| 카테고리 | 예시 |
|---|---|
| 소셜 디자인 | 인스타·페북·X·핀터레스트·유튜브 포스트·스토리 |
| 프레젠테이션 | 슬라이드 구조·덱 자동 생성 |
| 문서 | 메모, 제안서, 리포트, 뉴스레터, 사업계획서 |
| 브랜드 자산 | 로고, 명함, 전단지, 포스터, 초청장 |
| 편집 | 텍스트·이미지·색상·포맷 수정, 문단 내 특정 단어만 수정, 번역 |
| 내보내기 | PNG, JPG, PDF, PPTX, GIF, MP4 |
| 정리 | 폴더 이동, 라이브러리 검색 |
| 브랜드 키트 | 색상·폰트·로고를 모든 디자인에 자동 적용 |

## 프롬프트 예시

```
Use Canva to create an Instagram post about 5 ChatGPT prompts every entrepreneur should use.
Bold typography, dark background with bright accent color, square format 1080x1080.
Respond entirely in Korean (한국어로 답변해주세요).
```

영어로 프롬프트를 작성하고 마지막 줄에 "한국어로 답변해주세요"를 붙이면 분석 품질과 한국어 출력을 동시에 챙길 수 있다.

빠른 참고 템플릿:

| 용도 | 템플릿 |
|---|---|
| 인스타 포스트 | `Use Canva to create an Instagram post about [TOPIC]. Style: [STYLE]. Include a CTA that says [CTA TEXT].` |
| 캐러셀 | `Use Canva to create a [NUMBER]-slide Instagram carousel about [TOPIC]. Bold headlines, one idea per slide.` |
| 브랜드 키트 적용 | `Use Canva to create a [DESIGN TYPE] about [TOPIC]. Use my brand kit for colors and fonts.` |
| 내보내기 | `Export my [DESIGN NAME] design as a [FORMAT] file.` |

## 디자인부터 게시까지 풀 워크플로우

Canva 커넥터에 **Metricool 커넥터**를 더하면 디자인 생성 → 브랜드 키트 적용 → PNG 내보내기 → 인스타그램·틱톡 예약 게시까지 하나의 Claude 대화에서 끝낼 수 있다.

```
1. Use Canva to create an Instagram post about 'Why every creator needs an AI workflow in 2026'.
2. Use my brand kit for the design.
3. Export it as a PNG.
4. Then use Metricool to schedule it on Instagram and TikTok tomorrow at my best posting time.
```

## 더 좋은 디자인을 받는 팁

| 팁 | 설명 |
|---|---|
| 스타일 명시 | "볼드", "미니멀", "레트로", "에디토리얼" 등 구체적일수록 첫 시안이 좋아짐 |
| 정확한 사이즈 | IG 피드 1080×1080, 스토리 1080×1920, X 1200×675 |
| 들어갈 문구 직접 제공 | 헤드라인·서브헤드·CTA를 Claude가 추측하게 만들지 않음 |
| 분위기+컬러 팔레트 지정 | "다크 모던", "밝고 에너제틱" 등 |
| 여러 시안 요청 | 옵션 여러 개를 받아 베스트를 골라 반복 개선 |

## 관련 지식

- [[Claude]] — Canva 커넥터를 실행하는 AI 어시스턴트
- [[MCP]] — Claude와 외부 앱(Canva 포함)을 연결하는 프로토콜 계열의 커넥터 방식
- [[AI 카피라이팅]] — Canva 디자인에 들어갈 카피 문구를 생성하는 선행 작업
- [[SNS 콘텐츠 마케팅]] — Canva로 제작한 디자인이 배포되는 채널

## 출처

- [[Claude x Canva 마스터클래스 (2026)]] — 연결법, 프롬프트 템플릿, 브랜드 키트, 풀 워크플로우
