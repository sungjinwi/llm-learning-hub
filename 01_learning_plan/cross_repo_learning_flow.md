# Cross Repo Learning Flow

작성일: 2026-05-20

## 목적

이 문서는 메인 LLM 학습 repo와 전문 interaction engineering repo를 끊기지 않게 연결하기 위한 운영 규칙이다.

## Repo 역할

| Repo | 권장 폴더명 | 역할 |
| --- | --- | --- |
| Main learning hub | `D:\llm-learning-hub` | Python, JSON, API, LLM Theory Lite, RAG, 미니 프로젝트의 메인 학습 흐름 |
| Interaction engineering lab | `D:\llm-interaction-engineering` | Prompt, Context, Harness, Eval, Guardrail 전문 실습 |

## 기본 원칙

매일 학습은 `D:\llm-learning-hub`에서 시작한다.

`D:\llm-interaction-engineering`은 별도 과정처럼 끊어서 들어가는 곳이 아니라, 메인 학습 중 특정 주제에서 필요한 전문 실습을 수행하는 lab이다.

기본 흐름:

```text
메인 학습 주제 확인
-> 필요한 경우 interaction lab 연결 실습
-> 결과를 다시 메인 학습 기록에 요약
```

## Day별 연결 규칙

| Main Day | Main 주제 | Interaction lab 연결 |
| --- | --- | --- |
| Day 4 | API와 LLM 호출 | 공식 문서 기반 prompt, API 질문 구조화 |
| Day 5 | Prompt와 structured output | Prompt Engineering Day 1~4 |
| Day 6 | Embedding과 RAG | Context Engineering Day 5~6 |
| Day 7 | Mini LLM Project | Harness Engineering Day 10~14 |
| 1주 이후 | Agent, LangGraph, 운영 개선 | Eval harness, guardrail, logging, permission boundary |

## 전환 조건

아래 상황이면 interaction lab으로 연결한다.

- prompt의 목표, 제약, 출력 형식이 불명확할 때
- RAG context를 어떻게 넣어야 할지 판단이 필요할 때
- 검색 결과, user input, tool result를 분리해야 할 때
- prompt 변경 전후를 평가표로 비교해야 할 때
- agent나 workflow의 tool 권한, 검증, 로그, 실패 처리를 설계해야 할 때

아래 상황이면 main learning hub에 머문다.

- Python 문법, 파일 처리, JSON 처리, API 응답 파싱을 배우는 중일 때
- Pandas, CSV, 평가 데이터 처리를 배우는 중일 때
- LLM Theory Lite의 최소 개념을 처음 배우는 중일 때
- 작은 코드 실습이나 출력 예측이 주된 목표일 때

## 전환 안내 형식

AI는 repo를 전환할 때 다음 형식으로 안내한다.

```md
오늘의 메인 학습:
- repo: D:\llm-learning-hub
- 주제:
- 완료할 실습:

연결 실습:
- repo: D:\llm-interaction-engineering
- 파일:
- 목적:

다시 메인 repo에 남길 기록:
- 배운 점:
- 약점:
- 다음 복습:
```

## 기록 규칙

interaction lab에서 수행한 실습 결과는 lab repo에 상세히 남긴다.

메인 repo에는 다음만 요약한다.

- 어떤 연결 실습을 했는가
- 왜 연결했는가
- 메인 학습에 어떤 판단 기준이 추가되었는가
- 다음에 다시 확인할 약점은 무엇인가

## 예시

### Day 5 Prompt 연결

```md
오늘의 메인 학습:
- repo: D:\llm-learning-hub
- 주제: Day 5 Prompt와 structured output

연결 실습:
- repo: D:\llm-interaction-engineering
- 파일: 03_subjects/prompt_engineering/exercises/day2_prompt_quality_check.md
- 목적: prompt의 모호함, 누락, 충돌을 찾는 연습

다시 메인 repo에 남길 기록:
- JSON output을 요구할 때는 출력 schema와 실패 조건을 함께 적어야 함.
```

### Day 6 RAG 연결

```md
오늘의 메인 학습:
- repo: D:\llm-learning-hub
- 주제: Day 6 Embedding과 RAG

연결 실습:
- repo: D:\llm-interaction-engineering
- 파일: 03_subjects/context_engineering/exercises/day6_rag_context_grounding.md
- 목적: 검색된 chunk, 사용자 질문, 지시문을 분리하는 context packet 작성

다시 메인 repo에 남길 기록:
- retrieval 결과가 맞아도 generation에서 근거 없는 답을 만들 수 있으므로 grounding 조건이 필요함.
```
