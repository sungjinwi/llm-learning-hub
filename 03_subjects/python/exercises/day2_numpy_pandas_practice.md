# Day 2 NumPy Pandas Practice

## 적용 학습법

- 기본: 문서 기반 실습
- 보조: 출력 예측

## 목표

배열과 DataFrame의 모양 변화, 필터링, 집계를 직접 확인한다.

## 실습 1 - shape 예측

```python
import numpy as np

x = np.array([[1, 2, 3], [4, 5, 6]])
print(x.shape)
print(x.reshape(3, 2))
```

실행 전에 `x.shape`와 reshape 결과를 예측한다.

## 실습 2 - DataFrame 필터링

```python
import pandas as pd

df = pd.DataFrame({
    "name": ["kim", "lee", "park"],
    "score": [80, 95, 91],
    "team": ["A", "B", "A"],
})

passed = df[df["score"] >= 90]
print(passed)
```

질문:

1. `df["score"] >= 90`의 결과는 무엇인가?
2. 왜 그 결과로 행을 필터링할 수 있는가?
3. team별 평균 점수를 구하는 코드를 작성해라.
