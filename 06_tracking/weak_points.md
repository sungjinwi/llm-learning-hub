# Weak Points

약점은 숨길 것이 아니라 다음 학습을 자동으로 정하는 입력값이다.

## 기록 형식

```md
## YYYY-MM-DD - 주제

- 약점:
- 근거:
- 교정 설명:
- 재출제 문제:
- 다음 복습:
- 상태: open
```

## Open

## Resolved

## 2026-05-20 - list, dict, class 요약 표현

- 약점: `list`와 `dict`의 차이, `class`의 정체를 설명할 때 표현이 다소 부정확함.
- 근거: Day 1 마무리 요약에서 `list`를 "중복 및 value의 집합", `class`를 "데이터"라고 표현함.
- 교정 설명: `list`는 순서가 있는 값의 모음이고 인덱스로 접근한다. `dict`는 key-value 쌍의 모음이고 key로 접근한다. `class`는 데이터 자체라기보다 데이터와 행동을 가진 객체를 만들기 위한 설계도다.
- 재출제 문제: `list`, `dict`, `class`를 각각 한 문장으로 다시 설명하라.
- 다음 복습: 2026-05-21
- 상태: resolved - 재설명에서 list, dict, class를 정확히 구분함.

## 2026-05-20 - Python dict 기본 개념

- 약점: `dict`를 "순서가 없고 중복이 허용되지 않는다"로 설명했지만, Python 3.7+에서는 삽입 순서가 보존되며 중복 제한은 key에 적용된다는 점이 빠져 있었음.
- 근거: Day 1 진단 질문 1에서 list와 dict의 차이를 설명할 때 dict의 순서와 중복 기준을 부정확하게 표현함.
- 교정 설명: `list`는 순서 기반으로 값을 저장하고 같은 값을 여러 번 넣을 수 있다. `dict`는 key-value 쌍으로 값을 저장하며 key는 중복될 수 없고, 같은 key에 다시 값을 넣으면 기존 value가 덮어써진다.
- 재출제 문제: `items = {"a": 1, "b": 2}; items["a"] = 3` 실행 후 `items`의 내용과 이유를 설명하라.
- 다음 복습: 2026-05-21
- 상태: resolved - 재출제에서 기존 key의 value 변경을 정확히 설명함.

## 2026-05-20 - parameter와 argument 구분

- 약점: parameter와 argument의 의미를 서로 반대로 이해함.
- 근거: Day 1 active recall 재출제에서 `parameter: 2, 3`, `argument: a, b`라고 답함.
- 교정 설명: parameter는 함수를 정의할 때 괄호 안에 적는 이름이고, argument는 함수를 호출할 때 실제로 넘기는 값이다. `def introduce(name, age):`에서 `name`, `age`는 parameter이고, `introduce("Kim", 30)`에서 `"Kim"`, `30`은 argument다.
- 재출제 문제: `def introduce(name, age): return name + " is " + str(age); introduce("Kim", 30)`에서 parameter와 argument를 각각 찾아라.
- 다음 복습: 2026-05-21
- 상태: resolved - 재출제에서 parameter와 argument를 정확히 구분함.
