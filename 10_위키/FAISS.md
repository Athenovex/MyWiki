---
id: kb-faiss
type: tool
status: canonical
aliases: ["Facebook AI Similarity Search"]
domains: ["AI", "development"]
related: ["[[임베딩]]", "[[LangChain]]", "[[RAG]]"]
sources: ["[[동국대_교육자료1]]"]
created: 2026-08-15
updated: 2026-08-15
---

# FAISS

> LangChain 기준, 문서의 임베딩 벡터와 원본 텍스트를 저장하고 유사도 검색을 수행하는 벡터 데이터베이스 라이브러리.

## 개요

`FAISS.from_documents()` 실행 후 FAISS 벡터 DB 내부에는 3가지(+연결 정보)가 저장된다.

## 저장 구조

1. **FAISS Index** — 벡터(임베딩) 저장소: 의미 검색을 위한 벡터들이 ID별로 저장되는 인덱스
2. **DocStore** — 원본 텍스트(page_content) + metadata 저장소: 검색 후 원문을 보여주고 출처 정보를 제공하기 위해 저장 (예: `{"source": "a.pdf", "page": 1}`)
3. **index_to_docstore_id** — 연결 정보: FAISS Index의 벡터(ID)와 DocStore의 문서(ID)를 연결하는 매핑

## 검색 시 흐름

사용자 질문 → 질문을 임베딩 → FAISS Index에서 유사한 벡터(ID) 검색 → index_to_docstore_id를 통해 DocStore에서 원본 문서 가져오기 → 검색 결과(원문 + metadata) 반환

## 관련 지식

- [[임베딩]] — FAISS가 저장·검색하는 벡터의 생성 방식
- [[LangChain]] — FAISS를 벡터 DB로 활용하는 대표적 프레임워크
- [[RAG]] — FAISS는 RAG 파이프라인의 검색 단계를 구현하는 데 쓰인다

## 출처

- [[동국대_교육자료1]] p.13 "FAISS 벡터 DB에는 무엇이 저장될까? (LangChain 기준)"
