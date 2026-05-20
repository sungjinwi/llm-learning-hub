# Day 5 Prompt And Structured Output

## 적용 학습법

- 기본: 구조화 비교
- 보조: 능동적 회상

## 목표

프롬프트를 감으로 바꾸지 않고, 입력과 기대 출력 기준으로 비교한다.

정확한 structured output 사용법은 학습 당일 공식 문서로 확인한다.

## 실습 1 - prompt 버전 비교

같은 질문에 대해 두 prompt의 차이를 설명한다.

```python
question = "환불 규정을 알려줘."

prompt_v1 = "답변해줘: " + question
prompt_v2 = """
너는 고객센터 상담원이다.
아래 질문에 대해 FAQ 문서에 근거해서만 답변하라.
근거가 부족하면 '문서에서 확인할 수 없습니다'라고 답하라.

질문: 환불 규정을 알려줘.
"""

print(prompt_v1)
print(prompt_v2)
```

질문:

1. v1과 v2 중 RAG에 더 적합한 prompt는 무엇인가?
2. 그 이유는 무엇인가?
3. v2에서도 여전히 부족한 점은 무엇인가?

## 실습 2 - JSON 출력 검증

```python
import json

raw_output = '{"answer": "환불은 7일 이내 가능합니다.", "confidence": 0.8}'
parsed = json.loads(raw_output)

print(parsed["answer"])
print(parsed["confidence"])
```

질문:

1. `raw_output`과 `parsed`의 타입은 각각 무엇인가?
2. JSON output이 일반 문장 출력보다 좋은 경우는 언제인가?
3. JSON 파싱이 실패할 수 있는 경우는 무엇인가?

## 실습 3 - 평가 기준 만들기

아래 질문에 대한 답변을 평가할 기준 3개를 직접 작성한다.

```text
질문: 배송은 얼마나 걸리나요?
기대 근거: shipping.md에 "일반 배송은 2-3일 소요"라고 적혀 있음.
```

답변 형식:

```md
1. 근거 일치:
2. 답변 완전성:
3. 금지할 실패:
```

## 완료 기준

- prompt 버전을 비교할 기준을 말할 수 있다.
- structured output이 필요한 이유를 설명할 수 있다.
- LLM 답변 평가 기준을 최소 3개 만들 수 있다.
