# Day 1 Active Recall - Python Core

## 2026-05-20 진단 후 문제

정답은 먼저 보지 말고 직접 답한 뒤 채점한다.

1. `list`와 `dict`는 데이터를 찾는 방식이 어떻게 다른가?
2. `dict`에서 같은 key에 값을 두 번 넣으면 어떤 일이 생기는가?
3. 아래 코드의 출력은 무엇인가?

```python
items = {"a": 1, "b": 2}
items["a"] = items["a"] + 5
print(items)
```

4. 반복문에서 `if`를 함께 쓰는 이유를 한 문장으로 설명하라.
5. 함수를 만들 때 parameter와 return은 각각 어떤 역할을 하는가?

## 2026-05-20 작은 구현 실습

목표: 학생 점수 목록에서 60점 이상인 학생 이름만 리스트로 반환하는 함수 만들기.

```python
students = [
    {"name": "Kim", "score": 80},
    {"name": "Lee", "score": 55},
    {"name": "Park", "score": 70},
]

def get_passed_names(student_list):
    result = []

    for student in student_list:
        if student["score"] >= 60:
            result.append(student["name"])

    return result

passed = get_passed_names(students)
print(passed)
```

예상 출력:

```python
['Kim', 'Park']
```
