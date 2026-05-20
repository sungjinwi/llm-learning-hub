# 2026-05-20 Day 1 학습 기록 - Python Core

NotebookLM 또는 슬라이드 제작용으로 바로 넣을 수 있도록 오늘 학습 흐름, 핵심 개념, 실습 코드, 약점 보정, 다음 복습 항목을 한 파일에 정리한다.

## 1. 오늘의 학습 목표

주제: Python 기본 문법과 자료구조

목표:

- 변수, 타입, 조건문, 반복문의 기본 흐름을 이해한다.
- `list`, `dict`, `function`, `class`의 최소 개념을 구분한다.
- 코드 실행 전에 출력 결과를 예측한다.
- 헷갈린 개념을 약점으로 기록하고 재출제로 해결한다.
- LLM 활용 과정 사전준비 관점에서 Python 기본기를 점검한다.

## 2. 오늘 사용한 학습 방식

- 소크라테스식 문답: 먼저 사용자가 개념을 설명하고, 부족한 부분만 교정했다.
- 능동적 회상: 정답을 먼저 보지 않고 출력과 이유를 예측했다.
- 코드 출력 예측: `dict`, 반복문, 조건문, 함수, class 예제를 실행 전 추론했다.
- 빈칸 구현: 학생 점수 목록에서 60점 이상인 학생 이름만 추출하는 함수를 완성했다.
- 파인만식 요약: 마지막에 `list`, `dict`, `function`, `parameter/argument`, `class`를 직접 설명했다.

## 3. 핵심 개념 요약

### list

`list`는 순서가 있는 값의 모음이다. 각 값은 0부터 시작하는 인덱스로 접근한다.

예:

```python
values = [10, 20, 30]
print(values[1])
```

핵심:

- 순서가 있다.
- 인덱스로 접근한다.
- 같은 값을 여러 번 넣을 수 있다.

### dict

`dict`는 key-value 쌍으로 값을 저장하는 자료구조다.

예:

```python
items = {"a": 1, "b": 2}
items["a"] = 3
print(items)
```

출력:

```python
{'a': 3, 'b': 2}
```

핵심:

- key로 value에 접근한다.
- key는 중복될 수 없다.
- 같은 key에 값을 다시 넣으면 기존 value가 갱신된다.
- Python 3.7+에서는 삽입 순서가 보존된다.

### function

`function`은 반복되는 로직을 이름 붙여 재사용하기 위한 구조다.

예:

```python
def add(a, b):
    return a + b

result = add(2, 3)
print(result)
```

출력:

```python
5
```

핵심:

- `parameter`: 함수를 정의할 때 받기로 약속한 이름. 예: `a`, `b`
- `argument`: 함수를 호출할 때 실제로 넘기는 값. 예: `2`, `3`
- `return`: 함수 밖으로 돌려주는 결과값

### class

`class`는 데이터와 그 데이터를 다루는 행동을 가진 객체를 만들기 위한 설계도다.

예:

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def is_passed(self):
        return self.score >= 60

student = Student("Lee", 55)

print(student.name)
print(student.is_passed())
```

출력:

```python
Lee
False
```

핵심:

- `dict`는 `student["name"]`처럼 key로 접근한다.
- 객체는 `student.name`처럼 점 표기법으로 속성에 접근한다.
- 객체의 행동은 `student.is_passed()`처럼 메서드로 실행한다.

## 4. 오늘의 주요 실습

### 실습 목표

학생 점수 목록에서 60점 이상인 학생 이름만 리스트로 반환하는 함수 만들기.

### 실습 코드

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

출력:

```python
['Kim', 'Park']
```

### 이 실습에서 확인한 개념

- `students`는 `dict`를 원소로 가진 `list`다.
- `for student in student_list`는 학생 정보를 하나씩 꺼낸다.
- `student["score"] >= 60`은 합격 조건을 검사한다.
- `result.append(student["name"])`은 합격한 학생의 이름만 결과 리스트에 추가한다.
- `print(passed)`는 리스트 전체를 출력하므로 대괄호와 문자열 따옴표가 함께 보인다.

## 5. 오늘 발견한 약점과 교정

### 약점 1. dict의 순서와 중복 기준

처음 설명:

- `dict`는 순서가 없고 중복이 허용되지 않는다고 설명했다.

교정:

- Python 3.7+의 `dict`는 삽입 순서를 보존한다.
- 중복 제한은 value 전체가 아니라 key에 적용된다.
- 같은 key에 값을 다시 넣으면 기존 value가 덮어써진다.

해결 근거:

```python
items = {"a": 1, "b": 2}
items["a"] = 3
print(items)
```

위 코드에서 `'a'` key의 value만 `3`으로 바뀐다고 정확히 설명했다.

상태: resolved

### 약점 2. parameter와 argument 구분

처음 답변:

- `parameter: 2, 3`
- `argument: a, b`

교정:

- parameter는 함수 정의에 적는 이름이다.
- argument는 함수 호출 시 실제로 넘기는 값이다.

예:

```python
def introduce(name, age):
    return name + " is " + str(age)

message = introduce("Kim", 30)
print(message)
```

정답:

- parameter: `name`, `age`
- argument: `"Kim"`, `30`
- 출력: `Kim is 30`

상태: resolved

### 약점 3. list, dict, class 요약 표현

처음 요약에서 `list`, `dict`, `class` 표현이 약간 부정확했다.

최종 교정 문장:

- `list`는 순서를 가진 데이터의 집합이고 인덱스로 접근 가능하다.
- `dict`는 key-value 쌍을 가진 데이터 집합이고 key를 통해 접근 가능하다.
- `class`는 데이터 자체가 아니라 변수와 함수로 구성된 객체를 만드는 설계도다.

상태: resolved

## 6. 오늘의 운영 개선

학습 중 문제 출제 방식에서 개선점이 발견되었다.

개선 전 문제:

- 코드 일부가 누락되거나 사용자가 답변 번호를 붙이기 불편할 수 있었다.

개선 후 규칙:

- 코드 출력 예측 문제는 독립 실행 가능한 전체 스니펫으로 출제한다.
- 필요한 변수, 함수, import, 입력값이 모두 포함되어야 한다.
- 오답 기록 전에 출제문 누락이나 모호함을 먼저 확인한다.
- 여러 문제를 낼 때는 사용자가 답변하기 쉽도록 번호와 답변 템플릿을 함께 제공한다.

이 규칙은 `AI_STUDY_OPERATING_RULES.md`에 반영되었다.

## 7. Day 1 완료 판단

완료한 항목:

- Python Core 노트 작성
- Active recall 문제 풀이
- 약점 기록과 재출제
- 약점 resolved 처리
- 작은 구현 실습
- 5문장 이내 개념 요약
- LLM 활용 과정 사전준비 관점의 계획 점검
- 자주 하는 실수 문서 작성

Day 1 상태: completed

## 8. 내일 첫 복습 문제

다음 학습 시작 전에 아래 3문제를 먼저 풀고 Day 2로 넘어간다.

1. `list`, `dict`, `class`를 각각 한 문장으로 설명하라.
2. `def add(a, b): return a + b`와 `add(2, 3)`에서 parameter와 argument를 구분하라.
3. 아래 코드의 출력과 이유를 설명하라.

```python
items = {"name": "Kim", "score": 80}
items["score"] = items["score"] + 5
print(items)
```

## 9. LLM 과정 사전준비 관점의 다음 단계

교육과정은 LangChain, RAG, Agent, Graph RAG 중심의 LLM 활용 과정이다.

따라서 이후 사전준비는 다음 순서가 적합하다.

1. Python 실전 도구: `import`, `venv`, `pip`, `pathlib`, 파일 입출력, JSON, `try/except`
2. Pandas 기초: CSV 읽기, 필터링, 결측치, groupby
3. API와 LLM 호출: request/response, 환경변수, OpenAI API 기본 호출
4. Prompt와 구조화 출력: system/user 메시지, JSON output, prompt versioning
5. Embedding과 RAG: chunking, retrieval, generation, 검색 결과 확인
6. 미니 LLM 프로젝트: FAQ 기반 QA, Gradio UI, 로그, 간단 평가표

## 10. NotebookLM 슬라이드 제안 구성

슬라이드 1: 오늘의 목표

- Python Core 첫날
- LLM 활용 과정 사전준비
- 출력 예측과 약점 기록 중심 학습

슬라이드 2: 오늘 배운 핵심 개념

- list
- dict
- function
- parameter / argument
- class

슬라이드 3: list와 dict 비교

- list: 순서, 인덱스
- dict: key-value, key 접근
- 같은 key 재할당 시 value 갱신

슬라이드 4: function과 parameter / argument

- parameter는 정의 시 이름
- argument는 호출 시 실제 값
- return은 함수 밖으로 돌려주는 값

슬라이드 5: class 최소 개념

- 객체 설계도
- 데이터와 행동을 함께 묶음
- `student["name"]` vs `student.name`

슬라이드 6: 주요 실습 코드

- 학생 점수 목록
- 60점 이상 필터링
- 이름 리스트 반환

슬라이드 7: 오늘의 약점과 해결

- dict 순서와 key 중복
- parameter / argument 반대 이해
- class를 데이터 자체로 표현한 점

슬라이드 8: 학습 운영 개선

- 독립 실행 가능한 문제 출제
- 답변 템플릿 제공
- 오답 기록 전 출제 오류 확인

슬라이드 9: LLM 과정 대비 방향

- PyTorch보다 API, JSON, RAG, 평가 우선
- LangChain 코드의 입력, 처리, 출력 추적
- 근거 기반 답변과 평가 습관

슬라이드 10: 내일 할 일

- Day 1 복습 3문제
- Python 실전 도구 학습
- JSON, 파일 입출력, 예외 처리 진입
