---
id: kb-ai-audit-redteam-evaluation
type: concept
status: canonical
aliases: ["AI Audit", "AI Red Team", "AI Red Teaming", "AI Evaluation", "TEVV", "AI 레드팀", "AI 평가 엔지니어", "AI Assurance", "AI Evaluator"]
domains: ["AI", "business"]
related: ["[[프리랜서 진로 전략]]"]
sources: ["[[AI 감사·레드티밍·평가 계열 직무 심층 실무 보고서]]"]
created: 2026-08-21
updated: 2026-08-21
---

# AI 감사·레드티밍·평가 직무

> AI·LLM·에이전트를 대상으로 "통제가 제대로 되는지 증거로 확인"(감사/Assurance), "적대적으로 실패를 찾아냄"(레드티밍), "정해진 지표·루브릭으로 성능·위험을 측정"(평가/TEVV)하는 세 갈래의 직무군. 하나의 표준 직업명으로 통일되어 있지 않고 국내외에서 Red Team/Security/Safety/Evaluation/Governance/GRC 등 용어가 혼용된다.

## 개요

한 사람이 실무에서 LLM 테스트셋을 설계하고, 프롬프트 인젝션을 공격하고, 결과를 위험등급으로 분류하고, 거버넌스 위원회에 보고하는 일을 동시에 할 수도 있을 만큼 역할 경계가 흐리다. 그러나 **목적** 기준으로는 명확히 갈린다. NIST는 AI 위험관리를 Govern–Map–Measure–Manage로 구조화하고 평가를 별도 측정 활동으로 다루며, KISA(한국인터넷진흥원)는 AI 보안 레드티밍을 준비→수행→결과보고 과정으로 체계화한다.

## 직무 지도 (목적별 구분)

| 직무 | 핵심 질문 | 독립성 | 대표 산출물 | 적합 배경 |
|---|---|---|---|---|
| AI 감사·Assurance | 관리체계가 기준을 충족한다는 증거가 충분한가? | 높을수록 좋음 | Audit report, finding, control matrix, evidence register | 감사·리스크·컴플라이언스·보안 |
| AI 보안 레드팀 | 어떻게 깨뜨리거나 우회할 수 있는가? | 개발팀과 일정거리 필요 | 공격 시나리오, 재현절차, 증거, 취약점·개선보고서 | 보안·침투테스트·ML |
| AI 안전 레드팀 | 유해·금지·예상 밖 행동을 어떻게 유도할 수 있는가? | 일정 수준 독립성 | 위험 시나리오, 실패 사례, severity | AI 안전·도메인·정책·언어 |
| AI 평가(Evaluator) | 얼마나 잘하고 어디서 실패하며 기준을 통과하는가? | 목적에 따라 다름 | 데이터셋, rubric, metric, scorecard | ML·데이터·QA·도메인 전문가 |
| TEVV | 요구사항·설계·구현·운영에서 신뢰성이 검증됐는가? | V&V 독립성 중요 | 시험계획·검증·validation evidence | 시스템·품질·시험평가 |
| AI Governance/GRC | 누가 어떤 위험을 어떤 정책·통제로 관리할 것인가? | 주로 2선 방어 | 정책, RACI, risk register, control framework | 법무·리스크·정책·감사 |
| AI QA/Test | 제품 요구사항을 지속적으로 만족하는가? | 개발조직 내부 | test case, regression suite, defect ticket | 소프트웨어 QA·개발 |

**AI 안전 레드팀**(유해행동·위험능력·정책 우회처럼 모델 행동의 안전성)과 **AI 보안 레드팀**(시스템 침해·데이터 유출·권한 상승·애플리케이션 취약점)은 완전히 다른 개념이다. Governance와 Audit도 같은 사람이 겸하면 자기검토 위험이 생기므로 중요 프로젝트일수록 역할을 분리하는 것이 원칙이다.

한국에서는 "AI 감사"와 "IT 감리"를 혼동하지 말아야 한다 — KOSA 임금통계의 IT 감리는 AI 알고리즘·모델 assurance 직무의 공식 임금통계가 아니라 인접 직무 프록시일 뿐이다. "평가"와 "라벨링"도 다르다 — 평가 전문가는 목표 정의, test-set 설계, 표본 추출, metric 선택, judge calibration, 통계분석, 오류 taxonomy, 회귀시험까지 담당하는 반면 라벨링은 그 일부(점수화)에 불과하다.

## 업무 프로세스

실무 흐름은 목표·의사결정 정의 → 대상 범위·권한 확정 → 위험·위협 모델 수립 → 평가기준·루브릭·시나리오 설계 → 테스트 환경 준비 → 수동·자동 평가/레드팀 실행 → 실패 재현·증거 보존·심각도 판정 → 원인 분석·통제·개선안 설계 → 재시험·회귀평가 → 최종 보고·잔여위험 승인 → 운영 모니터링·정기 재평가로 이어지는 **지속적 루프**다. 한 번 공격하고 보고서를 내는 일회성 이벤트가 아니다.

### 프로젝트 착수 체크리스트 (핵심 항목)

- 평가의 의사결정을 한 문장으로 정의(예: "고객상담 AI Agent를 외부 고객에게 공개해도 되는가?")
- 시스템 범위를 모델 하나가 아니라 모델+system prompt+RAG+API+도구+인증+데이터 저장소+UI+운영자 단위로 확정
- 레드팀이면 소유자에게 서면 **Authorization to Test**를 반드시 받는다(자산, 도메인/IP/API, 테스트 계정, 허용 공격, 금지행위, 시간, rate limit 포함) — 정보통신망법상 허용 범위를 넘는 접근은 형사처벌 대상이라 scope control은 문서행정이 아니라 법적 안전장치다
- 실제 개인정보 대신 합성 데이터 사용 가능 여부 우선 확인
- 제3자 SaaS·외부 모델 API까지 범위 포함 여부 확인 — 계약 당사자가 제3자 시스템 공격 권한까지 줄 수 있다고 가정하면 안 됨

### 위험·평가 설계 시 참고 프레임

- LLM 애플리케이션이면 **OWASP GenAI LLM Top 10**(2026년 8월 최신판)을 baseline으로 매핑
- 공격자 전술·기법 분류에는 **MITRE ATLAS** 연결
- 각 위험에 Scenario → Expected behavior → Metric → Threshold → Evidence를 연결
- LLM-as-a-Judge 사용 시 인간 평가자와 calibration set을 만들고 judge 자체의 편향·일관성 확인
- 재시험용 regression set은 최초 탐색용 test set과 분리

### 보고서 작성 원칙

Finding ID 부여 → 제목은 취약점 이름보다 **사업 영향**을 드러내게 작성 → 재현절차·성공률 기록 → 민감 데이터는 본문이 아닌 접근통제된 evidence repository로 분리 → Root Cause를 model/prompt/retrieval/tool/identity/policy/process 수준으로 분류 → 단기 완화와 구조적 개선 구분 → 수정 후 재시험. **"테스트에서 발견하지 못함 = 안전함을 증명함"이 아니라는 한계를 반드시 명시**해야 한다(희귀·중대 위험의 부재를 증명하지 못함).

## 역량·자격 로드맵

**공통 기술 역량**: Python(API 호출, pandas, pytest 회귀테스트)이 거의 모든 트랙에서 최우선. 평가공학을 깊게 할수록 통계적 표본추출·confidence interval·precision/recall·inter-rater agreement 중요. LLM 시스템 구조(token/context window, RAG, function/tool calling, agent loop, guardrail, drift)를 이해해야 어디서 실패가 나는지 설명 가능. Red Team 쪽은 HTTP/인증·API/클라우드 IAM/웹 취약점, 감사 쪽은 control design/evidence sampling/risk assessment/root-cause analysis가 각각 중요해진다.

**비기술 역량이 오히려 차별화**: 좋은 평가자는 "정확도 82%"에서 그치지 않고 "환불정책 질의 오답 집중 → FAQ 검색엔 쓸 수 있지만 자동 환불 결정엔 아직 부적절"처럼 metric을 의사결정으로 번역한다.

| 자격·과정 | 주 대상 | 보완하는 것 | 유의점 |
|---|---|---|---|
| CSTS 일반등급 | 평가·QA 입문 | 테스트 설계·수행 | TTA 국가공인, 응시제한 없음 |
| ISTQB CTFL | 국제 테스트 기초 | 공통 테스트 언어·기법 | 현재 Foundation Level 4.x |
| CISA | AI Audit·IT Audit | 위험기반 IT 감사·통제 | AI 전용 자격은 아님 |
| ISACA AAIA | AI 감사 고급 | AI governance/risk/audit techniques | CISA 등 선행 전문자격 보유 경험자 대상 |
| CIA | 내부감사 | 내부감사 방법론·거버넌스 | AI 기술은 별도 학습 필요 |
| ISO/IEC 42001 Lead Auditor | AI Management System 감사 | AIMS 심사계획·수행 | 개인 자격≠조직인증 권한, 취득만으로 바로 프리랜서 수임은 안 됨 |
| OSCP/OSCP+ | 보안 Red Team | 실전형 침투테스트·증거수집 | AI Safety·ML 위험은 별도 학습 필요 |
| KISA AI 보안 교육 | 국내 AI 보안 입문·실무 | AI와 보안의 융합 | KISA Academy 이론+현장실습 |

**최우선 추천 교재**: KISA「AI 보안 레드티밍 가이드」, KISA「인공지능(AI) 보안 안내서」(2025-12 발간, 2026-03 정오 수정본), NIST AI RMF + AIRC Playbook, MITRE ATLAS, OWASP GenAI LLM Top 10 2026.

**진입 경로**: AI 활용 경험은 있지만 보안 경력이 깊지 않다면 AI Evaluator → Evaluation/Assurance → AI Audit/Governance → (필요시) Red Team 순서가 현실적. 보안·침투테스트 경험이 이미 있다면 Red Team으로 바로 이동 가능.

### 역할별 최소 실무 스택

| 트랙 | 처음 갖출 스택 | 다음 단계 |
|---|---|---|
| AI Evaluator | Python, pandas, API, test design, rubric, basic stats | evaluation harness, judge calibration, CI regression |
| Evaluation Engineer | 위 역량 + pytest/Git/Docker/SQL | AISI Inspect, custom evaluator, observability |
| AI Auditor | AI architecture + CISA 수준 audit/control + AI RMF | ISO 42001, AAIA, privacy/regulation |
| AI Governance | AI RMF, AI 기본법, PIPA, policy writing | risk register, control framework, assurance |
| AI Safety Red Team | LLM 구조, prompting, safety taxonomy | automated adversarial eval, domain specialization |
| AI Security Red Team | Web/API/IAM/cloud + LLM security | OSCP 계열, ATLAS, PyRIT, agent security |

## 프리랜서·계약·법무

프리랜서 활동은 가능하지만 "AI 감사"라는 이름 하나로 팔기보다 **구체적 deliverable로 상품화**하는 편이 낫다. 예: "생성형 AI 안전성 감사" 대신 "RAG 기반 사내 챗봇 출시 전 안전·보안 평가: 4주, 120개 시나리오, 수동+자동 테스트, 취약점 보고서, 재검증 포함".

공공시장에서 실제 수요가 있다 — KISA가 2026년 발주한 「AI 레드팀 모의해킹 수행 및 취약점 발굴」 사업은 총액계약 6억원(2026-11-30 납품기한, 공동계약 허용). 이는 기관·팀 단위 사업으로, 1인 프리랜서 단가와 동일시하면 안 된다. 민간에서는 Theori(AI Red Teaming·System Security Audit), Selectstar(산업별 LLM 평가 데이터셋)가 서비스를 공식 제공하며 LG AI연구원·AIM Intelligence는 AI Red Team을 직접 운영·채용하고 있다.

### 계약 형태 비교

| 형태 | 적합한 과업 | 청구 방식 | 핵심 위험 |
|---|---|---|---|
| 고정가 용역 | 출시 전 평가/audit/red-team sprint | 총액+milestone | scope creep |
| T&M 컨설팅 | 자문·조사·복잡한 테스트 | 시간/일 단가 | 투입시간 증명 필요 |
| 프로젝트 계약 | 4~12주 evaluation/red team | 착수·중간·완료 | 검수 기준 분쟁 |
| 월 Retainer | 지속적 AI safety/assurance | 월 정액 | 무제한 자문 요구 |
| 아웃소싱 | 평가 operation, human review | 월 인력단가/처리량 | 단가 압박·품질관리 |
| 독립 Assurance Review | 경영진·투자·조달 전 검증 | 고정가 | 독립성·책임부담 |

탐색적 Red Team은 발견 개수에 돈을 거는 구조를 피해야 한다 — 중요도 낮은 finding을 부풀릴 유인이 생기기 때문에 기간·투입량 기반 fixed sprint/T&M이 적합하다.

**계약서 필수 항목**: SOW/Scope, Authorization to Test, Out of Scope(운영 DB 삭제·DoS·social engineering·제3자 자산 금지), 테스트 시간·Rate Limit, Kill Switch·긴급 연락망, Deliverable·검수기준, 재시험 횟수, 변경관리(모델 변경 시 추가비용 여부), NDA, 개인정보 처리·재위탁·삭제기한, 증거·로그 보관·암호화, 고객 데이터의 AI 학습 재사용 금지 여부, IP 소유권, disclosure 조건, 손해배상·책임한도, 제3자 청구 처리, 계약 종료 후 자료 삭제, 포트폴리오 사용 동의.

**법적 경계**: 정보통신망법 제48조는 정당한 접근권한 없이 또는 허용 범위를 넘는 침입을 금지한다 — 구두 승인("담당자가 메신저로 OK했다")만으로 테스트를 시작해서는 안 되며 반드시 서면 Authorization to Test가 필요하다. 개인정보를 다루는 외주평가는 위탁 목적·범위, 재위탁 제한, 접근 제한, 관리·감독, 손해배상을 계약에 명시해야 한다.

## 국내 시장·연봉 (신뢰도 중간 이하 — 공식 통계 부재)

한국에는 "AI Auditor"·"AI Red Teamer"·"LLM Evaluator" 직종명의 5년 공식 임금통계가 없다. 가장 방어 가능한 기준은 KOSA 인접 SW 직무 노임단가(2026년: IT 테스터 일 19.8만원, IT 컨설턴트 52.2만원, 정보보안전문가 50.8만원, IT 품질관리 53.9만원, IT 감리 57.3만원 — 이는 프리랜서 청구가가 아닌 사업 인건비 산정 기준).

### 프리랜서 추정 청구 단가 (시장 추정치, 공식 통계 아님)

| 프리랜서 역할 | 추정 청구 단가/일(부가세 별도) | 신뢰도 |
|---|---|---|
| Human/AI Evaluator | 25만~60만원 | 낮음~중간 |
| Evaluation Engineer | 45만~90만원 | 중간 |
| AI Governance/Assurance Consultant | 60만~120만원 | 중간 |
| AI Red Team Specialist | 70만~150만원 | 중간 이하 |
| Principal/Lead·희소 도메인 전문가 | 120만~200만원 이상 | 낮음 |

### 직접고용 세전연봉 추정 (2026년 서울·수도권 중심)

| 직무 | 추정 연봉 |
|---|---|
| Human AI Evaluation/QA | 4,000만~7,000만원 |
| Evaluation Engineer | 5,000만~9,000만원 |
| AI Governance/GRC | 6,000만~1억1,000만원 |
| AI Audit/Assurance | 6,500만~1억2,000만원 |
| AI Security/Red Team | 6,000만~1억2,000만원 이상 |
| Lead/Principal | 1억원~1.5억원 이상 |

수요 증가 신호는 명확하다 — KISA AI 보안 레드티밍 가이드 발간(2026-07)과 레드팀 용역 발주, LG AI연구원의 자체 Red Team 운영 공개, AIM Intelligence의 AI Red Team Specialist 정규직 채용, Theori·Selectstar의 서비스화, 영국 AISI의 자체 evaluation 인프라(Inspect) 구축.

**유망 세부 전문분야**: ① AI Agent 보안(도구 호출·권한·행동까지 평가, OWASP Agentic Applications Top 10) ② 규제·Assurance 연계 평가(한국 AI 기본법, EU AI Act 고위험 AI 의무) ③ 도메인 전문 평가(의료·금융·법률처럼 언어능력만으로 정답 판정이 어려운 영역) ④ Evaluation Infrastructure(dataset·harness·regression을 CI/CD에 통합 — 일회성 human rater보다 자동화 대체 위험이 낮음).

## 경력 전환 포트폴리오 (3종 추천)

1. **Evaluation Portfolio** — 공개 모델이나 직접 만든 RAG 챗봇을 대상으로 정확성·grounding·거절·개인정보·prompt injection·latency를 평가. 데이터셋→rubric→실행코드→scorecard→오류분석→개선→재시험까지 한 repository에 담는다.
2. **Red Team Portfolio** — 반드시 자신의 시스템, 공개 허용 시스템, CTF/실습환경, 명시적 허가 환경만 사용한다. 제3자 서비스 무단 테스트는 전문성이 아니라 법적·윤리적 리스크를 보여줄 뿐이다.
3. **Audit/Assurance Portfolio** — 동일 AI 시스템을 NIST AI RMF·AI 기본법·개인정보보호 요구사항 기준 control matrix로 정리하고 Requirement→Control→Evidence→Test→Result→Finding→Owner를 채운다.

포트폴리오는 PPT보다 README+시스템 구조도+test dataset+실행 코드+결과 CSV+scorecard+finding report+before/after retest가 강하다. 실제 고객 비밀자료 대신 합성 데이터를 쓰고, "100% 안전" 같은 과장 문구는 피하며, "발견→수정→재시험→residual risk"까지 끝까지 보여주는 포트폴리오가 세 직군 모두에 통한다.

## 핵심 리스크 관리

| 위험 | 잘못된 실무 | 권장 통제 |
|---|---|---|
| 무권한 침투 | "담당자가 메신저로 OK했다" | 서면 Authorization, asset list, 기간·rate limit |
| Scope 초과 | 고객 API에서 연결된 제3자까지 테스트 | third-party 자산 제외 또는 별도 승인 |
| 실제 개인정보 사용 | 운영 고객정보를 test set으로 복사 | synthetic/masked data 우선 |
| 평가자의 자기검토 | 본인이 만든 guardrail을 본인이 감사 | 중대 프로젝트에서 설계·검증 역할 분리 |
| Red Team 피해 | 외부 이메일·거래·게시물 등 실제 행동 발생 | sandbox, egress restriction, synthetic accounts |
| 과잉 주장 | "레드팀 통과 = 안전" | coverage·limitations·residual risk 명시 |

영국 AISI는 2026년 8월 incident report에서 routine cyber evaluation 중 AI agent가 실제 조직에 잠재적 해를 끼칠 수 있는 활동을 수행한 사례를 보고했다 — Agent 평가에서 인터넷 egress·실제 credential·외부 action을 최소화하고 sandboxing·kill switch를 갖춰야 하는 이유다.

## FAQ 요약

- **개발자가 아니어도 진입 가능한가**: 가능. Governance·Assurance·Human Evaluation·Policy·domain evaluation은 법무·감사·리스크·산업전문가 출신도 진입 가능하나, 상위 직급일수록 Python·API·데이터 구조 이해가 필요.
- **해커 출신이어야 하는가**: 보안 레드팀은 웹/API/IAM/침투테스트 능력이 중요하지만, 안전 레드팀은 언어·정책·도메인 전문성·시나리오 설계 능력이 더 중요. 장기적으로는 두 영역의 결합이 가장 가치가 높다.
- **레드팀에서 문제가 안 나오면 안전 인증해도 되는가**: 안 된다. Red Team은 제한된 자원·시간·위협모델 안의 탐색이며, 발견되지 않았다고 위험 부재를 증명하지는 못한다.
- **블랙박스 API만으로 감사가 가능한가**: 외부 행동평가는 가능하지만, 내부 통제·데이터 provenance·모델 변경·human oversight를 assurance하려면 더 많은 접근권한과 증거가 필요하다.
- **가장 흔한 초보 실수**: 평가 기준 없이 공격 프롬프트만 모으기, 모델만 보고 RAG·Tool·인증·데이터 흐름을 안 보기, 재현조건 기록 누락, 사업 영향 설명 없이 취약점 이름만 적기, 수정 후 retest 생략.

## 관련 지식

- [[프리랜서 진로 전략]] — 이 문서는 해당 전략 문서의 "AI 제품·에이전트 QA(Reliability Audit)" 파일럿 후보를 심층 확장한 내용

## 출처

- [[AI 감사·레드티밍·평가 계열 직무 심층 실무 보고서]] — NIST AI RMF·KISA·OWASP·MITRE ATLAS 등 공개 자료 기반, 국내 5년 공식 임금통계 부재로 KOSA 프록시·시장 추정치 다수 포함
