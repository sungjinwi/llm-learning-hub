# Day 6 LLM Theory Lite - Embedding And RAG

## 적용 학습법

- 기본: 역공학
- 보조: 검색 결과 평가

## 목표

Embedding, similarity search, hallucination, grounding을 RAG 디버깅과 연결한다.

## 실습 1 - embedding의 역할

아래 두 문장이 정확히 같은 단어를 쓰지는 않지만 의미는 가깝다.

```text
질문: 환불은 며칠 안에 가능한가요?
문서: 상품 수령 후 7일 이내 환불 신청이 가능합니다.
```

질문:

1. keyword 검색만으로는 놓칠 수 있는 부분은 무엇인가?
2. embedding은 이런 상황에서 어떤 역할을 하는가?
3. embedding 검색 결과가 항상 정답이라고 볼 수 없는 이유는 무엇인가?

## 실습 2 - similarity search와 top-k

```python
retrieved_chunks = [
    {"rank": 1, "source": "shipping.md", "text": "일반 배송은 2-3일 소요됩니다."},
    {"rank": 2, "source": "refund.md", "text": "상품 수령 후 7일 이내 환불 신청이 가능합니다."},
]
```

질문:

1. rank 1 결과가 항상 답변 근거로 가장 좋은가?
2. top-k를 너무 작게 잡으면 어떤 문제가 생기는가?
3. top-k를 너무 크게 잡으면 어떤 문제가 생기는가?

## 실습 3 - retrieval과 generation 분리

아래 실패를 분류한다.

```text
질문: 환불은 며칠 안에 가능한가요?
검색 결과: refund.md가 검색됨. "상품 수령 후 7일 이내 환불 신청이 가능합니다."
모델 답변: 환불은 30일 이내 가능합니다.
```

질문:

1. retrieval은 성공했는가?
2. generation은 성공했는가?
3. harness나 eval에서는 이 실패를 어떻게 기록해야 하는가?

## 완료 기준

- embedding과 similarity search의 역할을 설명할 수 있다.
- top-k와 chunk 품질이 RAG 성능에 영향을 준다고 설명할 수 있다.
- retrieval 실패와 generation 실패를 분리할 수 있다.
