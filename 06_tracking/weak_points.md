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

## 2026-05-21 - Python slicing end index

- 약점: `list[start:end]`에서 `end` 인덱스가 포함된다고 착각함.
- 근거: `results[:3]`의 출력과 개수를 `['doc1', 'doc2', 'doc3', 'doc4']`, 총 4개로 예측함.
- 교정 설명: Python slicing에서 `start`는 포함되고 `end`는 포함되지 않는다. 따라서 `results[:3]`은 index 0, 1, 2만 가져와 `['doc1', 'doc2', 'doc3']`이 된다.
- 재출제 문제: `items = ["a", "b", "c", "d", "e"]; print(items[1:4]); print(items[:2])`의 출력을 예측하라.
- 다음 복습: 2026-05-22
- 상태: open

## 2026-05-21 - pathlib name and stem

- 약점: `Path.name`이 확장자를 제외한 파일명이라고 예측함.
- 근거: `Path("data") / "faq.json"`에서 `file_path.name`의 출력을 `faq`로 예측함.
- 교정 설명: `Path.name`은 확장자를 포함한 마지막 경로 요소를 반환한다. 확장자를 제외한 이름은 `Path.stem`이고, 확장자는 `Path.suffix`다.
- 재출제 문제: `p = Path("logs/app/error.txt")`에서 `p.name`, `p.stem`, `p.suffix`의 출력을 예측하라.
- 다음 복습: 2026-05-22
- 상태: open

## 2026-05-21 - Python json dump load functions

- 약점: Python에서 JSON 저장/읽기 함수 이름을 JavaScript/웹 계열 함수명과 혼동함.
- 근거: Python dict를 JSON 파일로 저장하는 함수로 `json.jsonify`, JSON 파일을 Python dict로 읽는 함수로 `json.parse`를 답함.
- 교정 설명: Python `json` 모듈에서 문자열 변환은 `json.dumps`/`json.loads`, 파일 저장/읽기는 `json.dump`/`json.load`를 사용한다. `JSON.parse`는 JavaScript의 함수명이고, `jsonify`는 Flask에서 응답을 JSON으로 만들 때 쓰는 이름이다.
- 재출제 문제: Python dict를 JSON 파일에 저장할 때와 JSON 파일을 Python dict로 읽을 때 각각 어떤 함수를 쓰는지 답하라.
- 다음 복습: 2026-05-22
- 상태: open

## Resolved

## 2026-05-21 - dict missing key access

- 약점: 없는 key를 `item["score"]`처럼 직접 접근하면 `None`이 반환된다고 예측함.
- 근거: `.get()` 차이를 설명할 때 `item["score"]`는 값이 없으면 `None`이 나온다고 답함.
- 교정 설명: `dict["missing_key"]`는 key가 없으면 `KeyError`를 발생시킨다. 기본값을 원하면 `dict.get("missing_key", default)`를 사용한다.
- 재출제 문제: `item = {"name": "Kim"}`에서 `item["score"]`와 `item.get("score", 0)`의 결과 차이를 설명하라.
- 다음 복습: 2026-05-22
- 상태: resolved - 재출제에서 없는 key 직접 접근이 `KeyError`임을 정확히 설명함.

## 2026-05-21 - JSON null to Python None

- 약점: JSON의 `null`이 Python에서 `NULL`로 변환된다고 표현함.
- 근거: `json.loads` 설명에서 "null을 파이썬에 맞는 NULL"로 자동 변환한다고 답함.
- 교정 설명: Python의 null-like 값은 `None`이다. `json.loads`는 JSON `null`을 Python `None`으로, JSON `true`/`false`를 Python `True`/`False`로 변환한다.
- 재출제 문제: `json.loads('{"active": true, "memo": null}')`의 결과에서 `active`와 `memo` 값이 Python에서 각각 무엇인지 예측하라.
- 다음 복습: 2026-05-22
- 상태: resolved - 재출제에서 JSON `true`와 `null`이 Python `True`, `None`으로 변환됨을 정확히 답함.

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
