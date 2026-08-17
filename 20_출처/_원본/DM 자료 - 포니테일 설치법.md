---
title: "📩 DM 자료 — ‘포니테일’ 설치법"
source: "https://breezy-bar-fa2.notion.site/DM-387919e704a38040b2ebc75e7cd834a0"
notion_page_id: "387919e7-04a3-8040-b2eb-c75e7cd834a0"
archived_date: "2026-08-01"
---

# 📩 DM 자료 — ‘포니테일’ 설치법

(제가 직접 삽질한 설치 방법입니다🫠)

.

안녕하세요! 댓글 남겨주셔서 감사합니다~ 🙌

처음에 `/plugin`이 안 떠서 한참 헤맸거든요. 제가 겪은 순서 그대로, 막힌 데까지 다 적었으니, 그대로 하시면 돼요!

⚠️ **먼저 — 이건 *****터미널(CLI) 클로드코드***** 기준이에요.** VS Code 터미널이나 터미널 앱에서 `claude` 친 거요. **데스크톱 GUI 앱에선 **`**/plugin**`**이 안 떠요** — 저도 이거 때문에 처음에 한참 헷갈렸습니다. 데스크톱 쓰시면 터미널에서 하시는 걸 추천해요!

#### 📌 제일 중요 — 아무 깃이나 믿고 깔면 안 돼요!

포니테일 같은 플러그인은 *그 코드가 내 컴퓨터에서 실행*돼요. 출처 모르는 깃허브를 막 설치하면 악성코드가 들어올 수도 있어요. 설치 중에 도구가 "이거 믿을 거예요?" 경고를 띄우는 것도 그 때문이에요 — **그 경고는 안전장치니까 무시하지 마세요.**

👉 포니테일은 MIT 오픈소스 + 깃허브 별 46.9k개라 저는 믿고 썼지만, **출처를 모르는 플러그인은 절대 깔지 마세요.**

---

#### 🟦 클로드코드 설치법

**STEP 0. 클로드코드부터 최신으로**

`/plugin`이 "Unknown command"로 안 뜨면 = 구버전이니,

- 버전 확인:

```
claude --version
```

- 업데이트 (npm으로 깔았으면):

```
npm install -g @anthropic-ai/claude-code@latest
```

- 그다음 터미널 한 번 껐다 켜기 (native 설치면 자동 업데이트라 재시작만)

**STEP 1. 포니테일 등록 + 설치 (⚠️ 한 줄씩 따로!)**

두 줄 한 번에 치면 깨져요. 하나 치고 엔터, 또 하나 치고 엔터:

```
/plugin marketplace add DietrichGebert/ponytail
```

```
/plugin install ponytail@ponytail
```

→ 설치 화면 뜨면 **"Install for you (user scope)"** 골라요. (모든 폴더에서 쓰려고. 혼자 작업이면 협업자 옵션은 X)

**STEP 2. 적용**

```
/reload-plugins
```

**STEP 3. 켜고 끄기**

```javascript
/ponytail full
```

← 켜기 (강도: lite < full < ultra)

```
/ponytail off
```

← 끄기 ※ `off`는 자동완성 메뉴에 안 떠요. `/ponytail off` 통째로 치면 돼요.

**STEP 4. 실험 (전후 비교)**

같은 걸 두 번 시켜서 줄 수 비교:

1. `/ponytail off` → "프로필 카드 만들어줘" → 줄 수 기록

1. `/clear` (대화 비우기) → `/ponytail full` → 같은 거 → 줄 수 기록

→ AI한테 `방금 만든 거 총 몇 줄이야?` 물어보면 알려줘요.

**STEP 5. 더 있는 명령**

- `/ponytail-gain` 측정 자랑 화면

- `/ponytail-review` 지금 코드 과잉 점검

- `/ponytail-audit` 전체 저장소 스캔

---

#### 🟧 코덱스(Codex) 설치법

클로드코드랑 명령이 달라요 — `/plugin`은 안 먹어요!

**1. 터미널에서 등록** (`claude` 아니라 `codex`):

```javascript
codex plugin marketplace add DietrichGebert/ponytail
```

**2. codex 실행** → `codex`

**3.** `/plugins` (복수형!) 열기 → Ponytail 선택 → 설치

**4.** `/hooks` 열기 → 라이프사이클 hooks 2개 검토하고 **신뢰(trust)** (← 이것도 위 📌 보안 확인! 믿을 때만 trust)

**5.** 새 thread(대화) 시작 *(데스크톱앱은 설치 후 재시작)*

⚠️ **솔직 주의 2개 (이거 꼭 읽어요):**

1. `/ponytail-gain`이 보여주는 80~94%는 *포니테일 자체 벤치마크 자랑*이에요. 제가 직접 해보니 51%였어요(실전 평균은 54% 정도래요). 그 수치 그대로 믿지 마세요.

1. 서드파티 플러그인이라 *코드 실행 권한*이 들어가요. 포니테일은 MIT 오픈소스라 저는 써봤지만, 출처 모르는 플러그인은 함부로 깔지 마세요.

> **남들 자랑 수치 받아쓸 때, 저는 직접 해봅니다. 검증하는 AI일지 팔로우🔥
> @muni.view**
