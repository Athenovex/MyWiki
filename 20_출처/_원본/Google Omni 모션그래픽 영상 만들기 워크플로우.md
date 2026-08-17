---
title: "Google Omni 모션그래픽 영상 만들기 워크플로우"
source: "https://kimminwook.notion.site/Google-Omni-3928c53193a78026b720db80376f97e1?fbclid=PAT01DUATL82VleHRuA2FlbQIxMABzcnRjBmFwcF9pZA81NjcwNjczNDMzNTI0MjcAAaeRWmWB-ymtYSeYWSRATylHfmhzCmgf5aRz3s_rFvCHGGyUcpjyxr-oTlx3Zw_aem_JRPh-B9ThvwcSL5SJpxSrw"
notion_page_id: "3928c531-93a7-8026-b720-db80376f97e1"
archived_date: "2026-08-01"
---

# Google Omni 모션그래픽 영상 만들기 워크플로우

## 🎬 구글 옴니로 영상 편집하기 — 단계별 워크플로우

> **Claude + Gemini Omni**를 활용해 마음에 드는 영상 스타일을 내 대본으로 그대로 재현하는 방법.
> **편집 기술이 전혀 없어도 괜찮습니다.**

**사용 도구:** `Claude AI` → `Gemini Omni` → `CapCut` → `Instagram / YouTube`

---

### 📋 전체 흐름 한눈에 보기

| 단계 | 할 일 | 사용 도구 |  |
| --- | --- | --- | --- |
| 1️⃣ | 레퍼런스 영상 찾기 | Instagram, Pinterest, YouTube |  |
| 2️⃣ | 스타일 분석 프롬프트 붙여넣기 | Claude |  |
| 3️⃣ | 씬별 프롬프트 받기 | Claude |  |
| 4️⃣ | 씬 하나씩 영상 생성 | Gemini Omni |  |
| 5️⃣ | 채팅으로 수정 요청 | Gemini Omni |  |
| 6️⃣ | 최종 편집 & 내보내기 | CapCut |  |

---

### 1️⃣ 레퍼런스 영상 찾기

**Instagram, Pinterest, YouTube에서 찾으세요**

마음에 드는 스타일의 모션 디자인 영상을 **1~2개** 찾습니다.
화면 녹화하거나 저장해 두세요. 그리고 **내 대본**도 미리 준비합니다 — 영상에서 실제로 나갈 정확한 문장이면 됩니다.

> 💡 **어디서 찾을까?**
> Instagram 릴스나 YouTube에서 아래 키워드로 검색해 보세요.
> - `kinetic typography reel` (키네틱 타이포그래피 릴)
> - `motion design short` (모션 디자인 쇼츠)
> - `AI video edit style` (AI 영상 편집 스타일)
> 
> 내가 원하는 에너지가 느껴지는 영상이라면 일단 저장!

---

### 2️⃣ Claude에 프롬프트 붙여넣기

**레퍼런스 + 내 대본 업로드**

레퍼런스 영상(또는 캡처 이미지)을 업로드하고, 내 대본을 붙여넣습니다.
그다음 아래 프롬프트를 그대로 붙여넣으면 Claude가 스타일을 분석하고 **바로 쓸 수 있는 씬별 프롬프트**를 만들어 줍니다.

> 📋 **아래 두 버전 중 하나를 선택해 전체를 복사한 뒤 Claude에 붙여넣으세요**
> 한국어·영어 어느 쪽을 써도 결과는 동일하게 작동합니다.

#### 🇰🇷 한국어 버전

```
레퍼런스 영상과 내 대본을 첨부합니다.
이 영상의 '스타일'을 AI 영상 생성기(Gemini Omni / Veo)로
내 대본에 맞게 재현하고 싶습니다.

1단계: 레퍼런스 영상을 깊이 있게 분석해 주세요.
 - 애니메이션 스타일 (2D, 3D, 키네틱 타이포그래피, 플랫 디자인)
 - 움직임의 특징 (속도, 이징, 바운스, 부드러운지 스냅감 있는지)
 - 전환 방식 (컷, 와이프, 모핑, 줌)
 - 색상 팔레트 (정확한 색상값과 배경)
 - 타이포그래피 스타일 (굵기, 애니메이션, 텍스트 위치)
 - 카메라 움직임 (고정, 줌, 팬, 흔들림)
 - 전체 분위기와 페이싱 (빠름, 차분함, 드라마틱)
 - 사운드 느낌 (휘익 소리, 클릭음, 베이스 히트, 음악 스타일)

2단계: 내 대본을 씬당 8~10초 단위로 나눠 주세요.
(AI가 한 번에 최대 10초까지만 생성할 수 있기 때문입니다.)

3단계: 각 씬마다 아래 내용이 포함된 상세 프롬프트를
하나씩 작성해 주세요.
 - 화면에 무엇이 나타나고 어떻게 움직이는지
 - 화면에 표시될 정확한 텍스트 (최대 5~6단어)
 - 레퍼런스와 일치하는 색상, 배경, 타이포그래피
 - 카메라 움직임
 - 다음 씬으로 넘어가는 전환 방식
 - 효과음과 음악 무드

내 대본은 다음과 같습니다:
 [여기에 내 대본을 붙여넣으세요]
```

#### 🇺🇸 영어 원본 버전

```
I'm attaching a reference video and my script below.
I want to recreate this video's STYLE for my own
script using an AI video generator (Gemini Omni / Veo).

Step 1: Analyze the reference video deeply. Describe:
 - Animation style (2D, 3D, kinetic typography, flat design)
 - How things move (speed, easing, bounce, smooth or snappy)
 - Transitions (cuts, wipes, morphs, zooms)
 - Color palette (exact colors and background)
 - Typography style (bold, thin, animated, where text appears)
 - Camera behavior (static, zoom, pan, shake)
 - Overall mood and pacing (fast, calm, dramatic)
 - Sound feel (whooshes, clicks, bass hits, music style)

Step 2: Break my script into scenes of 8-10 seconds
each (because the AI generates max 10 seconds per clip).

Step 3: For EACH scene, write one detailed prompt that includes:
 - What appears on screen and how it animates
 - The exact text shown on screen (max 5-6 words)
 - Colors, background, and typography matching the reference
 - Camera movement
 - Transition into the next scene
 - Sound effects and music mood

Here is my script:
 [PASTE YOUR SCRIPT HERE]
```

> ✍️ **팁:** 씬 프롬프트는 영어로 작성하면 Gemini Omni 결과물 품질이 더 좋습니다. 한글 자막·텍스트는 나중에 CapCut에서 따로 얹는 걸 추천합니다.

---

### 3️⃣ Claude에게 씬별 프롬프트 받기

**씬 하나당 프롬프트 하나, 복사만 하면 끝**

Claude가 내 대본을 씬 단위로 쪼개고, 씬마다 상세 프롬프트를 작성해 줍니다.
각 씬은 **8~10초** — Gemini Omni가 한 번에 생성할 수 있는 최대 길이입니다.

| 씬 | 역할 | 구간 | 핵심 효과 |
| --- | --- | --- | --- |
| **SCENE 1** | 훅 / 위기감 | 0 – 8초 | 굵은 텍스트 · 베이스 히트 |
| **SCENE 2** | 증거 / 반전 | 8 – 17초 | 글리치 효과 · 줌 펀치 |
| **SCENE 3** | 핵심 설명 | 17 – 25초 | 스티커 · 페이퍼 슬랩 |
| **SCENE 4** | CTA (행동 유도) | 25 – 35초 | 스핀 효과 · 환호 사운드 |

---

### 4️⃣ Gemini Omni에서 영상 생성

**한 번에 씬 하나씩**

Gemini 앱을 열고 영상 모델을 선택합니다 — **Gemini Omni Flash**가 최신 모델입니다.
씬 프롬프트 하나를 붙여넣고, 레퍼런스 영상을 첨부한 뒤 생성 버튼을 누르세요.
씬마다 이 과정을 반복합니다.

> ⚠️ **꿀팁 (중요!)**
> 생성할 때마다 **반드시 레퍼런스 영상이나 원본 클립을 첨부**하세요.
> 첨부하지 않으면 Omni가 내 스타일을 따라 하는 게 아니라 **자기 마음대로 스타일을 만들어 버립니다.**

---

### 5️⃣ 채팅으로 수정하기

**어색한 부분은 그냥 말로 고치세요**

씬이 마음에 안 들면 Gemini 채팅창에 그냥 말하면 됩니다.
해당 씬을 다시 만들어 주니, 씬마다 가장 잘 나온 버전만 남기세요.

> 💬 **수정 명령 예시** (한국어 / 영어 원본)
> - “텍스트 더 크게 해줘” / *“Make the text bigger”*
> - “애니메이션 속도 느리게 해줘” / *“Slow down the animation”*
> - “배경색을 빨간색으로 바꿔줘” / *“Change the background color to red”*
> - “전환할 때 글리치 효과 더 강하게” / *“Add more glitch effect on the transition”*
> - “텍스트가 더 강하게 쾅 들어오게 해줘” / *“Make the text slam in harder”*

---

### 6️⃣ CapCut에서 최종 조립

**음악, 내레이션 넣고 내보내기**

생성한 씬들을 모두 CapCut(또는 다른 편집기)에 넣고 순서대로 배치한 뒤,
음악이나 내레이션을 추가하고 내보내면 완성입니다. 🎉

> ⚠️ **중요:** 화면 속 텍스트가 깨지거나 어색하다면, 그 텍스트는 **CapCut이나 Figma에서 직접 다시 입력**하세요.
> AI는 아직 텍스트를 완벽하게 깔끔히 그리지 못합니다 — **업로드 전에 반드시 한 번 더 확인!**

---

### ✅ 최종 체크리스트

- [ ] 레퍼런스 영상 1~2개 저장 완료

- [ ] 내 대본 준비 완료

- [ ] Claude로 스타일 분석 & 씬별 프롬프트 생성

- [ ] Gemini Omni에서 씬별 영상 생성 (레퍼런스 첨부 필수!)

- [ ] 어색한 씬은 채팅으로 수정

- [ ] CapCut에서 조립 + 음악/내레이션 추가

- [ ] 화면 텍스트 최종 점검 후 업로드

---

한번에 뚝딱 완성되지 않습니다. 결과물이 마음에 들지 않으시면 계속 원하시는 방향으로 요청하시다 보면 멋진 완성작이 나올겁니다. 화이팅~😉😊

=================

[**🎁 10GB 이상 ‘콘텐츠 소스팩’ 무료로 다운받기 - 우주보스의 선물 보따리입니다!**](https://blog.naver.com/woojooboss/223558177937)
