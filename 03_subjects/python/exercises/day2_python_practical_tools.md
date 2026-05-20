# Day 2 Python Practical Tools

## 적용 학습법

- 기본: 출력 예측과 디버깅 격리
- 보조: 문서 기반 실습

## 목표

LLM API와 RAG 실습 전에 반드시 필요한 Python 실전 도구를 익힌다.

- `import`와 모듈
- `venv`, `pip`의 역할
- `pathlib` 경로 처리
- 파일 읽기와 쓰기
- JSON 읽기와 만들기
- `try/except`
- `assert`

## 실습 1 - pathlib 출력 예측

아래 코드는 독립 실행 가능한 예제다. 실행 전 출력과 이유를 먼저 예측한다.

```python
from pathlib import Path

base = Path("data")
file_path = base / "faq.json"

print(file_path)
print(file_path.suffix)
print(file_path.name)
```

답변 형식:

```md
1. 첫 번째 출력:
2. 두 번째 출력:
3. 세 번째 출력:
4. 이유:
```

## 실습 2 - JSON 구조 읽기

```python
import json

raw = '{"question": "배송은 얼마나 걸리나요?", "answer": "보통 2-3일 걸립니다."}'
item = json.loads(raw)

print(item["question"])
print(item["answer"])
```

질문:

1. `raw`의 타입은 무엇인가?
2. `item`의 타입은 무엇인가?
3. 두 줄의 출력은 무엇인가?
4. LLM API 응답을 다룰 때 왜 JSON 구조 이해가 중요한가?

## 실습 3 - 예외 처리 원인 찾기

```python
item = {"question": "환불 가능한가요?"}

try:
    print(item["answer"])
except KeyError as error:
    print("missing key:", error)
```

질문:

1. 이 코드는 왜 실패할 수 있는가?
2. 실제 출력은 무엇인가?
3. API 응답에서 없는 key에 접근할 때 `try/except`가 왜 필요한가?

## 완료 기준

- `Path` 객체와 문자열 경로의 차이를 설명할 수 있다.
- JSON 문자열과 Python `dict`의 차이를 설명할 수 있다.
- `KeyError`가 언제 발생하는지 설명할 수 있다.
- 작은 파일/JSON 처리 코드를 직접 작성할 수 있다.
