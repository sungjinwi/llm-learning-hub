# Day 6 Embedding And RAG

## 적용 학습법

- 기본: 역공학
- 보조: 검색 결과 평가

## 목표

RAG를 하나의 마법 상자가 아니라 chunking, retrieval, generation으로 나누어 이해한다.

정확한 embedding API와 LangChain retriever 사용법은 학습 당일 공식 문서로 확인한다.

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

## 실습 2 - retrieval 결과 평가

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

## 실습 3 - 실패 원인 분리

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
- 검색된 chunk를 직접 확인해야 하는 이유를 설명할 수 있다.
- RAG 실패 원인을 분리해서 말할 수 있다.
