---
id: kb-langchain
type: tool
status: canonical
aliases: ["랭체인"]
domains: ["AI", "development"]
related: ["[[RAG]]", "[[FAISS]]", "[[임베딩]]"]
sources: ["[[동국대_교육자료1]]", "[[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]]"]
created: 2026-08-15
updated: 2026-08-16
---

# LangChain

> RAG 파이프라인의 각 단계를 연결하고 관리하여, 질문에 대한 정확하고 신뢰할 수 있는 답변을 생성하도록 돕는 오픈소스 프레임워크.

## 개요

문서 로딩부터 답변 생성까지 LLM 애플리케이션 구축에 필요한 여러 단계를 하나의 흐름으로 연결·관리한다. LangChain은 특정 LLM(OpenAI, Gemini 등)이나 특정 벡터 DB에 종속되지 않고, 로더·스플리터·벡터 저장소·리트리버·프롬프트·LLM 같은 컴포넌트를 표준화된 인터페이스로 이어붙이는 방식으로 동작한다. 이 덕분에 개발자는 [[RAG]] 파이프라인의 각 단계를 부품처럼 교체하거나 재사용할 수 있다.

## 동작 흐름 (6단계)

1. **입력**: 질문 또는 프롬프트를 입력받는다. 프롬프트 템플릿을 미리 정의해두면 매번 같은 형식으로 질문을 감싸서 LLM에 전달할 수 있다.
2. **도큐먼트 로더(Document Loader)**: URL·이메일·PDF 등 다양한 소스에서 도큐먼트를 불러와 이후 처리를 위해 메모리나 데이터베이스에 적재한다. 소스 형식마다 전용 로더가 있어 형식 차이를 흡수해준다.
3. **스플리터(Text Splitter)**: 불러온 문서를 통째로 다루지 않고 작은 조각(Splits, Chunk)으로 분할한다. LLM의 입력 길이 제한을 지키고, 검색 시 관련 있는 부분만 정확히 집어낼 수 있게 하기 위함이다.
4. **저장(Vector Store)**: 분할된 문서 조각을 [[임베딩]] 벡터로 변환해 벡터 데이터베이스에 저장한다. 이 단계 이후로 문서는 원문이 아니라 검색 가능한 벡터 형태로도 존재하게 된다.
5. **검색(Retrieval)**: 사용자의 Query(질문)를 같은 방식으로 임베딩한 뒤, 벡터 DB에서 그와 유사한 문서 조각을 검색한다.
6. **출력**: 검색된 문서 조각과 원래 질문을 담은 프롬프트를 LLM에 전달해 최종 답변을 생성한다.

아래는 이 6단계를 LangChain 스타일로 표현한 의사코드(pseudocode)다 (이해를 돕기 위해 위키 편집 과정에서 작성한 것으로, 실제 LangChain API의 정확한 문법·버전과는 다를 수 있다).

```python
from langchain.document_loaders import PyPDFLoader
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain.vectorstores import FAISS
from langchain.embeddings import OpenAIEmbeddings

# 2. 도큐먼트 로더: PDF에서 문서 불러오기
docs = PyPDFLoader("회사_매뉴얼.pdf").load()

# 3. 스플리터: 문서를 작은 조각으로 분할
splitter = RecursiveCharacterTextSplitter(chunk_size=500, chunk_overlap=50)
splits = splitter.split_documents(docs)

# 4. 저장: 분할된 문서를 임베딩으로 변환해 벡터 DB에 저장
vectorstore = FAISS.from_documents(splits, OpenAIEmbeddings())

# 5. 검색: 질문과 유사한 문서 조각 검색
retriever = vectorstore.as_retriever()
relevant_docs = retriever.invoke("환불 정책이 뭐야?")

# 6. 출력: 검색된 문서 + 프롬프트를 LLM에 전달해 답변 생성 (체인 실행부는 생략)
```

## 특징

모듈화, 유연성, 통합성, 확장성을 갖춰 위 6단계를 연결·관리한다.

- **모듈화**: 로더·스플리터·벡터스토어·리트리버 등 각 컴포넌트가 독립된 부품처럼 분리돼 있어 하나만 교체하기 쉽다.
- **유연성**: 특정 LLM이나 특정 벡터 DB에 묶이지 않고 여러 조합을 자유롭게 구성할 수 있다.
- **통합성**: 다양한 서드파티 도구·API(검색 엔진, 데이터베이스, 다른 LLM 제공사 등)와 연동하기 위한 인터페이스를 제공한다.
- **확장성**: 단순한 6단계 파이프라인을 넘어, 여러 체인을 엮거나 도구 호출을 결합해 복잡한 에이전트로 발전시킬 수 있다.

## LangChain을 사용하는 이유 (7가지)

출처 자료의 "LangChain을 사용하는 이유" 표를 그대로 옮긴 것이다.

| # | 이유 | 설명 |
|---|---|---|
| 1 | LLM을 쉽게 연결 | OpenAI, Hugging Face, Cohere 등 다양한 LLM API를 손쉽게 호출 가능 |
| 2 | 프롬프트 관리 용이 | `PromptTemplate`을 사용해 체계적으로 프롬프트 설계 및 재사용 가능 |
| 3 | 메모리 활용 가능 | 대화 상태를 저장해 대화형 챗봇 개발에 유리 |
| 4 | 벡터 데이터베이스와 통합 가능 | FAISS, Pinecone, Weaviate 등과 쉽게 연결하여 장기 기억 구현 가능 |
| 5 | 다양한 데이터 소스 활용 | PDF, 웹페이지, 데이터베이스 등에서 정보를 읽어와 모델 입력으로 활용 |
| 6 | 체인(Chain) 기반 워크플로우 | LLM 응답을 조합하여 여러 단계의 논리적인 처리가 가능 |
| 7 | 에이전트 기반 동적 실행 | 도구(Tool)과 연동해 LLM이 동적으로 판단하고 실행할 수 있도록 지원 |

> LangChain은 LLM 애플리케이션 개발을 더 빠르고, 유연하고, 확장성 있게 만들어 준다. (출처 자료 원문)

## LangChain 구성도

출처 자료의 "랭체인 구성도" 다이어그램(brunch.co.kr/@ywkim36/147 인용)에 따르면, LangChain은 다음 구성 요소를 중심으로 연결된다.

- **모델**: LLM 모델 호출
- **인덱스**: 도큐먼트 로더, 스플리터, 벡터 DB 등 문서 처리·색인 관련 컴포넌트
- **메모리**: 대화 상태 저장
- **프롬프트**: 프롬프트 템플릿 관리
- **체인**: 여러 단계를 연결한 처리 흐름
- **에이전트와 도구**: 검색·계산·코드 실행 등 외부 도구를 동적으로 호출

## LangChain과 유사 프레임워크 비교

출처 자료에는 없는 내용이지만, LLM 앱 개발 프레임워크를 선택할 때 자주 비교되는 대안이라 일반적으로 알려진 내용을 바탕으로 위키 편집 과정에서 추가한다.

| 프레임워크 | 특징 |
|---|---|
| LangChain | 범용 체인·에이전트 프레임워크. 컴포넌트 조합의 자유도가 높은 대신 학습 곡선이 있다는 평도 있다 |
| LlamaIndex | 문서 인덱싱·검색(RAG)에 특화. 데이터 연결과 인덱스 구축이 상대적으로 간단하다 |
| Semantic Kernel (Microsoft) | .NET/C# 생태계와의 통합에 강점이 있다 |

실무에서는 RAG 중심의 단순한 검색 Q&A라면 LlamaIndex를, 복잡한 멀티스텝 에이전트나 다양한 외부 도구 연동이 필요하면 LangChain을 선택하는 경우가 많다는 것이 일반적인 평가다.

## 관련 지식

- [[RAG]] — LangChain은 RAG 파이프라인을 구현하는 대표적 프레임워크
- [[FAISS]] — LangChain에서 흔히 사용하는 벡터 데이터베이스 라이브러리
- [[임베딩]] — LangChain의 저장/검색 단계에서 문서를 벡터로 변환하는 데 사용

## 출처

- [[동국대_교육자료1]] p.11 "랭체인", p.12 "LangChain을 사용하는 이유", p.13 "LangChain 동작 흐름 한눈에 보기", p.18 "랭체인 구성도" (brunch.co.kr/@ywkim36/147 인용)
- [[동국대캠퍼스타운_AI 어플리케이션 MVP 제작 과정 교안]] p.8 "랭체인", p.9 "LangChain을 사용하는 이유", p.10 "LangChain 동작 흐름 한눈에 보기", p.12 "랭체인 구성도" (동일 내용)
