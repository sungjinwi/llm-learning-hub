# Python Practical Tools Notes

## 상태

in_progress

## 오늘 확인한 개념

- `Path("data") / "file.json"`처럼 `Path` 객체에서 `/`는 경로 결합으로 동작한다.
- `Path.name`은 확장자를 포함한 마지막 경로 요소이고, `Path.stem`은 확장자를 제외한 이름이며, `Path.suffix`는 확장자다.
- JSON은 API 요청과 응답에서 자주 쓰이는 텍스트 기반 구조화 데이터 형식이다.
- `json.loads(raw)`는 JSON 문자열을 Python 자료구조로 바꾼다.
- `json.dumps(data)`는 Python 자료구조를 JSON 문자열로 바꾼다.
- `json.dump(data, file)`은 Python 자료구조를 JSON 파일에 저장한다.
- `json.load(file)`은 JSON 파일을 Python 자료구조로 읽는다.
- JSON `null`은 Python `None`, JSON `true`/`false`는 Python `True`/`False`로 변환된다.
- f-string은 변수, dict 값, 계산 결과를 prompt, 로그, 사용자 메시지용 문자열로 조립할 때 쓴다.
- 없는 key를 `dict["key"]`로 직접 접근하면 `KeyError`가 발생한다.
- `dict.get("key", default)`는 key가 없을 때 기본값을 반환한다.
- `try/except KeyError`는 누락 key 접근 실패를 잡아 처리할 때 쓴다.
- `assert 조건식`은 조건이 `False`일 때 `AssertionError`를 발생시킨다.
- `with open(path, "w") as file:`은 파일을 쓰기 모드로 열고, 블록이 끝나면 자동으로 닫는다.
- `with open(path, "r") as file:`은 파일을 읽기 모드로 연다.

## 아직 남은 확인

- `import`와 모듈의 역할
- `venv`와 `pip`의 역할
- Day 2 전체 내용을 5문장 이내로 파인만식 설명

## 다음에 다시 물어볼 질문

1. `Path.name`, `Path.stem`, `Path.suffix`는 각각 무엇을 반환하는가?
2. `json.dump`와 `json.dumps`의 차이는 무엇인가?
3. `dict["missing"]`과 `dict.get("missing")`의 차이는 무엇인가?
4. `with open(..., "w")`와 `with open(..., "r")`의 차이는 무엇인가?
