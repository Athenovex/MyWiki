---
id: kb-streamlit
type: tool
status: canonical
aliases: []
domains: ["development"]
related: ["[[Cloud Run]]"]
sources: ["[[동국대_교육자료1]]", "[[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]]"]
created: 2026-08-15
updated: 2026-08-15
---

# Streamlit

> Python만으로 데이터 앱(웹 애플리케이션)을 쉽고 빠르게 만들 수 있는 오픈소스 프레임워크.

## 주요 특징

- Python 기반: Python 스크립트만으로 웹 앱 개발
- 빠른 개발: 코드 변경 시 자동으로 앱 새로고침
- 풍부한 구성 요소: 데이터 표시·차트·테이블·입력 폼 등 위젯 제공
- 손쉬운 배포: 몇 번의 명령으로 웹 앱 배포
- 오픈소스 & 커뮤니티

## 작동 원리

Python 코드 작성(.py) → 실시간 실행(코드 실행 시 앱 자동 렌더링) → 웹 브라우저 표시(인터랙티브 웹 앱 제공) → 상호작용&업데이트(사용자 입력에 따라 동적 업데이트)

## 활용 분야

데이터 분석 대시보드, 머신러닝 모델 시연, 내부 도구&자동화, 교육&학습, 빠른 프로토타이핑.

## 배포

`streamlit run app.py`(로컬 실행) → `streamlit share app.py`(공유) → Streamlit Community Cloud 또는 클라우드에 배포 → 공유 가능한 URL로 누구나 접속.

## 관련 지식

- [[Cloud Run]] — Streamlit으로 만든 앱을 컨테이너화해 배포하는 대상 플랫폼 중 하나

## 출처

- [[동국대_교육자료1]] p.16 "Streamlit 이란?"
- [[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]] p.13 (동일 다이어그램)
