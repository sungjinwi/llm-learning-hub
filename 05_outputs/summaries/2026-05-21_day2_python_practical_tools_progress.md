# 2026-05-21 학습 기록 - Day 2 Python Practical Tools 진행

## 1. 오늘의 목표

Day 2로 넘어가기 전에 Day 1 보충 개념을 확인하고, LLM API/RAG 실습에 필요한 Python 실전 도구를 익힌다.

## 2. 수행한 실습

- Day 1 복습: `list`, `dict`, `class`, parameter/argument
- Day 1 보충: slicing, string preview, nested data 접근, `enumerate`
- Day 2 실습: `pathlib`, JSON `loads`/`dump`/`load`, f-string, `.get()`, `KeyError`, `try/except`, `assert`, `with open`
- Day 2 마무리 빈칸 구현: JSON 파일 저장, 다시 읽기, `assert` 검증, f-string 출력

## 3. 핵심 개념

- Python slicing에서 `start`는 포함되고 `end`는 포함되지 않는다.
- `Path.name`은 확장자를 포함하고, `Path.stem`은 확장자를 제외한 파일명이다.
- JSON 문자열은 `json.loads`, JSON 파일은 `json.load`로 읽는다.
- Python 자료구조를 JSON 문자열로 만들 때는 `json.dumps`, 파일에 저장할 때는 `json.dump`를 쓴다.
- 없는 key를 직접 접근하면 `KeyError`가 나고, 기본값이 필요하면 `.get()`을 쓴다.
- `with open(...) as file`은 파일을 열고 블록 종료 시 자동으로 닫는다.

## 4. 내가 직접 설명한 내용

- JSON은 API 요청/응답에서 구조화된 데이터를 주고받기 위한 공통 형식이다.
- f-string은 Python 내부에서 처리한 `dict`/`list` 결과를 사용자 메시지, prompt, 로그로 조립할 때 유용하다.
- `assert`는 조건이 `False`일 때 실행을 멈추고 `AssertionError`를 낸다.

## 5. 틀렸거나 헷갈린 부분

- `results[:3]`에서 end index가 포함된다고 예측함.
- `Path.name`을 확장자 없는 파일명으로 예측함.
- Python JSON 파일 저장/읽기 함수명에서 `jsonify`, `parse`와 혼동함.

## 6. 교정된 설명

- `results[:3]`은 index 0, 1, 2만 가져온다.
- `Path.name == "file.json"`, `Path.stem == "file"`, `Path.suffix == ".json"`이다.
- Python에서는 `json.dump`/`json.load`가 파일 대상이고, `json.dumps`/`json.loads`가 문자열 대상이다.

## 7. 코드 예시

```python
from pathlib import Path
import json

data = {"name": "Kim", "score": 90}
path = Path("student.json")

with open(path, "w") as file:
    json.dump(data, file)

with open(path, "r") as file:
    loaded = json.load(file)

assert loaded["score"] >= 60

message = f"{loaded['name']} passed"
print(message)
```

## 8. 다음 복습 문제

- `items = ["a", "b", "c", "d"]; items[1:3]`의 결과 예측
- `Path("logs/app/error.txt")`에서 `name`, `stem`, `suffix` 예측
- `json.dump`와 `json.dumps`, `json.load`와 `json.loads` 차이 설명

## 9. 다음 학습과의 연결

Day 2는 아직 `in_progress`다. 다음 시간에는 `import`/모듈, `venv`/`pip`의 역할을 확인하고 Day 2를 마무리한다.

## 10. NotebookLM/슬라이드 구성안

- Python 파일/JSON 처리 흐름
- API 응답 파싱을 위한 nested data와 missing key 처리
- 실수하기 쉬운 이름: `name/stem/suffix`, `dump/dumps`, `load/loads`
