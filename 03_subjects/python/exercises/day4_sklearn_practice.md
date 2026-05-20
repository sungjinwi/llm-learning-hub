# Day 4 Scikit Learn Practice

## 적용 학습법

- 기본: 역공학
- 보조: 능동적 회상

## 목표

Scikit-Learn의 fit, predict, score 흐름과 평가 지표를 코드로 확인한다.

## 실습

아래 코드의 흐름을 입력, 학습, 예측, 평가로 나누어 설명한다.

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score

X, y = load_iris(return_X_y=True)
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = RandomForestClassifier(random_state=42)
model.fit(X_train, y_train)

pred = model.predict(X_test)
print(accuracy_score(y_test, pred))
```

질문:

1. `fit`은 무엇을 저장하는가?
2. `predict`는 어떤 입력을 받아 무엇을 반환하는가?
3. 왜 train/test split이 필요한가?
