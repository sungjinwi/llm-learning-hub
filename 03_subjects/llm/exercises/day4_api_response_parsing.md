# Day 4 API And LLM Calls

## 적용 학습법

- 기본: 문서 기반 실습
- 보조: 역공학

## 목표

LLM API를 호출하기 전에 요청과 응답을 JSON 구조로 읽는 능력을 만든다.

정확한 OpenAI API 호출 방식은 학습 당일 공식 문서로 확인한다.

## 실습 1 - 요청 JSON 읽기

```python
request_body = {
    "model": "example-model",
    "messages": [
        {"role": "system", "content": "You are a helpful tutor."},
        {"role": "user", "content": "Python dict를 설명해줘."},
    ],
}

print(request_body["model"])
print(request_body["messages"][1]["content"])
```

질문:

1. `request_body`의 타입은 무엇인가?
2. `messages`의 타입은 무엇인가?
3. 두 번째 출력은 무엇인가?
4. system 메시지와 user 메시지는 역할이 어떻게 다를 것 같은가?

## 실습 2 - 응답 JSON 파싱

```python
response = {
    "id": "resp_123",
    "output": [
        {
            "type": "message",
            "content": [
                {"type": "output_text", "text": "dict는 key-value 쌍입니다."}
            ],
        }
    ],
}

text = response["output"][0]["content"][0]["text"]
print(text)
```

질문:

1. `text`에 도달하기 위해 어떤 key와 index를 거치는가?
2. 중첩 구조를 모르면 어떤 실수가 생길 수 있는가?
3. 실제 API 응답 구조는 왜 공식 문서로 확인해야 하는가?

## 실습 3 - API key 보안 점검

아래 설명 중 위험한 것을 고르고 이유를 설명한다.

1. API key를 `.env`에 저장하고 `.gitignore`에 추가한다.
2. API key를 코드 파일에 직접 적고 GitHub에 push한다.
3. 로그에 요청 본문을 남기되 key는 출력하지 않는다.

## 완료 기준

- API 요청과 응답을 dict/list 구조로 추적할 수 있다.
- API key를 코드에 직접 쓰면 안 되는 이유를 설명할 수 있다.
- 실제 API 사용법은 공식 문서 확인 후 최소 예제로 연결한다.
