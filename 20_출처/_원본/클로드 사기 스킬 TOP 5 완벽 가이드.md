---
title: "클로드 사기 스킬 TOP 5 완벽 가이드"
source: "https://neat-product-c0f.notion.site/TOP-5-39d19ffaaaf180c8beded1f14e30f010?fbclid=PAT01DUATFawNleHRuA2FlbQIxMABzcnRjBmFwcF9pZA81NjcwNjczNDMzNTI0MjcAAaekcY0IcnZj7BU7NZIZ78-mBt4IWIjRRYV7ecNeDlH0EcgggbtuXFDjby9qsg_aem_tkdC-OlIaiBEmAa6dOtC9w"
notion_page_id: "39d19ffa-aaf1-80c8-bede-d1f14e30f010"
archived_date: "2026-08-01"
---

# 클로드 사기 스킬 TOP 5 완벽 가이드

> **아무것도 몰라도 따라 할 수 있는 클로드 스킬 사용법**
> 
> 클로드를 쓰면서 스킬을 안 쓰면 반만 쓰는 겁니다. 이 5개만 설치해도 상위 1%가 됩니다.

---

### 🔽 먼저 이것부터: 스킬 받아서 적용하는 법 (30초)

스킬은 대부분 "깃허브(GitHub)"라는 사이트에 올라와 있습니다. 개발자들이 쓰는 사이트라 처음엔 낯설 수 있는데, 우리가 할 건 딱 두 가지뿐입니다. **내려받기, 올리기.**

**방법 A. 클로드 앱/웹 (코딩 몰라도 OK)**

1. 스킬의 깃허브 링크 접속 → 오른쪽 위 초록색 **[ Code ]** 버튼 → **Download ZIP**

1. 클로드(claude.ai) 접속 → 설정(Settings) → **기능(Capabilities)** → **스킬(Skills)**

1. **스킬 업로드** 버튼 누르고 받은 파일을 올리기

1. 끝. 이제 클로드가 필요할 때 알아서 꺼내 씁니다

**방법 B. 클로드 코드 (터미널 사용자, 더 쉬움)**

다운로드조차 필요 없습니다. 명령어 한 줄 복붙이면 자동으로 설치됩니다. 각 스킬 소개에 복붙용 명령어를 적어뒀어요.

> 💡 **적용됐는지 확인하는 법**
> 
> 설치 후 클로드에게 "지금 사용할 수 있는 스킬 목록 보여줘"라고 물어보세요. 목록에 뜨면 성공. 클로드 코드는 설치 후 세션을 한 번 재시작해야 인식되는 경우가 있습니다. 스킬이 자동 발동 안 하면 "OO 스킬 써서 해줘"라고 직접 언급하면 됩니다.

---

### 1. 스킬이 뭔가요?

스킬은 한마디로 **클로드에게 꽂는 전문가 칩**입니다.

평소에 클로드를 쓸 때 이런 경험 있으시죠?

- 매번 "이런 말투로 써줘", "이 형식 지켜줘"를 처음부터 다시 설명

- 어제 하던 작업을 오늘 이어서 하려면 또 처음부터 설명

- 영상이나 디자인을 시키면 어딘가 어색한 "AI 티" 나는 결과물

스킬은 이런 지시사항과 전문 지식을 **파일로 만들어 클로드에 설치**해두는 기능입니다. 한 번 설치하면 클로드가 필요할 때 알아서 꺼내 씁니다.

- 커뮤니티에 공개된 스킬만 **수만 개**, 대부분 무료입니다

- 클로드 유료 플랜(Pro 이상)과 클로드 코드에서 사용 가능합니다

---

### 2. TOP 5 스킬 소개

#### ① Remotion — 프롬프트 한 줄로 영상을 만드는 스킬

**어떤 스킬인가요?**
주제만 던지면 클로드가 대본을 쓰고, 장면을 짜고, 모션그래픽 애니메이션까지 만들어 **완성된 MP4 영상**으로 렌더링해줍니다. 영상 편집 프로그램이 필요 없습니다. 올해 1월 공개 데모가 X에서 **조회수 600만**을 넘기고 첫 주에만 2.5만 명이 설치하며 스킬 마켓 1위를 찍었습니다.

**이런 분에게 최고**
릴스/쇼츠 만드는 크리에이터, 제품 소개 영상이 필요한 사장님. 세로(9:16), 가로(16:9) 모두 지원하고, 무료로 내 컴퓨터에서 돌아갑니다.

**활용 예시**

- "AI 에이전트가 뭔지 설명하는 30초 세로 영상 만들어줘"

- "우리 가게 구글 리뷰로 후기 영상 만들어줘" (별점 애니메이션까지)

- "이 CSV 데이터로 움직이는 차트 영상 만들어줘"

**설치 (클로드 코드에서 한 줄)**

```
npx skills add remotion-dev/skills
```

[remotion-best-practices.zip](attachment:623f7d31-51b8-4f01-be56-ac559902631d:remotion-best-practices.zip)

- 깃허브: [https://github.com/remotion-dev/skills](https://github.com/remotion-dev/skills)

- 공식 안내: [https://remotion.dev/docs/ai/claude-code](https://remotion.dev/docs/ai/claude-code)

- 팁: 만든 뒤 "Remotion Studio 열어줘"라고 하면 브라우저에서 미리보기가 됩니다

---

#### ② Claude Mem — 대화가 끝나도 기억하는 스킬

**어떤 스킬인가요?**
클로드는 원래 대화(세션)가 끝나면 내용을 전부 잊습니다. 이 스킬은 작업 내용을 자동으로 요약해 저장해뒀다가, 다음에 클로드를 켜면 알아서 불러옵니다. "어제 하던 그 작업 이어서 해줘"가 진짜로 통하게 됩니다.

**이런 분에게 최고**
클로드 코드로 프로젝트를 진행하는 분. 매번 프로젝트 구조를 다시 설명하는 게 지겨운 분.

**실사용 후기 (해외 리뷰)**
한 사용자가 몇 주간 써본 결과, 259번의 세션에서 **6,814개의 기억**이 자동으로 쌓였고, 프로젝트 10개를 커버하는데 전부 노트북 속 39MB 파일 하나에 담겼습니다. "어제 같이 고친 버그를 오늘 클로드가 기억 못 하던 문제가 사라졌다"는 평.

**설치**

- 공식 문서: [https://docs.claude-mem.ai/introduction](https://docs.claude-mem.ai/introduction)

- 깃허브: [https://github.com/thedotmack/claude-mem](https://github.com/thedotmack/claude-mem)

- 클로드 코드 전용 플러그인입니다. 문서의 설치 명령어 한 줄이면 끝나요

- 자세한 설치 가이드(영문): [https://www.datacamp.com/tutorial/claude-mem-guide](https://www.datacamp.com/tutorial/claude-mem-guide)

---

#### ③ UI/UX Pro Max — 디자인 두뇌를 이식하는 스킬

**어떤 스킬인가요?**
클로드에게 UI 스타일 67종, 컬러 팔레트 161종, 폰트 조합 57종, UX 규칙 99개를 통째로 심어줍니다. AI가 만든 웹사이트 특유의 "보라색 그라데이션 + 어색한 레이아웃"에서 벗어나, 진짜 디자이너가 만든 것 같은 결과물이 나옵니다.

**이런 분에게 최고**
홈페이지, 랜딩페이지, 앱 화면을 만들고 싶은데 디자이너가 아닌 분.

**결과물 직접 확인하기 (강력 추천)**
말보다 눈으로 보는 게 빠릅니다. 이 스킬로 만든 실제 사이트들:

- 명품 쇼핑몰 데모: [https://ui-ux-pro-max-skill.nextlevelbuilder.io/demo/luxury-ecommerce](https://ui-ux-pro-max-skill.nextlevelbuilder.io/demo/luxury-ecommerce)

- 핀테크 대시보드 데모: [https://ui-ux-pro-max-skill.nextlevelbuilder.io/demo/fintech-crypto-dashboard](https://ui-ux-pro-max-skill.nextlevelbuilder.io/demo/fintech-crypto-dashboard)

**설치 (클로드 코드에서 두 줄)**

```
/plugin marketplace add nextlevelbuilder/ui-ux-pro-max-skill
/plugin install ui-ux-pro-max@ui-ux-pro-max-skill
```

- 깃허브: [https://github.com/nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)

- 공식 사이트: [https://ui-ux-pro-max-skill.com](https://ui-ux-pro-max-skill.com)

---

#### ④ Marketing Skills — 설치하면 마케터가 되는 스킬 팩

**어떤 스킬인가요?**
카피라이팅, SEO 감사, 랜딩페이지 진단(CRO), 이메일 시퀀스, 분석, 광고까지 **마케팅 전 영역의 스킬 40여 종이 한 번에** 설치되는 팩입니다. 마케팅 커뮤니티 Swipe Files 운영자 Corey Haines가 만들었고, 현재 가장 많이 설치되는 마케팅 스킬 팩입니다.

**이런 분에게 최고**
마케터 없이 혼자 다 하는 사장님, 1인 브랜드 운영자. 스킬을 따로 부를 필요 없이 "랜딩페이지 진단해줘"라고 하면 알아서 맞는 스킬이 발동됩니다.

**활용 예시**

- "우리 랜딩페이지 진단하고 전환율 높일 개선안 줘" → CRO 스킬 자동 발동

- "신제품 출시 이메일 시퀀스 5통 짜줘" → 이메일 스킬 자동 발동

- "우리 사이트 SEO 분석해줘" → SEO 스킬 자동 발동

**설치 (클로드 코드에서 한 줄)**

```
npx skills add coreyhaines31/marketingskills
```

- 깃허브: [https://github.com/coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills)

- 공식 사이트 (스킬 전체 목록): [https://marketing-skills.com](https://marketing-skills.com)

- 클로드 앱만 쓰는 분: 깃허브에서 필요한 스킬 폴더 하나만 ZIP으로 받아 업로드해도 됩니다 (copywriting이나 cro부터 추천)

---

#### ⑤ Superpowers — 클로드 활용의 끝판왕

**어떤 스킬인가요?**
아이디어 하나를 던지면 클로드가 질문을 던져 기획을 다듬고 → 작업을 잘게 쪼개고 → 하나씩 실행하고 → 결과를 **스스로 검증**까지 하는 풀코스 작업 프레임워크입니다. 커뮤니티 스킬 최대 규모로 깃허브 별 **4.1만 개**, 설치 12만 회를 넘겼고, 유명 개발자 Simon Willison이 공개 추천했습니다.

**이런 분에게 최고**
"대충 시키면 대충 나온다"에 지친 분. 복잡한 프로젝트를 통째로 맡기고 싶은 분. 클로드 코드 사용자라면 한 번은 거쳐 가는 스킬입니다.

**활용 예시**

- "포트폴리오 사이트 만들고 싶어" → 클로드가 먼저 질문으로 요구사항을 정리한 뒤 계획을 세우고 실행

- 큰 작업을 시켰을 때 중간에 산으로 가는 일이 확 줄어듭니다

**설치 (클로드 코드, 공식 마켓플레이스)**

```
/plugin install superpowers@claude-plugins-official
```

- 깃허브: [https://github.com/obra/superpowers](https://github.com/obra/superpowers)

- 설치 후 /superpowers:brainstorm 같은 새 명령어가 생깁니다. 평소처럼 대화해도 자동 발동돼요

---

### 3. 추천 설치 순서

처음이라면 이 순서를 추천합니다.

1. **Remotion부터** → 효과가 제일 화려해서 "스킬이 뭔지" 몸으로 이해됨

1. **Marketing Skills** → 글/마케팅 업무에서 바로 체감

1. **UI/UX Pro Max** → 홈페이지나 앱 화면 만들 때

1. **Claude Mem** → 클로드 코드로 프로젝트를 굴리기 시작하면 그때

1. **Superpowers** → 클로드 코드에 익숙해진 뒤 마지막에 (초보 단계에선 과할 수 있어요)

---

### 4. 자주 묻는 질문 (FAQ)

**Q. 전부 무료인가요?**
네, 5개 모두 무료 오픈소스입니다. 단, 스킬 기능 자체는 클로드 유료 플랜(Pro 이상)에서 사용할 수 있습니다.

**Q. 코딩을 전혀 몰라도 되나요?**
네. 명령어라고 해봐야 이 가이드의 한 줄을 복사해서 붙여넣는 게 전부입니다. 클로드 앱만 쓰는 분은 ZIP 업로드 방식(방법 A)으로 하면 터미널을 열 일도 없습니다.

**Q. 스킬을 설치했는데 클로드가 안 쓰는 것 같아요.**
스킬은 클로드가 "필요하다고 판단할 때" 자동 발동됩니다. 잘 안 되면 "OO 스킬을 사용해서 해줘"라고 직접 언급해보세요. 클로드 코드는 설치 후 세션 재시작도 한 번 해주세요. 대부분 해결됩니다.

**Q. 스킬을 여러 개 설치하면 충돌하지 않나요?**
클로드는 작업에 맞는 스킬만 골라서 불러오기 때문에 여러 개를 설치해도 괜찮습니다. 오히려 조합될 때(예: ④로 마케팅 기획하고 ①로 홍보 영상 제작) 시너지가 납니다.

---

> 📌 **이 가이드가 도움이 됐다면**
> 
> 인스타그램 **@moodmode.ai** 를 팔로우하세요.
> 매주 새로운 AI 정보를 가장 빠르게 전해드립니다.
