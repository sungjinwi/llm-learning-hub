# Day 1 Supplement - Indexing, Slicing, String, Nested Data

## 목적

Day 1은 완료 상태로 유지한다. 이 파일은 Day 2로 넘어가기 전에 LLM/API/RAG 코드에서 자주 쓰이는 Python 기초를 10~20분만 보강하기 위한 실습이다.

## 왜 필요한가

- `text[:200]`: 긴 문서나 prompt 앞부분만 확인한다.
- `results[:3]`: 검색 결과 top 3개만 확인한다.
- `response["output"][0]["content"][0]`: API 응답의 nested JSON 구조를 따라간다.
- `for i, chunk in enumerate(chunks)`: chunk 번호와 내용을 함께 확인한다.

## 실습 1 - list slicing

```python
results = ["doc1", "doc2", "doc3", "doc4", "doc5"]

print(results[0])
print(results[:3])
print(results[2:])
print(results[-1])
```

질문:

1. 네 줄의 출력은 각각 무엇인가?
2. `results[:3]`은 몇 개의 값을 가져오는가?
3. `results[-1]`은 어떤 상황에서 유용한가?

## 실습 2 - string slicing

```python
text = "환불은 상품 수령 후 7일 이내 가능합니다."

preview = text[:10]
print(preview)
print(len(text))
```

질문:

1. `preview`에는 어떤 문자열이 들어가는가?
2. 긴 문서를 LLM에 넣기 전에 앞부분만 확인하는 이유는 무엇인가?

## 실습 3 - nested data 접근

```python
response = {
    "output": [
        {
            "content": [
                {"text": "dict는 key-value 쌍입니다."}
            ]
        }
    ]
}

text = response["output"][0]["content"][0]["text"]
print(text)
```

질문:

1. `text`까지 도달하는 경로를 순서대로 설명하라.
2. `output`이 list이기 때문에 필요한 표기법은 무엇인가?
3. 이런 구조를 모르면 API 응답 파싱에서 어떤 실수가 생기는가?

## 실습 4 - enumerate

```python
chunks = ["배송 안내", "환불 안내", "교환 안내"]

for index, chunk in enumerate(chunks):
    print(index, chunk)
```

질문:

1. 출력은 무엇인가?
2. RAG에서 chunk 번호를 함께 출력하면 어떤 점이 좋은가?

## 완료 기준

- `list[start:end]`에서 `start`는 포함되고 `end`는 포함되지 않는다고 설명할 수 있다.
- string도 list처럼 slicing할 수 있음을 설명할 수 있다.
- nested `dict`/`list` 구조에서 key와 index를 구분해 따라갈 수 있다.
- `enumerate`가 index와 값을 함께 준다고 설명할 수 있다.
