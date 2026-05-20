# Python And LLM Readiness Roadmap

## Day 1 - Python Core

- 변수와 타입
- 조건문
- 반복문
- list, dict, tuple, string
- indexing and slicing
- function
- class의 최소 개념

완료 산출물:

- `notes/python_core.md`
- `questions/day1_active_recall.md`
- `exercises/day1_supplement_indexing_slicing.md`

## Day 2 - Python Practical Tools

- `import`와 모듈
- `venv`와 `pip`
- `pathlib` 경로 처리
- 파일 읽기와 쓰기
- JSON 읽기와 만들기
- string 조립과 f-string
- nested list/dict 접근
- `dict.get`
- `try/except`
- `assert` 기초

완료 산출물:

- `notes/python_practical_tools.md`
- `exercises/day2_python_practical_tools.md`

## Day 3 - Data Handling With Pandas

- CSV 읽기
- DataFrame 구조
- filter
- missing values
- groupby
- 간단한 데이터 요약
- list/dict comprehension과 DataFrame 변환 감각

완료 산출물:

- `notes/pandas_data_handling.md`
- `exercises/day3_pandas_data_handling.md`

## Day 4 - API And LLM Calls

- HTTP request/response 감각
- 환경변수와 API key 관리
- JSON 요청과 JSON 응답
- OpenAI API 호출 구조
- 응답 파싱
- 에러 처리와 로그
- LLM Theory Lite: token, context window, next-token prediction

완료 산출물:

- `../llm/notes/api_llm_calls.md`
- `../llm/notes/llm_theory_lite.md`
- `../llm/exercises/day4_api_response_parsing.md`
- `../llm/exercises/day4_llm_theory_lite_api.md`

## Day 5 - Prompt And Structured Output

- system/user 메시지
- prompt versioning
- temperature와 출력 안정성
- JSON output
- 실패 사례 비교
- 간단 평가 기준 만들기
- LLM Theory Lite: sampling, hallucination, grounding

완료 산출물:

- `../llm/notes/prompt_structured_output.md`
- `../llm/exercises/day5_prompt_eval_practice.md`
- `../llm/exercises/day5_llm_theory_lite_generation.md`

## Day 6 - Embedding And RAG

- chunking
- embedding
- similarity search
- vector database의 역할
- retrieval 결과 확인
- generation과 retrieval 분리 디버깅
- LLM Theory Lite: embedding, similarity search, grounding

완료 산출물:

- `../llm/notes/embedding_rag.md`
- `../llm/exercises/day6_rag_retrieval_practice.md`
- `../llm/exercises/day6_llm_theory_lite_embedding_rag.md`

## Day 7 - Mini LLM Project

- FAQ 문서 준비
- 문서 chunking
- 검색 결과 확인
- 답변 생성
- 로그 저장
- 간단 평가표 작성
- `range`, slicing, `enumerate`로 chunk와 검색 결과를 직접 점검
- LLM Theory Lite: evaluation, 모델 학습 방식 개요, agent loop

완료 산출물:

- `../llm/projects/faq_qa_mini_project.md`
- `../llm/exercises/day7_llm_theory_lite_eval_agent.md`
- `../../05_outputs/projects/week1_llm_project_review.md`

## Later - PyTorch Supplement

- tensor creation
- shape manipulation
- autograd
- nn.Module
- training loop

PyTorch는 LLM 활용 과정의 직접 선행 지식이 아니라 보충 주제로 다룬다.

## Later - LLM Theory Deepening

아래 내용은 단기 사전준비에서는 깊게 다루지 않고, 1주 이후 필요할 때 확장한다.

- transformer 구조
- attention 세부 동작
- tokenizer 세부 구현
- model training loop
- fine-tuning 실습
- RLHF/RLAIF 세부 과정
- inference optimization
