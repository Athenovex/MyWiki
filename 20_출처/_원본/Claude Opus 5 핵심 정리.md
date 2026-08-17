---
title: "Claude Opus 5 핵심 정리"
source: "https://fieldby.notion.site/Claude-Opus-5-3a8d730b39538184afe2d87347df068e?fbclid=PAVERTVgTT5hVleHRuA2FlbQIxMABzcnRjBmFwcF9pZA81NjcwNjczNDMzNTI0MjcAAafFY9vZFGpx9Ph37xtXq0LbB4rrRW5ql9f8xywFC8t3Mt1aezaDyy-gfvsyqg_aem_cIuhYc58MaqFt0uAiGDLHg"
notion_page_id: "3a8d730b-3953-8184-afe2-d87347df068e"
archived_date: "2026-08-01"
---

# Claude Opus 5 핵심 정리

> 🔎 한눈 요약
> · 2026년 7월 24일 앤트로픽이 공개한 새 플래그십 AI 모델
> · 성능은 직전 모델(Opus 4.8)의 2배 이상, 가격은 그대로 (입력 $5 / 출력 $25)
> · 코딩·컴퓨터 조작·업무 자동화 등 대부분의 시험에서 1위, '어긋난 행동' 점수는 최근 모델 중 최저

### 1. 무엇이 나왔나

앤트로픽이 Claude Opus 5를 공개했습니다. 최상위 모델 Fable 5에 가까운 지능을 절반 비용으로 쓸 수 있게 설계된 플래그십 모델로, Claude Max 요금제의 기본 모델이자 Claude Pro에서 쓸 수 있는 가장 강력한 모델입니다.

![이미지](https://cdn.sanity.io/images/4zrzovbb/website/54b7ab1d2c2521f83ae5d2da5f9d99321c370d24-2880x1620.png)

### 2. 가격과 이용 방법

- 가격: 입력 100만 토큰당 5달러, 출력 25달러 — 직전 모델 Opus 4.8과 동일

- Fast 모드: 기본 속도의 약 2.5배로 실행. 요금은 기본가의 2배

- 쓸 수 있는 곳: Claude.ai · Claude API(claude-opus-5) · Claude Code · Claude Cowork

- Max 요금제 = 기본 모델 / Pro 요금제 = 최상위 모델로 제공

### 3. 성적표 — 주요 벤치마크

공식 발표에 실린 결과입니다. 아래 그래프에서 주황색 선이 Opus 5입니다.

- 코딩 (Frontier-Bench v0.1): 전 모델 1위 — Opus 4.8의 2배 이상 성능을 더 낮은 작업당 비용으로 (43.3% vs 21.1%)

![이미지](https://cdn.sanity.io/images/4zrzovbb/website/7530b1086992936d7e9d5796a892d1e8fa063253-3840x2160.png)

- 처음 보는 문제 (ARC-AGI 3): 학습한 적 없는 새 문제 풀이 — 2위 모델의 3배 점수 (30.2%)

![이미지](https://cdn.sanity.io/images/4zrzovbb/website/b5e071ba6a9ce5628b4662f05484d1806a9fdc94-3840x2160.png)

- 컴퓨터 조작 (OSWorld 2.0): 모든 비용 구간에서 1위 — Fable 5 최고 기록을 약 1/3 비용으로 추월 (70.6%)

![이미지](https://cdn.sanity.io/images/4zrzovbb/website/44fac8bd76238d8c09305ec7fe1511670d45c6d6-3840x2160.png)

- 업무 자동화 (Zapier AutomationBench): 같은 비용에서 2위 모델의 약 1.5배 통과율 (26.0%)

![이미지](https://cdn.sanity.io/images/4zrzovbb/website/c7c726c5588b69c944dcc205bd1ba7ebdf8c2259-3840x2160.png)

- 과학 연구: 유기화학 과제 +10.2점, 단백질 과제 +7.7점 (Opus 4.8 대비, 내부 벤치마크)

전체 비교표 (Opus 5 · Fable 5 · Opus 4.8 · GPT-5.6 Sol):

![이미지](https://cdn.sanity.io/images/4zrzovbb/website/a8fb4f77a9fe240e6f27f3bdc47a137f3c74a29d-2600x2578.png)

### 4. 일하는 방식 — 스스로 검증하고 끝까지

Opus 5는 자기 결과물을 검증하고 성공할 때까지 신중하게 반복하는 능력이 크게 강해졌습니다. 공식 발표에 실린 사례 세 가지입니다.

- 도면을 직접 '볼' 수 없는 조건에서 3D 부품 모델링 과제를 받자, 픽셀에서 형상을 읽어내는 컴퓨터 비전 코드를 스스로 짜서 부품을 복원했습니다. 같은 조건의 경쟁 모델은 5번 시도에도 실패했습니다.

- 유명 오픈소스 패키지 매니저의 실제 버그를 받아, 커뮤니티 패치가 놓친 근본 원인까지 찾아 고쳤습니다. 경쟁 모델은 겉 증상만 고치고 '해결됐다'고 보고했습니다.

- 트레이딩 회사 엔지니어가 한 세션 만에 신규 거래소 시세 연동 기능을 완성했습니다. 검증할 실시간 데이터가 없자 테스트 장치까지 직접 만들어 코드를 확인했습니다.

### 5. 눈으로 보는 결과물 — 공식 영상 2개

**① 작동하는 가상 풍동 — 자동차 주변 공기 흐름을 시각화한 인터랙티브 실험실**

[동영상](https://www.youtube.com/watch?v=4WQd-8d5j4k)

직접 체험하기 → [바람 실험실 열기](https://assets.claude.ai/brand/artifacts/blog/opus/5-aeolus-demo.html)

**② 3D 인터랙티브 동물 세포 — 각 기관을 눌러보며 탐색**

[동영상](https://www.youtube.com/watch?v=2eiKnt9Hi6I)

직접 체험하기 → [3D 세포 열기](https://assets.claude.ai/brand/artifacts/blog/opus/5-sectio-demo.html)

### 6. 더 믿을 수 있어졌다 — 안전·정렬

- 자동 행동 감사에서 '어긋난 행동' 점수 2.3 — 최근 모델 중 가장 낮음

- 사람을 속이는 행동이 가장 적고, 오용 시도에 대한 저항은 가장 강함

![이미지](https://cdn.sanity.io/images/4zrzovbb/website/76d4af96516ffca2aceb4c1d0b0a83e2720d874b-3840x2160.png)

### 7. 개발자용 새 기능 2가지

- 대화 중 도구 변경(베타): 대화 도중 Claude가 쓸 도구를 바꿔도 프롬프트 캐시가 유지됩니다

- 자동 폴백(베타): 안전 분류기에 걸린 요청을 다른 모델로 자동 우회 — Claude.ai·Code·Cowork에선 기본으로 Opus 4.8이 이어받습니다

### 8. 원문·링크

📄 공식 발표 원문: [Introducing Claude Opus 5](https://www.anthropic.com/news/claude-opus-5)

🎬 영상: [풍동](https://www.youtube.com/watch?v=4WQd-8d5j4k)  ·  [3D 세포](https://www.youtube.com/watch?v=2eiKnt9Hi6I)

이미지·차트 출처: Anthropic 공식 블로그
