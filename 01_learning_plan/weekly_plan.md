# Weekly Plan

## Week 1 - LLM 활용 과정 사전준비

| 날짜 | Day | 목표 | 상태 |
| --- | --- | --- | --- |
| 2026-05-20 | 1 | Python Core: 변수, 조건문, 반복문, list, dict, function, class | completed |
| 2026-05-21 | 1 보충 | LLM 코드에서 자주 쓰는 indexing/slicing, string 기초, nested data 접근 | completed |
| 2026-05-21 | 2 | Python 실전 도구: import, venv, pip, pathlib, 파일 입출력, JSON, string 처리, try/except | in_progress |
| TBD | 3 | 데이터 다루기: CSV, Pandas 필터링, 결측치, groupby | not_started |
| TBD | 4 | API와 LLM 호출: 환경변수, request/response, OpenAI API 기본 구조, token/context window | not_started |
| TBD | 5 | Prompt와 구조화 출력: system/user 메시지, JSON output, prompt versioning, temperature/hallucination | not_started |
| TBD | 6 | Embedding과 RAG: chunking, embedding, vector search, retrieval 확인, grounding | not_started |
| TBD | 7 | 미니 LLM 프로젝트: FAQ 기반 QA, 로그, 간단 평가표, eval/agent loop | not_started |

## 운영 메모

하루에 모든 것을 완벽히 이해하려 하지 않는다. 각 Day의 완료 기준은 "설명할 수 있음", "작은 코드로 재현 가능", "오답이 기록됨"이다.

LLM 활용 과정 대비에서는 PyTorch보다 API, JSON, 문서 처리, RAG, 평가, 디버깅을 우선한다.

Day 1 보충은 별도 진도로 길게 늘리지 않는다. Day 2 시작 전에 10~20분 정도 `text[:200]`, `results[:3]`, `response["output"][0]` 같은 실제 LLM 코드 패턴으로 확인한다.

LLM Theory Lite는 별도 긴 이론 Day로 운영하지 않는다. Day 4~7에서 실습 전에 10~20분씩 연결 개념을 확인한다.
