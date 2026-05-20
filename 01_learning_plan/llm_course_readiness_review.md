# LLM Course Readiness Review

작성일: 2026-05-20

참고 과정: https://camp.modulabs.co.kr/llm

## 과정 성격 판단

해당 과정은 딥러닝 모델을 직접 학습시키는 과정이라기보다, LLM을 활용해 실제 서비스를 만드는 과정에 가깝다.

페이지 기준 핵심 키워드는 다음과 같다.

- LangChain
- OpenAI API
- Gradio
- 문서 처리
- 벡터 데이터베이스
- RAG
- 검색 성능 평가
- 답변 성능 평가
- LangGraph
- Agent
- 비정형 문서 처리
- 멀티모달 RAG
- Graph RAG

따라서 사전준비는 PyTorch 내부 원리보다 Python 실전 문법, API 호출, JSON, 문서 처리, 검색, 평가, 디버깅 능력을 우선해야 한다.

## 현재 계획의 장점

현재 7일 계획은 다음 점에서 좋다.

- Python 기본 문법부터 시작한다.
- 출력 예측과 빈칸 코드로 직접 생각하게 만든다.
- 약점을 기록하고 다음 복습에 반영한다.
- Pandas, sklearn, PyTorch로 AI 개발의 큰 흐름을 경험하게 한다.
- AI가 작성한 코드를 역공학하도록 유도한다.

이 방식은 LLM 과정에서 코드 복붙만 하다가 구조를 놓치는 문제를 줄이는 데 도움이 된다.

## 현재 계획의 부족한 점

LLM 활용 중심 과정 기준으로는 다음이 부족하다.

- API 호출과 응답 구조 이해
- JSON 읽기와 만들기
- `.env`와 API key 관리
- HTTP 기본 개념
- 문서 로딩, chunking, metadata 관리
- embedding과 vector search의 의미
- RAG에서 retrieval과 generation을 분리해 디버깅하는 습관
- prompt 결과를 감이 아니라 기준으로 평가하는 방법
- LangChain 코드를 무작정 쓰지 않고 입력, 처리, 출력 흐름으로 읽는 훈련
- 비용, latency, rate limit 같은 운영 감각

## 권장 사전준비 순서

기존 7일 계획을 LLM 활용 과정에 맞추면 다음 순서가 더 적합하다.

| Day | 주제 | 목표 |
| --- | --- | --- |
| 1 | Python Core | 변수, 조건문, 반복문, list, dict, indexing/slicing, function, class 최소 개념 |
| 2 | Python 실전 도구 | import, venv, pip, pathlib, 파일 입출력, JSON, string 처리, nested data, try/except |
| 3 | 데이터 다루기 | Pandas 기초, CSV 읽기, 결측치, 필터링, groupby, list/dict 로그 변환 |
| 4 | API와 LLM 호출 | REST API 감각, request/response, OpenAI API 기본 호출, 환경변수 |
| 5 | Prompt와 구조화 출력 | system/user 메시지, JSON output, prompt versioning, 실패 케이스 비교 |
| 6 | Embedding과 RAG | chunking, embedding, vector search, retrieval 결과 확인 |
| 7 | 미니 LLM 프로젝트 | FAQ 문서 기반 QA, Gradio UI, 로그, 간단 평가표 |

PyTorch Tensor와 Training Loop는 중요하지만, 이 과정의 직접 선행 지식으로는 우선순위가 낮다. 교육과정 중 모델 내부 원리를 설명할 때 보조 지식으로 다루는 편이 낫다.

## 2026-05-20 반영 상태

위 권장 순서는 다음 파일에 반영되었다.

- `01_learning_plan/master_plan.md`
- `01_learning_plan/weekly_plan.md`
- `03_subjects/python/roadmap.md`
- `03_subjects/llm/roadmap.md`
- `06_tracking/progress_dashboard.md`
- `03_subjects/python/exercises/practice_index.md`
- `03_subjects/python/exercises/day2_python_practical_tools.md`
- `03_subjects/python/exercises/day3_pandas_data_handling.md`
- `03_subjects/llm/exercises/day4_api_response_parsing.md`
- `03_subjects/llm/exercises/day5_prompt_eval_practice.md`
- `03_subjects/llm/exercises/day6_rag_retrieval_practice.md`
- `03_subjects/llm/projects/faq_qa_mini_project.md`

정확도가 중요한 파트에서 공식 문서를 우선 확인하는 규칙은 다음 파일에 반영되었다.

- `AI_STUDY_OPERATING_RULES.md`
- `04_ai_prompts/method_router.md`
- `04_ai_prompts/official_docs_policy.md`
- `01_learning_plan/daily_routine.md`

## 꼭 추가할 Python 개념

- `import`와 모듈 구조
- `venv`, `pip`, 패키지 설치
- `.env` 파일과 환경변수
- `pathlib`로 경로 다루기
- 파일 읽기와 쓰기
- JSON 직렬화와 역직렬화
- `try/except` 예외 처리
- 함수 scope
- indexing과 slicing
- string method와 f-string
- nested list/dict 접근
- `dict.get`과 누락 key 처리
- `range`, `enumerate`, `zip`
- list/dict comprehension
- `assert`로 간단 테스트하기
- 에러 메시지 읽기와 최소 재현 코드 만들기

## 2026-05-20 추가 보강 판단

전체 흐름은 유지하되, 이후 Day에서 자연스럽게 필요해지는 Python 연결 개념을 명시적으로 추가했다.

추가한 이유:

- slicing은 문서 preview, top-k 검색 결과 확인, chunking에서 반복 사용된다.
- string/f-string은 prompt 조립과 로그 작성의 기본이다.
- nested list/dict 접근은 API 응답과 JSON 파싱의 핵심이다.
- `dict.get`과 `try/except`는 누락 field를 다룰 때 필요하다.
- list/dict comprehension은 평가 로그와 문서 목록을 다룰 때 자주 등장한다.
- `range`와 `enumerate`는 chunk 번호, 검색 결과 순위, 반복 디버깅에 필요하다.

## 꼭 추가할 LLM 개념

- token과 context window
- next-token prediction
- sampling과 temperature
- prompt, system message, user message
- temperature와 출력 안정성
- structured output
- embedding
- similarity search
- vector database
- RAG의 3단계: chunking, retrieval, generation
- hallucination과 grounding
- 평가 기준: 검색 평가와 답변 평가를 분리
- API 비용, latency, rate limit
- API key 보안
- 로그와 재현 가능성

## 2026-05-20 LLM Theory Lite 반영

LLM 이론은 별도 장기 과정으로 분리하지 않고 Day 4~7의 보조 트랙으로 추가했다.

반영한 이유:

- LLM 활용 과정에서도 token, context window, hallucination, embedding, evaluation을 모르면 API/RAG/prompt 품질을 표면적으로만 이해하게 된다.
- 반대로 transformer 수식, training loop, PyTorch 내부 구현까지 단기간에 깊게 들어가면 현재 과정 대비 효율이 낮다.
- 따라서 필요한 이론을 실습 직전에 10~20분씩 연결하는 방식이 적합하다.

반영 파일:

- `03_subjects/llm/notes/llm_theory_lite.md`
- `03_subjects/llm/exercises/day4_llm_theory_lite_api.md`
- `03_subjects/llm/exercises/day5_llm_theory_lite_generation.md`
- `03_subjects/llm/exercises/day6_llm_theory_lite_embedding_rag.md`
- `03_subjects/llm/exercises/day7_llm_theory_lite_eval_agent.md`
- `01_learning_plan/llm_theory_lite_coverage_check.md`

누락 방지 체크:

- API 사용 판단: token, context window, next-token prediction
- Prompt 평가: temperature, hallucination, grounding, structured output
- RAG 이해: embedding, similarity search, retrieval/generation 분리
- 프로젝트 검증: evaluation, 모델 학습 방식 개요, agent loop
- 장기 보류: transformer 세부 수식, PyTorch training loop, 모델 직접 fine-tuning 구현

## 학습 운영 권장

매일 다음 질문을 포함한다.

1. 이 코드의 입력은 무엇인가?
2. 중간 데이터 구조는 무엇인가?
3. 출력은 무엇인가?
4. 실패한다면 어느 단계에서 실패할 가능성이 큰가?
5. AI가 준 코드 중 내가 설명하지 못하는 줄은 어디인가?

LLM 서비스 개발에서는 정답 코드보다 데이터 흐름을 읽는 능력이 더 중요하다.
