# Practice Index

학습 중 코드 실습이 필요하면 여기서 현재 Day에 맞는 파일을 고른다.

## Week 1 - LLM 활용 과정 사전준비

| Day | 주제 | 실습 파일 |
| --- | --- | --- |
| 1 | Python core | `day1_python_core_practice.md` |
| 1 보충 | Indexing, slicing, string, nested data | `day1_supplement_indexing_slicing.md` |
| 2 | Python practical tools | `day2_python_practical_tools.md` |
| 3 | Pandas data handling | `day3_pandas_data_handling.md` |
| 4 | API and LLM calls | `../../llm/exercises/day4_api_response_parsing.md` |
| 4 보충 | LLM theory lite: token, context window, next-token prediction | `../../llm/exercises/day4_llm_theory_lite_api.md` |
| 5 | Prompt and structured output | `../../llm/exercises/day5_prompt_eval_practice.md` |
| 5 보충 | LLM theory lite: temperature, hallucination, grounding | `../../llm/exercises/day5_llm_theory_lite_generation.md` |
| 6 | Embedding and RAG | `../../llm/exercises/day6_rag_retrieval_practice.md` |
| 6 보충 | LLM theory lite: embedding, similarity search, RAG failure | `../../llm/exercises/day6_llm_theory_lite_embedding_rag.md` |
| 7 | Mini LLM project | `../../llm/projects/faq_qa_mini_project.md` |
| 7 보충 | LLM theory lite: eval, model training overview, agent loop | `../../llm/exercises/day7_llm_theory_lite_eval_agent.md` |

## 보류된 보충 실습

아래 주제는 LLM 활용 과정 사전준비 이후 필요할 때 보충한다.

- NumPy broadcasting
- scikit-learn pipeline
- PyTorch tensor/autograd
- training loop

## LLM 코드에서 자주 다시 등장하는 Python 기초

아래 항목은 별도 긴 이론보다 Day별 실습에서 반복 확인한다.

- indexing/slicing: 문서 preview, top-k 검색 결과 확인, chunking
- string/f-string: prompt 조립, 로그 메시지 작성
- nested list/dict 접근: API 응답, JSON, metadata
- `dict.get`: optional field와 누락 key 처리
- list/dict comprehension: 평가 로그와 문서 목록 가공
- `range`, `enumerate`: chunk 번호, 검색 결과 순위, 반복 디버깅

## LLM Theory Lite 연결 개념

아래 항목은 별도 긴 이론 강의보다 Day 4~7 실습 앞뒤에 짧게 확인한다.

- token/context window: API 비용, 긴 문서 처리, RAG 필요성
- next-token prediction: LLM이 정답 조회기가 아니라 생성 모델이라는 감각
- temperature/sampling: 출력 안정성과 다양성
- hallucination/grounding: 근거 없는 답변과 문서 기반 답변의 차이
- embedding/similarity search: RAG 검색의 기본 원리
- evaluation: prompt, RAG, model 변경을 기준으로 비교하는 방법
- agent loop: context gathering, action, verification, retry/report

## 사용 규칙

1. 사용자의 질문을 `04_ai_prompts/method_router.md`로 분류한다.
2. 해당 Day 또는 주제의 실습 파일을 연다.
3. 정확도가 중요한 API, 라이브러리, 평가 지표는 `04_ai_prompts/official_docs_policy.md`를 확인한다.
4. 정답을 먼저 보여주지 않는다.
5. 사용자가 답하거나 코드를 작성하면 채점한다.
6. 틀린 내용은 `06_tracking/weak_points.md`에 추가할 형식으로 정리한다.
