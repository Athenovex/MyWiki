---
id: kb-faiss
type: tool
status: canonical
aliases: ["Facebook AI Similarity Search"]
domains: ["AI", "development"]
related: ["[[임베딩]]", "[[LangChain]]", "[[RAG]]"]
sources: ["[[동국대_교육자료1]]", "[[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]]"]
created: 2026-08-15
updated: 2026-08-16
---

# FAISS

> LangChain 기준, 문서의 임베딩 벡터와 원본 텍스트를 저장하고 유사도 검색을 수행하는 벡터 데이터베이스 라이브러리.

## 개요

FAISS(Facebook AI Similarity Search)는 Meta(구 Facebook)가 개발한 오픈소스 벡터 유사도 검색 라이브러리로, 대량의 벡터 중에서 질문 벡터와 가장 가까운 벡터들을 빠르게 찾아준다. [[LangChain]]에서는 `FAISS.from_documents()`를 실행하면 문서 조각들이 임베딩되어 FAISS 벡터 DB 안에 저장되는데, 이때 내부적으로 3가지(+연결 정보)가 함께 저장된다.

## 저장 구조

출처 자료의 "FAISS 벡터 DB에는 무엇이 저장될까? (LangChain 기준)" 다이어그램에 실린 과정과 표를 그대로 옮긴 것이다. 문서(Document 객체, `page_content` + `metadata`)를 임베딩 모델(다이어그램 예시: **OpenAI Embeddings, `text-embedding-ada-002`**)로 벡터화한 뒤, `FAISS.from_documents()`를 실행하면 다음 3가지(+연결 정보)가 저장된다.

**① FAISS Index** — 벡터(임베딩) 저장소: 의미 검색을 위한 벡터들이 ID별로 저장되는 인덱스. 실제 유사도 계산·검색이 일어나는 핵심 구조다.

| ID | 임베딩 벡터 |
|---|---|
| 0 | [0.123, -0.456, ..., 0.789] |
| 1 | [-0.111, 0.234, ..., -0.321] |
| 2 | [0.987, -0.654, ..., 0.111] |

**② DocStore** — 원본 텍스트(page_content) + metadata 저장소: 검색 후 사람이 읽을 원문을 보여주고 출처 정보를 제공하기 위해 벡터와 별도로 저장한다.

| ID | page_content (원본 텍스트) | metadata (참조 정보) |
|---|---|---|
| doc_0 | "문서 내용 ..." | {"source": "a.pdf", "page": 1} |
| doc_1 | "문서 내용 ..." | {"source": "a.pdf", "page": 2} |
| doc_2 | "문서 내용 ..." | {"source": "b.pdf", "page": 5} |

**③ index_to_docstore_id** — 연결 정보: FAISS Index의 벡터(ID)와 DocStore의 문서(ID)를 연결하는 매핑. 벡터 검색 결과를 사람이 읽을 수 있는 원문으로 되돌리는 다리 역할을 한다.

| FAISS Index ID (벡터) | DocStore ID (문서) |
|---|---|
| 0 | doc_0 |
| 1 | doc_1 |
| 2 | doc_2 |

출처 자료의 "정리" 요약: ① page_content → 임베딩 벡터 생성 후 FAISS Index에 저장 ② 원본 텍스트(page_content)도 DocStore에 저장 ③ metadata(출처, 페이지 번호 등)도 DocStore에 저장 ④ 벡터(ID)와 문서(ID)를 연결하는 매핑 정보(index_to_docstore_id) 저장. 핵심은 "page_content(텍스트)를 숫자 벡터로 변환하여 의미를 컴퓨터가 이해할 수 있도록 만드는" 것이다.

## 검색 시 흐름

사용자 질문이 들어오면 FAISS는 다음 순서로 원문을 찾아 돌려준다: 질문을 [[임베딩]]으로 변환 → FAISS Index에서 유사한 벡터(ID)를 검색 → index_to_docstore_id를 통해 그 벡터에 대응하는 DocStore 문서 ID를 조회 → DocStore에서 원본 문서(원문+metadata)를 가져와 반환. 이 과정 덕분에 사용자는 벡터가 아니라 사람이 읽을 수 있는 문서와 출처 정보를 답으로 받는다.

아래는 출처 자료의 "검색 시 흐름" 다이어그램과 `similarity_search()` 결과 예시를 그대로 옮긴 것이다.

```
사용자 질문: "OOO에 대해 알려줘"
  → 질문을 임베딩 → FAISS Index에서 유사한 벡터(ID) 검색
  → index_to_docstore_id를 통해 DocStore에서 원본 문서 가져오기
  → 검색 결과 반환:
    Document(
      page_content: "...",
      metadata: {"source": "a.pdf", "page": 1}
    )

예시: similarity_search() 결과
  Document(
    page_content="문서 내용 ...",
    metadata={"source": "a.pdf", "page": 1}
  )
  → 원문 + metadata 반환!
```

## FAISS와 다른 벡터 데이터베이스 비교

출처 자료에는 없는 내용이지만, 벡터 DB를 선택할 때 자주 함께 비교되는 대안이라 일반적으로 알려진 내용을 바탕으로 위키 편집 과정에서 추가한다.

| 이름 | 특징 |
|---|---|
| FAISS | Meta가 개발한 오픈소스 라이브러리. 로컬에서 직접 실행하며 별도 서버가 필요 없고, 대규모 벡터의 고속 유사도 검색에 특화 |
| Pinecone | 완전관리형(매니지드) 클라우드 벡터 DB. 서버 운영 부담이 없다 |
| Chroma | 오픈소스, 로컬 개발·프로토타이핑에 간편하게 쓸 수 있다 |
| Milvus / Weaviate | 오픈소스 분산 벡터 DB. 대규모 프로덕션 환경에 적합 |

FAISS는 그 자체로는 "라이브러리"이지 완결된 데이터베이스 서버가 아니다. 그래서 메타데이터 영속성, 다중 사용자 동시 접근, 클러스터링 같은 기능은 직접 구현하거나 [[LangChain]] 같은 프레임워크의 래퍼(wrapper)에 의존해야 한다는 제약이 있다.

## 관련 지식

- [[임베딩]] — FAISS가 저장·검색하는 벡터의 생성 방식
- [[LangChain]] — FAISS를 벡터 DB로 활용하는 대표적 프레임워크
- [[RAG]] — FAISS는 RAG 파이프라인의 검색 단계를 구현하는 데 쓰인다

## 출처

- [[동국대_교육자료1]] p.14 "FAISS 벡터 DB에는 무엇이 저장될까? (LangChain 기준)"
- [[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]] p.11 (동일 내용)
