# Day 3 Pandas Data Handling

## 적용 학습법

- 기본: 단계별 출력 추적
- 보조: 오류 데이터 복구 훈련

## 목표

LLM 프로젝트에서 자주 만나는 CSV, 로그, 평가표 데이터를 Pandas로 읽고 필터링한다.

- CSV 읽기
- DataFrame 구조 이해
- 조건 필터링
- 결측치 확인
- groupby
- 간단한 평가표 만들기

## 실습 1 - DataFrame 필터링

```python
import pandas as pd

df = pd.DataFrame({
    "question": ["배송", "환불", "교환"],
    "category": ["delivery", "refund", "refund"],
    "resolved": [True, False, True],
})

refund_df = df[df["category"] == "refund"]
print(refund_df)
```

질문:

1. `df["category"] == "refund"`의 결과는 무엇인가?
2. `refund_df`에는 몇 개의 행이 남는가?
3. RAG 평가 로그에서 이런 필터링이 왜 필요한가?

## 실습 2 - 결측치 확인

```python
import pandas as pd

df = pd.DataFrame({
    "question": ["배송", "환불", "교환"],
    "expected_answer": ["2-3일", None, "7일 이내"],
    "retrieved_doc": ["shipping.md", "refund.md", None],
})

print(df.isna())
print(df.isna().sum())
```

질문:

1. 어떤 열에 결측치가 있는가?
2. 결측치가 있는 평가 데이터가 RAG 품질 판단에 어떤 문제를 만들 수 있는가?
3. 결측치를 삭제할지 채울지 결정할 때 무엇을 봐야 하는가?

## 실습 3 - groupby로 평가 요약

```python
import pandas as pd

df = pd.DataFrame({
    "category": ["delivery", "refund", "refund", "delivery"],
    "correct": [True, False, True, True],
})

summary = df.groupby("category")["correct"].mean()
print(summary)
```

질문:

1. `correct`가 boolean인데 평균을 내면 어떤 의미가 되는가?
2. category별 성능을 나눠 보는 이유는 무엇인가?
3. 전체 accuracy만 보는 것과 category별 성능을 보는 것의 차이는 무엇인가?

## 완료 기준

- DataFrame 필터링 과정을 boolean mask로 설명할 수 있다.
- 결측치가 평가에 미치는 영향을 설명할 수 있다.
- groupby 결과를 서비스 품질 분석과 연결할 수 있다.
