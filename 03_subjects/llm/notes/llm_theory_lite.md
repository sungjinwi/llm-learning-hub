# LLM Theory Lite

## 목적

이 노트는 LLM을 직접 학습시키기 위한 딥러닝 수업이 아니라, LLM API, prompt, RAG, agent, evaluation을 이해하고 디버깅하기 위해 필요한 최소 이론을 정리한다.

핵심 목표는 수식을 외우는 것이 아니라 다음 질문에 답할 수 있게 되는 것이다.

1. 왜 LLM은 자연스럽게 틀릴 수 있는가?
2. 왜 context window와 token 관리가 중요한가?
3. 왜 RAG는 검색과 생성을 나누어 디버깅해야 하는가?
4. 왜 embedding과 similarity search가 문서 검색에 쓰이는가?
5. 왜 prompt, context, harness, eval이 함께 필요해지는가?

## Day별 연결

| 연결 Day | 이론 개념 | 연결되는 실습 |
| --- | --- | --- |
| Day 4 | token, context window, next-token prediction | API 요청/응답, 비용, 응답 생성 방식 |
| Day 5 | sampling, temperature, structured output | 출력 안정성, JSON output, prompt version 비교 |
| Day 6 | embedding, similarity search, hallucination, grounding | RAG retrieval, vector search, 검색/생성 분리 |
| Day 7 | evaluation, pretraining/fine-tuning/RLHF 개요, agent loop | 미니 프로젝트, 평가표, 실패 원인 분류 |

## 1. Token

LLM은 문장을 글자나 단어 그대로가 아니라 token 단위로 처리한다.

왜 중요한가:

- 입력과 출력 비용은 token 수에 영향을 받는다.
- context window는 token 단위로 제한된다.
- 긴 문서, 긴 대화, 많은 검색 결과를 모두 넣을 수 없다.

학습 연결:

- Day 4 API 호출에서 비용과 입력 길이를 이해할 때 필요하다.
- Day 6 RAG에서 chunking이 왜 필요한지 설명할 때 필요하다.

## 2. Context Window

Context window는 모델이 한 번에 볼 수 있는 입력 범위다.

왜 중요한가:

- 모델은 context window 밖의 내용은 직접 볼 수 없다.
- 긴 문서를 모두 넣기 어렵기 때문에 RAG나 요약 memory가 필요하다.
- 관련 없는 정보를 너무 많이 넣으면 중요한 정보가 희석될 수 있다.

학습 연결:

- Day 6 RAG에서 문서를 chunk로 나누고 필요한 chunk만 검색하는 이유다.
- prompt/context/harness 학습에서 "무엇을 넣고 무엇을 뺄 것인가"의 기준이 된다.

## 3. Next-Token Prediction

LLM은 기본적으로 지금까지의 입력을 보고 다음 token을 예측하는 방식으로 문장을 생성한다.

왜 중요한가:

- LLM은 데이터베이스처럼 정답을 조회하는 시스템이 아니다.
- 근거가 부족해도 그럴듯한 문장을 만들 수 있다.
- "자연스럽다"와 "사실이다"는 다르다.

학습 연결:

- Day 5에서 structured output과 평가 기준이 필요한 이유다.
- Day 6에서 grounding과 source 확인이 필요한 이유다.

## 4. Sampling And Temperature

모델은 가능한 다음 token들 중에서 선택하며, temperature는 선택의 다양성에 영향을 준다.

왜 중요한가:

- 같은 prompt라도 답변이 달라질 수 있다.
- 낮은 temperature는 더 안정적인 출력을 기대할 때 유리하다.
- 높은 temperature는 아이디어 생성처럼 다양성이 필요할 때 쓸 수 있다.

학습 연결:

- Day 5 prompt version 비교와 출력 안정성 실습에서 필요하다.
- 평가 실험에서는 temperature 같은 조건을 고정해야 비교가 가능하다.

## 5. Embedding

Embedding은 문장이나 문서를 숫자 벡터로 표현한 것이다.

왜 중요한가:

- 비슷한 의미의 문장을 가까운 벡터로 표현할 수 있다.
- RAG에서 질문과 문서 chunk의 의미적 유사도를 비교하는 데 사용된다.
- keyword가 정확히 일치하지 않아도 관련 문서를 찾을 수 있다.

학습 연결:

- Day 6 embedding과 vector search의 핵심 이론이다.
- similarity search 결과가 항상 정답 근거는 아니므로 retrieval 평가가 필요하다.

## 6. Similarity Search

Similarity search는 질문 embedding과 문서 embedding을 비교해 가까운 문서를 찾는 과정이다.

왜 중요한가:

- 검색 결과가 틀리면 모델이 아무리 좋아도 답변 근거가 부족하다.
- top-k, chunk 크기, metadata가 검색 품질에 영향을 준다.
- RAG 실패는 generation 문제가 아니라 retrieval 문제일 수 있다.

학습 연결:

- Day 6에서 검색 결과를 직접 확인해야 하는 이유다.
- Day 7 미니 프로젝트에서 평가표에 "검색된 문서"를 기록하는 이유다.

## 7. Hallucination And Grounding

Hallucination은 모델이 근거 없는 내용을 그럴듯하게 생성하는 현상이다.

Grounding은 모델 답변을 제공된 문서나 검증 가능한 근거에 묶는 것이다.

왜 중요한가:

- LLM 활용 서비스에서는 그럴듯한 답변보다 근거 있는 답변이 중요하다.
- RAG prompt에는 "검색된 문서 안의 정보만 사용" 같은 제약이 필요하다.
- 근거가 없을 때 "모른다"고 답하는 행동을 설계해야 한다.

학습 연결:

- Day 5 prompt 설계와 Day 6 RAG 실습 모두에 필요하다.
- Day 7 평가표에서 "정답 근거 있음"을 따로 보는 이유다.

## 8. Pretraining, Fine-Tuning, RLHF 개요

세부 수식보다 역할만 이해한다.

- Pretraining: 대량 텍스트에서 언어 패턴과 지식을 학습한다.
- Fine-tuning: 특정 작업이나 형식에 더 잘 맞게 조정한다.
- RLHF 또는 preference tuning: 사람이 선호하는 답변 방식에 가깝게 조정한다.

왜 중요한가:

- 모델은 학습 데이터에서 본 패턴을 바탕으로 답하지만 최신 정보를 자동으로 아는 것은 아니다.
- 지시를 잘 따른다고 해서 항상 사실을 검증하는 것은 아니다.
- 최신 정보나 사내 문서는 RAG나 tool 사용이 필요하다.

학습 연결:

- Day 4 공식 문서 확인 규칙과 연결된다.
- Day 6 RAG가 필요한 이유와 연결된다.

## 9. Evaluation

Evaluation은 LLM 답변이 좋아 보이는지 감으로 판단하지 않고 기준으로 확인하는 일이다.

왜 중요한가:

- prompt를 바꿨을 때 실제로 좋아졌는지 확인해야 한다.
- RAG에서는 retrieval 품질과 generation 품질을 분리해야 한다.
- 모델 변경, prompt 변경, chunking 변경은 회귀를 만들 수 있다.

학습 연결:

- Day 5 평가 기준 만들기
- Day 6 RAG 실패 원인 분리
- Day 7 미니 프로젝트 평가표

## 10. Agent Loop

Agent는 보통 단순 답변보다 더 긴 루프를 가진다.

기본 흐름:

```text
context gathering -> action/tool use -> verification -> retry/report
```

왜 중요한가:

- agent가 잘 작동하려면 prompt만이 아니라 tool 권한, context, 검증, 로그가 필요하다.
- 실패했을 때 어떤 단계에서 실패했는지 확인해야 한다.

학습 연결:

- 이후 LangGraph, Agent, harness engineering 학습과 연결된다.

## 최소 완료 기준

아래 질문에 짧게 답할 수 있으면 이론 기초는 충분하다.

1. LLM은 왜 근거 없이도 그럴듯하게 답할 수 있는가?
2. context window가 왜 RAG와 memory 설계에 영향을 주는가?
3. embedding은 RAG 검색에서 어떤 역할을 하는가?
4. RAG 실패를 retrieval과 generation으로 나누는 이유는 무엇인가?
5. prompt 변경 전후를 평가표로 비교해야 하는 이유는 무엇인가?
