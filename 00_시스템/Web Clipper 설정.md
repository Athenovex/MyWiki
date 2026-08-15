---
title: Web Clipper 설정
---

# Web Clipper 설정

Obsidian Web Clipper(Chrome 확장)로 수집한 자료의 저장 규칙.

## 역할

Web Clipper의 역할은 **수집**뿐이다. 클리핑 단계에서 과도한 AI 요약·분류·지식 병합을 수행하지 않는다. 위키 반영은 Wiki Curator가 `01_수집`을 처리할 때 수행한다.

## 저장 위치

```
01_수집
```

## Frontmatter Template

Web Clipper 확장 설정의 Template에 다음을 등록한다.

```yaml
---
type: source
source_type: web
status: inbox
url: "{{url}}"
site: "{{site}}"
author: "{{author}}"
published: "{{published}}"
collected: "{{date}}"
processed: false
target_notes:
---
```

본문은 Web Clipper 기본 Markdown 변환 그대로 저장한다 (Highlighter/Reader 모드 등 과도한 가공 불필요).

## 사용자가 한 번 설정할 것

1. Obsidian Web Clipper 확장을 Chrome에 설치
2. 확장 설정 → Vault: 이 Vault(`MyWiki`) 지정
3. 확장 설정 → 저장 경로: `01_수집` 지정
4. 확장 설정 → Template: 위 Frontmatter 등록
5. 파일명 규칙: 페이지 제목 기반 (기본값 사용 가능)

## 처리 흐름

```
웹서핑 → 유용한 자료 발견 → Web Clipper로 저장(01_수집) → 끝
```

이후 사용자가 "위키 정리해줘"라고 하면 Wiki Curator가 `01_수집`의 웹 자료를 [[자료 처리규칙]]에 따라 처리한다.

## 관련 문서

[[자료 처리규칙]] · [[지식 스키마]]
