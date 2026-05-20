# Day 6 Embedding And RAG

## 적용 학습법

- 기본: 역공학
- 보조: 검색 결과 평가

## 목표

RAG를 하나의 마법 상자가 아니라 chunking, retrieval, generation으로 나누어 이해한다.

정확한 embedding API와 LangChain retriever 사용법은 학습 당일 공식 문서로 확인한다.

이론 연결:

- embedding: 문장과 문서를 벡터로 표현하는 방식
- similarity search: 질문과 가까운 문서 chunk를 찾는 과정
- hallucination: 검색 근거가 부족할 때 모델이 그럴듯하게 틀릴 수 있는 이유
- grounding: 답변을 검색된 근거에 묶는 방식

관련 보충 실습:

- `day6_llm_theory_lite_embedding_rag.md`

## 실습 1 - chunking 판단

아래 문서를 어떤 단위로 나눌지 제안한다.

```text
배송 안내:
일반 배송은 2-3일 소요됩니다.
도서 산간 지역은 1-2일 추가될 수 있습니다.

환불 안내:
상품 수령 후 7일 이내 환불 신청이 가능합니다.
사용 흔적이 있는 상품은 환불이 제한됩니다.
```

질문:

1. chunk를 몇 개로 나누는 것이 좋아 보이는가?
2. 너무 크게 자르면 어떤 문제가 생기는가?
3. 너무 작게 자르면 어떤 문제가 생기는가?

## 실습 2 - slicing으로 chunk 미리보기

아래 코드는 실제 chunking 라이브러리를 쓰기 전, slicing으로 chunk의 감각을 확인하는 연습이다.

```python
text = "배송 안내: 일반 배송은 2-3일 소요됩니다. 환불 안내: 상품 수령 후 7일 이내 환불 신청이 가능합니다."

chunk_size = 25

for start in range(0, len(text), chunk_size):
    chunk = text[start:start + chunk_size]
    print(start, chunk)
```

질문:

1. `range(0, len(text), chunk_size)`는 어떤 start 값을 만들 것 같은가?
2. `text[start:start + chunk_size]`에서 slicing이 어떤 역할을 하는가?
3. 실제 RAG에서는 단순 글자 수 slicing만으로 부족한 이유는 무엇인가?

## 실습 3 - retrieval 결과 평가

```python
query = "환불은 며칠 안에 가능한가요?"

retrieved_chunks = [
    {"source": "shipping.md", "text": "일반 배송은 2-3일 소요됩니다."},
    {"source": "refund.md", "text": "상품 수령 후 7일 이내 환불 신청이 가능합니다."},
]

for chunk in retrieved_chunks:
    print(chunk["source"], ":", chunk["text"])
```

질문:

1. 검색 결과 중 답변 근거로 적합한 chunk는 무엇인가?
2. 부적합한 chunk가 함께 검색되면 어떤 문제가 생길 수 있는가?
3. top-k를 바꾸면 어떤 차이가 생길 수 있는가?

## 실습 4 - 실패 원인 분리

아래 상황에서 원인이 retrieval인지 generation인지 구분한다.

```text
질문: 환불은 며칠 안에 가능한가요?
검색 결과: 배송 안내 chunk만 검색됨.
모델 답변: 일반 배송은 2-3일 걸립니다.
```

질문:

1. 주된 실패 원인은 retrieval인가 generation인가?
2. 어떤 로그를 보면 확인할 수 있는가?
3. 다음 실험으로 무엇을 바꿔볼 것인가?

## 완료 기준

- RAG를 chunking, retrieval, generation으로 나눠 설명할 수 있다.
- slicing과 `range`가 chunking의 기초 감각을 만드는 데 어떻게 쓰이는지 설명할 수 있다.
- embedding과 similarity search가 retrieval에 쓰이는 이유를 설명할 수 있다.
- hallucination과 grounding을 RAG 평가와 연결할 수 있다.
- 검색된 chunk를 직접 확인해야 하는 이유를 설명할 수 있다.
- RAG 실패 원인을 분리해서 말할 수 있다.
