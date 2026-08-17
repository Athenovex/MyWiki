---
id: kb-ponytail
type: tool
status: canonical
aliases: ["포니테일"]
domains: ["development", "AI"]
related: ["[[Claude Code]]", "[[Codex]]"]
sources: ["[[DM 자료 - 포니테일 설치법]]"]
created: 2026-08-17
updated: 2026-08-17
---

# Ponytail

> [[Claude Code]]·[[Codex]]용 오픈소스 플러그인(MIT 라이선스, GitHub 스타 4.69만). AI가 코드를 짤 때 발생하는 과잉 엔지니어링·불필요한 코드량을 줄여주는 것을 목표로 한다.

## 개요

`DietrichGebert/ponytail` 저장소로 배포되는 서드파티 플러그인이며, 설치되면 코드가 사용자 컴퓨터에서 직접 실행되므로 **출처가 검증된 플러그인만 설치**해야 한다 — 설치 도구가 띄우는 신뢰 여부 확인 경고는 무시하지 말아야 할 안전장치다.

## Claude Code 설치

```
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

두 명령은 반드시 한 줄씩 따로 입력한다(한 번에 붙여 넣으면 깨짐). 설치 화면에서 "Install for you (user scope)"를 선택하면 모든 폴더에서 사용 가능하다. 설치 전 `claude --version`으로 최신 버전인지 확인하고, 구버전이면 `npm install -g @anthropic-ai/claude-code@latest`로 업데이트한다.

| 명령 | 기능 |
|---|---|
| `/reload-plugins` | 설치 후 적용 |
| `/ponytail lite` / `full` / `ultra` | 강도별로 켜기 |
| `/ponytail off` | 끄기 (자동완성에 안 뜨므로 전체를 직접 입력) |
| `/ponytail-gain` | 코드량 절감 효과 측정 화면 |
| `/ponytail-review` | 현재 코드의 과잉 여부 점검 |
| `/ponytail-audit` | 저장소 전체 스캔 |

## Codex 설치

Codex는 `/plugin`이 아니라 별도 명령 체계를 쓴다.

```
codex plugin marketplace add DietrichGebert/ponytail
```

이후 `codex` 실행 → `/plugins`(복수형) 메뉴에서 Ponytail 설치 → `/hooks`에서 라이프사이클 훅 2개를 검토하고 신뢰(trust) 승인 → 새 대화(thread) 시작.

## 효과 검증 방법

같은 요청을 두 번 실행해 코드 줄 수를 비교한다: ① `/ponytail off` → 요청 실행 → 줄 수 기록 → ② `/clear`로 대화 초기화 → `/ponytail full` → 동일 요청 → 줄 수 기록. "방금 만든 거 총 몇 줄이야?"라고 물으면 AI가 집계해준다.

> ⚠️ **수치 주의**: `/ponytail-gain`이 보여주는 80~94% 절감률은 플러그인 자체 벤치마크로, 실제 사용자가 직접 테스트한 결과는 51%(제작자 언급 실전 평균은 약 54%)였다. 공개된 절감률 수치를 그대로 신뢰하지 말고 자신의 작업으로 직접 검증하는 것이 권장된다.

## 관련 지식

- [[Claude Code]] — 포니테일이 설치되는 주 실행 환경
- [[Codex]] — 포니테일을 지원하는 또 다른 실행 환경 (설치 명령 체계가 다름)

## 출처

- [[DM 자료 - 포니테일 설치법]] — 설치 전 과정, 실전 검증 수치, 보안 주의사항
