# Day 7 FAQ QA Mini Project

## 적용 학습법

- 기본: 프로젝트 기반 학습
- 보조: 코드 리뷰와 역공학

## 목표

작은 FAQ 문서를 기반으로 질문에 답하는 QA 흐름을 설계한다.

처음부터 LangChain 전체 코드를 붙이지 않는다. 먼저 Python 함수 수준에서 입력, 처리, 출력을 검증한 뒤 API/RAG/UI를 붙인다.

이론 연결:

- evaluation: 답변 품질을 감이 아니라 기준으로 판단한다.
- pretraining/fine-tuning/RLHF 개요: 모델이 무엇을 알고 무엇을 모를 수 있는지 이해한다.
- agent loop: context gathering, action, verification 흐름으로 프로젝트를 점검한다.

관련 보충 실습:

- `../exercises/day7_llm_theory_lite_eval_agent.md`

## 프로젝트 템플릿

```md
프로젝트 이름:

풀 문제:

사용자 질문 예시:

FAQ 문서 예시:

입력:

중간 처리:

출력:

실패 조건:

공식 문서 확인이 필요한 부분:

- OpenAI API:
- LangChain:
- Gradio:

LLM Theory Lite 확인:

- token/context window:
- embedding/similarity search:
- hallucination/grounding:
- evaluation:
- agent loop:

1단계 문서 로딩:
2단계 chunking:
3단계 retrieval:
4단계 답변 생성:
5단계 로그 저장:
6단계 평가:
7단계 UI 또는 CLI:

내가 먼저 구현할 최소 버전:

막힌 부분:
```

## 최소 버전 기준

처음 구현할 최소 버전은 다음만 만족해도 된다.

1. FAQ 문서 3개를 Python list/dict로 표현한다.
2. 사용자 질문 하나를 받는다.
3. 가장 관련 있어 보이는 문서 하나를 고른다.
4. 선택한 문서와 답변을 함께 출력한다.
5. 왜 그 문서를 골랐는지 설명한다.

## 평가표 예시

| 질문 | 검색된 문서 | 정답 근거 있음 | 답변 정확 | 실패 원인 |
| --- | --- | --- | --- | --- |
| 배송은 얼마나 걸리나요? | shipping.md | yes | yes | none |
| 환불은 며칠 안에 되나요? | shipping.md | no | no | retrieval |

## 완료 기준

- 전체 흐름을 입력, 처리, 출력으로 설명할 수 있다.
- 검색 실패와 생성 실패를 구분할 수 있다.
- evaluation 기준과 agent loop 관점으로 프로젝트를 설명할 수 있다.
- API key를 코드에 직접 쓰지 않는다.
- 최소 3개 질문에 대해 평가표를 작성한다.
- AI가 만든 코드라도 주요 변수와 데이터 구조를 설명할 수 있다.
