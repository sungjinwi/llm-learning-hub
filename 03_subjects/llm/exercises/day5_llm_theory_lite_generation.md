# Day 5 LLM Theory Lite - Generation

## 적용 학습법

- 기본: 출력 비교
- 보조: 실패 사례 분석

## 목표

Prompt와 structured output을 배우면서 sampling, temperature, hallucination, grounding의 의미를 함께 이해한다.

## 실습 1 - temperature와 출력 안정성

다음 두 상황에 더 적합한 temperature 방향을 고른다.

```text
상황 A:
고객센터 환불 규정을 JSON으로 정확히 출력해야 한다.

상황 B:
새로운 블로그 제목 아이디어 20개를 다양하게 제안해야 한다.
```

질문:

1. 어느 상황에서 낮은 temperature가 더 적합한가?
2. 어느 상황에서 높은 temperature가 도움이 될 수 있는가?
3. 평가 실험에서는 왜 temperature 같은 조건을 고정해야 하는가?

## 실습 2 - hallucination과 grounding

아래 답변의 위험을 설명한다.

```text
질문: 환불은 며칠 안에 가능한가요?
제공된 문서: 없음
모델 답변: 보통 14일 이내 환불 가능합니다.
```

질문:

1. 이 답변이 위험한 이유는 무엇인가?
2. hallucination 가능성을 줄이려면 prompt에 어떤 조건이 필요할까?
3. grounding된 답변이라면 어떤 근거가 함께 있어야 할까?

## 실습 3 - structured output이 필요한 이유

아래 두 출력 중 자동 검증이 쉬운 쪽을 고르고 이유를 설명한다.

```text
출력 A:
환불은 7일 이내 가능합니다. 근거는 refund.md입니다.

출력 B:
{"answer": "환불은 7일 이내 가능합니다.", "source": "refund.md", "has_grounding": true}
```

질문:

1. 자동 검증이 쉬운 출력은 무엇인가?
2. JSON output도 실패할 수 있는 경우는 무엇인가?
3. structured output과 eval은 어떻게 연결되는가?

## 완료 기준

- temperature와 출력 안정성을 연결해 설명할 수 있다.
- hallucination과 grounding의 차이를 설명할 수 있다.
- structured output이 평가와 자동화에 필요한 이유를 설명할 수 있다.
