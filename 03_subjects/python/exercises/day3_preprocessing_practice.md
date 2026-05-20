# Day 3 Preprocessing Practice

## 적용 학습법

- 기본: 오류 데이터 복구 훈련
- 보조: 역공학

## 목표

결측치, 이상치, 인코딩을 직접 처리한다.

## 실습

```python
import pandas as pd

df = pd.DataFrame({
    "age": [20, None, 35, 999],
    "city": ["Seoul", "Busan", None, "Seoul"],
    "label": ["yes", "no", "yes", "no"],
})
```

직접 할 일:

1. 결측치가 있는 열을 찾는다.
2. `age`의 999를 이상치로 보고 처리 방식을 제안한다.
3. `city`를 one-hot encoding한다.
4. 처리 전후 DataFrame의 차이를 설명한다.
