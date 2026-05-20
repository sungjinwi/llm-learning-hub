# LLM Readiness Roadmap

이 로드맵은 LangChain, RAG, Agent, Graph RAG 중심의 LLM 활용 과정에 대비하기 위한 사전준비용이다.

## Day 4 - API And LLM Calls

- HTTP request/response 기본 감각
- JSON 요청과 응답
- 환경변수와 API key 관리
- OpenAI API 호출 구조
- 응답 파싱
- 에러 처리와 로그
- LLM Theory Lite: token, context window, next-token prediction

완료 산출물:

- `notes/api_llm_calls.md`
- `notes/llm_theory_lite.md`
- `exercises/day4_api_response_parsing.md`
- `exercises/day4_llm_theory_lite_api.md`

공식 문서 확인:

- OpenAI API 기본 호출
- API key 관리
- 모델과 파라미터

## Day 5 - Prompt And Structured Output

- system/user 메시지
- prompt versioning
- temperature와 출력 안정성
- structured output
- JSON output 검증
- 실패 사례 비교
- LLM Theory Lite: sampling, temperature, hallucination, grounding

완료 산출물:

- `notes/prompt_structured_output.md`
- `exercises/day5_prompt_eval_practice.md`
- `exercises/day5_llm_theory_lite_generation.md`

공식 문서 확인:

- OpenAI structured output
- OpenAI prompting 관련 가이드

## Day 6 - Embedding And RAG

- chunking
- embedding
- similarity search
- vector database
- retrieval 결과 확인
- generation과 retrieval 분리 디버깅
- LLM Theory Lite: embedding, similarity search, hallucination, grounding

완료 산출물:

- `notes/embedding_rag.md`
- `exercises/day6_rag_retrieval_practice.md`
- `exercises/day6_llm_theory_lite_embedding_rag.md`

공식 문서 확인:

- OpenAI embeddings
- LangChain retriever/vector store 사용법

## Day 7 - Mini LLM Project

- FAQ 문서 준비
- 문서 chunking
- 검색 결과 확인
- 답변 생성
- 로그 저장
- 간단 평가표 작성
- Gradio 또는 CLI 인터페이스
- LLM Theory Lite: evaluation, pretraining/fine-tuning/RLHF 개요, agent loop

완료 산출물:

- `projects/faq_qa_mini_project.md`
- `exercises/day7_llm_theory_lite_eval_agent.md`
- `../../05_outputs/projects/week1_llm_project_review.md`

공식 문서 확인:

- LangChain chain/retriever 구성
- Gradio 기본 UI

## 학습 시 공통 질문

1. 입력 데이터는 무엇인가?
2. 중간 데이터 구조는 무엇인가?
3. 출력은 무엇인가?
4. 실패한다면 검색, prompt, 모델 생성, UI 중 어디가 원인인가?
5. 공식 문서 기준으로 확인해야 할 API 동작은 무엇인가?
6. 이 실습과 연결되는 LLM Theory Lite 개념은 무엇인가?
