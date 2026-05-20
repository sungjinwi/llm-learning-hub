# Day 1 Python Core Practice

## 적용 학습법

- 기본: 소크라테스식 문답
- 보조: 능동적 회상

## 목표

변수, 조건문, 반복문, list, dict, function을 직접 코드로 다룬다.

## 실습 1 - 출력 예측

정답을 보기 전에 출력 결과를 예측한다.

```python
scores = {"kim": 80, "lee": 95}
scores["park"] = scores["kim"] + 5

for name, score in scores.items():
    if score >= 90:
        print(name, "pass")
    else:
        print(name, "retry")
```

## 실습 2 - 빈칸 코드

짝수만 골라 합계를 구한다.

```python
numbers = [3, 4, 7, 8, 10]
total = 0

for n in numbers:
    if ___:
        total = ___

print(total)
```

## 실습 3 - 작은 구현

아래 조건을 만족하는 함수를 작성한다.

- 입력: 학생 이름과 점수 dict
- 출력: 90점 이상인 학생 이름 list

```python
def get_passed_students(scores):
    # 여기에 직접 작성
    pass

scores = {"kim": 80, "lee": 95, "park": 91}
print(get_passed_students(scores))
```
