# Master Plan

이 학습 시스템의 1주 계획은 모두의연구소 LLM 서비스 개발 과정 사전준비에 맞춰 운영한다.

참고 과정: https://camp.modulabs.co.kr/llm

## 전체 목표

7일 동안 Python 기초에서 시작해 LLM API, JSON, 문서 처리, RAG, 간단한 FAQ 기반 QA 프로젝트까지 연결한다. LLM 내부 이론은 별도 장기 과정으로 깊게 다루지 않고, Day 4~7에 필요한 최소 이론을 `LLM Theory Lite` 보조 트랙으로 함께 학습한다.

목표는 모델을 직접 학습시키는 것이 아니라 다음 네 가지다.

1. Python과 데이터 구조를 읽고 설명할 수 있게 한다.
2. LLM API 요청과 응답을 JSON 구조로 이해한다.
3. RAG를 검색과 생성 단계로 나누어 디버깅할 수 있게 한다.
4. AI가 만든 코드도 입력, 처리, 출력, 실패 가능성 기준으로 검토할 수 있게 한다.
5. token, context window, next-token prediction, embedding, hallucination, evaluation 같은 최소 이론을 활용 판단과 연결한다.

## 7일 커리큘럼

| Day | 주제 | 핵심 산출물 | 기본 학습법 |
| --- | --- | --- | --- |
| 1 | Python Core | 변수, 조건문, 반복문, list, dict, indexing/slicing, function, class 노트 | 소크라테스 문답, 능동적 회상 |
| 2 | Python 실전 도구 | import, venv, pip, pathlib, 파일 입출력, JSON, string 처리, try/except 실습 | 출력 예측, 디버깅 격리 |
| 3 | 데이터 다루기 | CSV 읽기, Pandas 필터링, 결측치, groupby 실습 | 단계별 출력 추적 |
| 4 | API와 LLM 호출 | 환경변수, request/response, OpenAI API 기본 호출 구조, token/context window 노트 | 문서 기반 실습, 역공학 |
| 5 | Prompt와 구조화 출력 | system/user 메시지, JSON output, prompt versioning, temperature/hallucination 비교 | 능동적 회상, 비교 실습 |
| 6 | Embedding과 RAG | chunking, embedding, vector search, retrieval 결과 확인, grounding 실습 | 역공학, 검색 결과 평가 |
| 7 | 미니 LLM 프로젝트 | FAQ 문서 기반 QA, 간단 UI 또는 CLI, 로그, 평가표, agent loop 개요 | 프로젝트 기반 학습, 코드 리뷰 |

## LLM Theory Lite 보조 트랙

LLM 이론은 수식과 모델 학습 구현을 목표로 하지 않는다. 현재 목표는 LLM 활용 과정에서 판단력을 주는 최소 개념을 익히는 것이다.

| 연결 Day | 이론 개념 | 필요한 이유 |
| --- | --- | --- |
| Day 4 | token, context window, next-token prediction | API 비용, 입력 길이, 모델 생성 방식 이해 |
| Day 5 | sampling, temperature, hallucination, structured output | 출력 안정성, 근거 없는 답변, JSON 검증 이해 |
| Day 6 | embedding, similarity search, grounding | RAG 검색과 답변 근거 확인 이해 |
| Day 7 | evaluation, pretraining/fine-tuning/RLHF 개요, agent loop | 평가표, 모델 한계, agent 검증 루프 이해 |

완료 산출물:

- `03_subjects/llm/notes/llm_theory_lite.md`
- `03_subjects/llm/exercises/day4_llm_theory_lite_api.md`
- `03_subjects/llm/exercises/day5_llm_theory_lite_generation.md`
- `03_subjects/llm/exercises/day6_llm_theory_lite_embedding_rag.md`
- `03_subjects/llm/exercises/day7_llm_theory_lite_eval_agent.md`
- `01_learning_plan/llm_theory_lite_coverage_check.md`

## PyTorch의 위치

PyTorch Tensor, Autograd, Training Loop는 중요하지만 이 과정의 직접 사전준비에서는 우선순위가 낮다.

LLM 활용 과정에서 먼저 필요한 것은 다음이다.

- Python 자료구조
- indexing/slicing과 nested data 접근
- 파일과 JSON 처리
- API 호출과 응답 파싱
- token과 context window
- next-token prediction과 hallucination
- 문서 chunking
- embedding과 vector search
- grounding과 evaluation
- RAG 평가
- LangChain/LangGraph 코드의 입력과 출력 추적

PyTorch는 1주 사전준비 이후 보충 주제로 다룬다.

## 매일 완료 기준

하루 학습은 다음 조건을 만족해야 완료로 본다.

- 핵심 개념 노트 1개 이상 작성
- 능동적 회상 문제 5개 이상 풀이
- 작은 코드 실습 또는 출력 예측 1개 이상 완료
- 틀린 문제 또는 헷갈린 개념을 `06_tracking/weak_points.md`에 기록
- 다음 복습 항목을 `06_tracking/review_schedule.md`에 기록
- 오늘 배운 내용을 5문장 이내로 파인만식 설명

## 신뢰성 기준

정확도가 중요한 내용은 공식 문서를 우선 확인한다.

- OpenAI API, 모델, 파라미터, 구조화 출력, tool calling: OpenAI 공식 문서
- LangChain, LangGraph: LangChain 공식 문서
- Gradio: Gradio 공식 문서
- Pandas, NumPy, scikit-learn: 각 프로젝트 공식 문서
- Python 문법과 표준 라이브러리: Python 공식 문서

단순 개념 복습이나 이미 검증된 기초 문법은 매번 문서를 찾지 않아도 된다. 하지만 API 사용법, 옵션, 최신 모델, 보안, 평가 지표, 라이브러리 동작처럼 바뀔 수 있거나 오해 비용이 큰 부분은 공식 문서 기반으로 설명한다.

## 1주 이후 보완 계획

1주 이후에는 속도보다 검증을 우선한다.

- LangChain 공식 문서 읽기
- OpenAI API 공식 예제 역공학
- RAG 실패 사례 모으기
- AI 없이 작은 기능 구현
- 기존 코드에 로그를 넣어 데이터 흐름 추적
- list/dict comprehension, `range`, `enumerate`를 실제 RAG 코드에서 다시 확인
- PyTorch 기초를 선택 보충
