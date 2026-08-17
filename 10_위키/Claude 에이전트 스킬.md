---
id: kb-claude-agent-skills
type: concept
status: canonical
aliases: ["Claude Skills", "클로드 스킬", "Agent Skills", "에이전트 스킬"]
domains: ["AI", "productivity"]
related: ["[[Claude Code]]", "[[Claude]]", "[[Claude Cowork]]"]
sources: ["[[클로드 사기 스킬 TOP 5 완벽 가이드]]", "[[교육 에이전트 스킬 사용 가이드]]", "[[클로드 디자인 스킬 TOP 5 설치 가이드]]", "[[에이전트 스킬 라이브러리를 오픈소스 공개 - AI 디자인 스킬 75개]]", "[[일잘러가 몰래 쓰는 클로드 스킬]]"]
created: 2026-08-17
updated: 2026-08-17
---

# Claude 에이전트 스킬 (Agent Skills)

> Claude에게 특정 작업의 절차·노하우·금지사항을 담아 설치하는 지침서 파일(`SKILL.md`). "클로드는 요리사, 스킬은 요리 레시피"에 비유되며, 한 번 설치하면 관련 요청이 들어올 때 Claude가 알아서 꺼내 쓴다.

## 개요

스킬은 매번 "이런 말투로 써줘", "이 형식 지켜줘"를 반복 설명하는 비효율을 없애는 기능이다. 파일 하나(`SKILL.md`)가 하나의 매뉴얼이며, Claude·Codex·Cursor 등 "에이전트 스킬" 표준을 지원하는 여러 AI 도구에서 공용으로 쓸 수 있다. 커뮤니티에 공개된 스킬만 수만 개이며 대부분 무료다.

## 설치 방법

| 환경 | 방법 |
|---|---|
| Claude 웹/앱 (Pro 이상) | GitHub의 `Code → Download ZIP` → 설정(Settings) → 기능(Capabilities)에서 "클라우드 코드 실행" 켜기 → Customize → Skills → "+" → ZIP 업로드 → 목록에서 토글 켜기 |
| [[Claude Code]] | `npx skills add <저장소>` 또는 `git clone <저장소> ~/.claude/skills/<이름>` 한 줄로 설치. `/plugin` 마켓플레이스를 통한 설치도 가능 |

설치 후 "지금 사용할 수 있는 스킬 목록 보여줘"로 적용 여부를 확인할 수 있고, 세션 재시작이 필요한 경우가 있다.

## 발동 방식

- **자동 발동**: 요청 내용이 스킬 설명과 맞아떨어지면 Claude가 알아서 선택해 사용
- **직접 호출**: "OO 스킬 써서 해줘"처럼 이름을 언급하거나 `/스킬이름`으로 슬래시 호출하면 100% 발동

여러 스킬을 동시에 설치해도 작업에 맞는 것만 골라 쓰므로 충돌 걱정은 적고, 오히려 조합(예: 마케팅 스킬로 기획 + 영상 스킬로 제작)될 때 시너지가 난다.

## 대표 스킬 카탈로그

### 글쓰기 / 콘텐츠

| 스킬 | 용도 | 링크 |
|---|---|---|
| humanizer | AI 특유의 문체 흔적(줄표, "certainly" 등)을 지우고 사람처럼 자연스럽게 다듬음 | github.com/blader/humanizer |
| beautiful prose | 군더더기 없는 또렷한 문장으로 다듬음 (에세이·칼럼용) | github.com/SHADOWPR0/beautiful_prose |
| hook generator | 반전형·혜택형·변화형 등 검증된 공식으로 SNS 첫 문장(훅) 생성 | github.com/charlie947/social-media-skills |

### 리서치 / 기획

| 스킬 | 용도 | 링크 |
|---|---|---|
| deep research | 여러 출처를 교차 검증하고 신뢰도 점수까지 매겨 리포트 작성 | github.com/199-biotechnologies/claude-deep-research-skill |
| brainstorming | 질문을 주고받으며 막연한 아이디어를 설계안으로 다듬음 | github.com/obra/superpowers |
| writing plans | 개발 작업을 파일 경로·검증 단계까지 포함한 실행 계획서로 정리 | github.com/obra/superpowers |

### 디자인 / 프론트엔드

| 스킬 | 용도 | 링크 |
|---|---|---|
| frontend-design | 코딩 전에 색·글꼴·여백 등 미적 방향을 먼저 정해 "AI 티" 나는 뻔한 디자인을 피함 (Anthropic 공식) | github.com/anthropics/skills |
| taste-skill | 결과물의 과감함·모션·밀도를 다이얼처럼 조절 (GitHub 스타 5.5만) | github.com/Leonxlnx/taste-skill |
| animate | 과하게 튕기는 모션 대신 절제된 고급스러운 애니메이션 타이밍 적용 | github.com/delphi-ai/animate-skill |
| Color Expert | OKLCH 등 인지 기반 색 공간으로 접근성 기준을 만족하는 컬러 팔레트 구성 | github.com/meodai/skill.color-expert |
| diagram-design | 13가지 에디토리얼 다이어그램 타입을 HTML+SVG로 생성, 브랜드 색·폰트 자동 반영 | github.com/cathrynlavery/diagram-design |
| frontend-slides | PPT를 애니메이션 있는 웹 프레젠테이션(HTML 슬라이드)으로 변환 | github.com/zarazhangrui/frontend-slides |
| UI/UX Pro Max | UI 스타일 67종·컬러 팔레트 161종·폰트 조합 57종·UX 규칙 99개 탑재 | github.com/nextlevelbuilder/ui-ux-pro-max-skill |
| MengTo Agent Skills 75개 | 웹디자인·랜딩페이지·모션·WebGL·UI 제작용 대규모 무료 오픈소스 스킬 라이브러리 (web-design 62개, codex 10개, ui 1개, media 2개 카테고리) | github.com/MengTo/Skills |

### 도구 연결 (MCP형 스킬)

| 스킬 | 용도 |
|---|---|
| playwright-mcp | Claude가 브라우저를 직접 열어 결과물을 눈으로 확인·수정 ("만들고→보고→고치는" 순환) |
| Figma MCP | 피그마 시안의 색상값·간격·글꼴 수치를 그대로 읽어와 코드로 구현 (개인 액세스 토큰 필요) |

### 마케팅 / 업무

| 스킬 | 용도 | 링크 |
|---|---|---|
| Marketing Skills Library | 카피라이팅·SEO·CRO·이메일 시퀀스 등 마케팅 스킬 40여 종 패키지 | github.com/coreyhaines31/marketingskills |
| internal-comms | 회사 톤에 맞춰 상태 보고·뉴스레터·FAQ를 직급별로 조절해 작성 | github.com/anthropics/skills |
| notion-skills | 대화·회의·리서치 내용을 구조화된 Notion 문서로 자동 정리 | github.com/tommy-ca/notion-skills |
| Education Agent Skills | 수업 설계·학습목표·질문 생성·형성평가·채점 기준을 지원하는 교사용 스킬 모음 | github.com/GarethManning/education-agent-skills |

### 개발 / 메모리

| 스킬 | 용도 |
|---|---|
| superpowers | 아이디어→질문으로 요구사항 정리→작업 분할→실행→자기검증까지 수행하는 풀코스 프레임워크. GitHub 스타 4.1만, 설치 12만 회 |
| Claude Mem | 세션이 끝나도 작업 내용을 자동 요약·저장해 다음 세션에 이어서 작업 가능 |
| Remotion | 대본·장면 구성·모션그래픽까지 자동으로 만들어 완성된 MP4 영상으로 렌더링 |

## 관련 지식

- [[Claude Code]] — 스킬을 `~/.claude/skills/`에 설치해 실행하는 주된 환경
- [[Claude Cowork]] — `.skill` 파일을 채팅창에 끌어와 저장하는 방식으로도 스킬 사용 가능

## 출처

- [[클로드 사기 스킬 TOP 5 완벽 가이드]] — Remotion, Claude Mem, UI/UX Pro Max, Marketing Skills, Superpowers
- [[교육 에이전트 스킬 사용 가이드]] — Education Agent Skills
- [[클로드 디자인 스킬 TOP 5 설치 가이드]] — frontend-design, taste-skill, playwright-mcp, animate, Figma MCP 설치법
- [[에이전트 스킬 라이브러리를 오픈소스 공개 - AI 디자인 스킬 75개]] — MengTo Agent Skills 75개 라이브러리
- [[일잘러가 몰래 쓰는 클로드 스킬]] — 15가지 실무 스킬 카탈로그, 설치법 A/B
