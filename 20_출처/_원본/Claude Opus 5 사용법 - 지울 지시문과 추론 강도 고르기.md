---
title: "🎚️ Claude Opus 5 사용법 — 지울 지시문과 추론 강도 고르기"
source: "https://app.notion.com/p/Claude-Opus-5-3a9fd99f0e5f81aea1b2c1cfbe3df344?fbclid=PAVERTVgTT7shleHRuA2FlbQIxMABzcnRjBmFwcF9pZA81NjcwNjczNDMzNTI0MjcAAafFY9vZFGpx9Ph37xtXq0LbB4rrRW5ql9f8xywFC8t3Mt1aezaDyy-gfvsyqg_aem_cIuhYc58MaqFt0uAiGDLHg"
notion_page_id: "3a9fd99f-0e5f-81ae-a1b2-c1cfbe3df344"
archived_date: "2026-08-01"
---

# 🎚️ Claude Opus 5 사용법 — 지울 지시문과 추론 강도 고르기

> ✨ 
> 
> **앤트로픽이 Opus 5용 프롬프트 문서에서 먼저 말한 건 "이렇게 쓰세요"가 아니라 "이건 지우세요"입니다.**
> 
> 예전 모델에서 품질을 올려줬던 지시가 지금은 비용만 늘리고 결과는 그대로거나 나빠집니다.
> 
> 공식 문서에서 바로 쓸 것만 골라, 복붙 가능한 형태로 정리했어요.

`2026-07-26 기준` · `앤트로픽 공식 문서` · `Claude Opus 5` · [**공식 프롬프트 문서 원문**](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5)

---

### 📊 한눈에 보기

| 항목 | 내용 |
| --- | --- |
| 추론 강도 | 다섯 단계 — 낮음·중간·높음·아주 높음·최대 |
| 기본값 | '높음' (따로 설정하지 않으면 이 값) |
| 시작 지점 | '높음'으로 시작해 직접 돌려보고 조정 |
| 비용·속도 조절 | 낮음·중간을 주된 수단으로 쓰기 |
| 지울 지시 | 재확인 요구 · 검증 단계 추가 · 검증용 보조 클로드 |
| 한 번에 기억하는 양 | 100만 토큰 (한 번에 쓰는 답은 최대 12.8만 토큰) |
| 값 | 100만 토큰당 입력 5달러 · 출력 25달러 (Opus 4.8과 동일) |
| Fast 모드 | 기본보다 약 2.5배 빠름, 값은 기본가의 두 배 |

출처 — [**Opus 5 발표문**](https://www.anthropic.com/news/claude-opus-5) · [**추론 강도 공식 문서**](https://platform.claude.com/docs/en/build-with-claude/effort)

---

### 🔄 뭐가 달라졌나

- 지시를 더 붙이면 좋아지던 관계가 깨졌습니다. Opus 5는 스스로 하는 일이 늘어서, 같은 지시를 겹쳐 쓰면 토큰만 더 씁니다.

- 답이 길다고 좋은 답이 아닙니다. 길이는 직접 지정해야 원하는 만큼 나옵니다.

- 이전 모델에서 쓰던 설정을 그대로 옮기면 손해입니다. 강도를 처음부터 다시 재보라는 게 공식 안내에요.

![앤트로픽 공식 성능 종합 — Opus 5와 다른 모델 비교](https://www-cdn.anthropic.com/images/4zrzovbb/website/a8fb4f77a9fe240e6f27f3bdc47a137f3c74a29d-2600x2578.png)

이미지 출처 — [**Opus 5 발표문**](https://www.anthropic.com/news/claude-opus-5)

- ****숫자로 보면 — 값은 그대로인데 순위가 올라갔습니다****

---

### 🎚️ 추론 강도 고르기

추론 강도는 **생각의 양**을 조절하는 손잡이입니다. 답변 길이를 줄이는 기능이 아니라, 모델이 속으로 얼마나 굴릴지를 정합니다.

![Frontier-Bench v0.1 — 추론 강도를 올릴 때마다 코딩 성적이 어떻게 움직이는지](https://www-cdn.anthropic.com/images/4zrzovbb/website/7530b1086992936d7e9d5796a892d1e8fa063253-3840x2160.png)

이미지 출처 — [**Opus 5 발표문**](https://www.anthropic.com/news/claude-opus-5)

- ****다섯 단계 — 언제 어느 칸에 두나****

- ****강도를 올리면 실제로 얼마나 더 쓰나****

- ****Fast 모드는 언제 쓰나****

- ****생각을 끄면 안 되는 이유****

---

### 🧹 지워야 할 지시문

- ****① "다시 확인해봐" 류 — 재확인 요구****

- ****② "검증 단계를 넣어라" 류 — 과잉 검증****

- ****③ "심각한 것만 보고해" — 코드 검토에서 범위 좁히기****

---

### 🧩 내 것으로 응용

- ****짧게 받는 지시문 — 그대로 복붙****

- ****진행 보고 지시문 — 자동화 작업에서 답답함 줄이기****

- ****작업별로 어느 강도부터 켜나****

---

### 🚧 자주 막히는 부분

- ****답이 너무 길게 나와요****

- ****예전 프롬프트를 그대로 옮겼는데 전보다 못해요****

- ****답변에 이상한 태그가 섞여 나와요****

- ****사실을 물었는데 틀린 답이 섞여요****

- ****이 일은 아직 다른 모델이 나아요****

> ✅ 
> 
> **솔직하게 — 지시문 하나 붙여서 전부 해결되는 건 아니에요.**
> 
> 같은 지시도 작업 종류에 따라 결과가 갈립니다. 위 문장들을 넣은 뒤 본인 작업으로 두세 번 돌려보고, 품질이 버티는 선에서 강도를 낮추는 게 순서입니다.

![OSWorld 2.0 — 컴퓨터를 직접 조작하는 작업, 작업당 비용 대비 성적](https://www-cdn.anthropic.com/images/4zrzovbb/website/44fac8bd76238d8c09305ec7fe1511670d45c6d6-3840x2160.png)

![AutomationBench — 실제 업무 자동화 통과율을 작업당 비용과 함께 본 것](https://www-cdn.anthropic.com/images/4zrzovbb/website/c7c726c5588b69c944dcc205bd1ba7ebdf8c2259-3840x2160.png)

이미지 출처 — [**Opus 5 발표문**](https://www.anthropic.com/news/claude-opus-5)

---

### ✅ 정리

**덜 시키고, 강도를 직접 고르는 것** — 이 두 가지가 Opus 5에서 달라진 전부입니다.

[**공식 프롬프트 문서 보기**](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5) · [**추론 강도 문서**](https://platform.claude.com/docs/en/build-with-claude/effort) · [**Opus 5 발표문**](https://www.anthropic.com/news/claude-opus-5) · [**Artificial Analysis 분석**](https://artificialanalysis.ai/articles/opus-5)

---

💡매일 업데이트 되는 AI 소식과 활용법을 가장 빠르게 받아보고 싶다면?

[프롬왓 | AI 크리에이터 (@prompt_what) • Instagram](https://www.instagram.com/prompt_what/)

**✨계정 팔로우해놓기!**

*PROMPT WHAT — @prompt_what*
