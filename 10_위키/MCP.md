---
id: kb-mcp
type: standard
status: canonical
aliases: ["Model Context Protocol", "모델 컨텍스트 프로토콜"]
domains: ["AI", "development", "automation"]
related: ["[[Claude Code]]", "[[Claude]]"]
sources: ["[[클로드에 무조건 설치해야 할 24가지]]", "[[주말동안 마스터하는 클로드 가이드북]]"]
created: 2026-08-17
updated: 2026-08-17
---

# MCP (Model Context Protocol)

> Claude 같은 LLM이 외부 파일·앱·데이터베이스·웹을 직접 다루게 해주는 연결 표준. "일반 클로드가 대화만 잘하는 사람이라면, MCP를 붙인 클로드는 파일을 읽고 웹을 열고 앱을 만지고 결과까지 정리하는 사람"에 비유된다.

## 개요

MCP는 AI 모델에게 "손과 눈"을 달아주는 장치다. MCP 서버 하나하나가 특정 외부 시스템(GitHub, Notion, PostgreSQL 등)에 접근하는 창구 역할을 하며, 필요한 조합만 골라 붙이는 방식으로 쓴다. 24개를 한 번에 설치하는 것이 아니라 자신의 업무에 맞는 조합을 고르는 것이 핵심이다.

## 대표 MCP 서버 (카테고리별)

| 카테고리 | 서버 | 역할 |
|---|---|---|
| 기본 엔진 | Filesystem, Memory, Sequential Thinking | 허용 폴더 파일 읽기·정리 / 취향·맥락 장기 저장 / 복잡한 문제 단계별 분해 |
| 코드/개발 | GitHub, Git, Context7, Docker, Claude Code Action | 이슈·PR·커밋 다루기 / 최신 라이브러리 문서 참조 / 컨테이너 관리 / GitHub Actions 연동 자동 리뷰 |
| 웹/리서치 | Perplexity, Playwright, Firecrawl, Fetch, Brave Search, Exa | 출처 기반 실시간 검색 / 브라우저 조작 / 웹페이지→마크다운 변환 / 특정 URL 읽기 / 의미 기반 검색 |
| 업무앱 | Google Drive, Slack, Notion, Linear, Figma | 문서·메시지·이슈·디자인 맥락을 직접 연결 |
| 데이터/제작 | PostgreSQL, SQLite, Glif | 자연어로 DB 질의 / 로컬 DB·CSV 분석 / 이미지·콘텐츠 생성 워크플로우 |
| 브라우저 | Chrome MCP | 웹사이트 클릭·입력·캡처 (Claude Code 내장 기능 우선 확인 권장) |

## 설치 원칙

- 한 번에 다 켜지 않고, 업무 유형별로 필요한 것만 추가한다 (예: 리서치 중심이면 Perplexity·Firecrawl·Playwright·Exa)
- 파일 권한은 폴더 단위로 제한 — 컴퓨터 전체를 열지 않는다
- API 키는 채팅창에 직접 붙여넣지 않고 환경변수로 관리
- GitHub 토큰 등은 처음엔 읽기 전용으로 최소 권한만 부여
- 처음 보는 MCP는 바로 설치하지 않고 최근 커밋·이슈·README를 먼저 확인
- 쓰기 권한(DB, 파일시스템 등)은 읽기 전용으로 먼저 테스트한 뒤 마지막에 켠다

## 연결 방법

[[Claude Code]]에서는 채팅창에 `/mcp` 입력 → 연결할 서비스 선택 → Authenticate로 브라우저 로그인하면 별도 터미널 명령 없이 연결된다. Claude Desktop 설정 파일(`mcpServers` JSON)에 직접 등록하는 방법도 있다.

## 관련 지식

- [[Claude Code]] — MCP를 실제로 연결해 쓰는 대표 실행 환경

## 출처

- [[클로드에 무조건 설치해야 할 24가지]] — MCP 24종 목록, 직업별 추천 조합, 설치 시 보안 수칙
- [[주말동안 마스터하는 클로드 가이드북]] — `/mcp` 연결 방법, 안전 팁
