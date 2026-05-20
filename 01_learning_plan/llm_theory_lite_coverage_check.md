# LLM Theory Lite Coverage Check

작성일: 2026-05-20

## 목적

현재 7일 사전준비 커리큘럼이 활용 실습에 치우쳐 LLM 자체 원리를 놓치지 않도록, 반드시 다룰 최소 이론과 의도적으로 뒤로 미룰 심화 이론을 구분한다.

## 포함한 최소 이론

| 개념 | 포함 위치 | 필요한 이유 | 상태 |
| --- | --- | --- | --- |
| token | Day 4 | 비용, 입력 길이, context window 이해 | included |
| context window | Day 4 | 긴 문서, memory, RAG 필요성 이해 | included |
| next-token prediction | Day 4 | LLM이 정답 조회기가 아니라 생성 모델임을 이해 | included |
| sampling/temperature | Day 5 | 출력 안정성과 다양성 trade-off 이해 | included |
| hallucination | Day 5, Day 6 | 근거 없는 답변 위험 이해 | included |
| grounding | Day 5, Day 6 | 문서 기반 답변과 source 확인 이해 | included |
| structured output | Day 5 | 자동 검증과 eval 연결 | included |
| embedding | Day 6 | RAG 검색의 기본 원리 이해 | included |
| similarity search | Day 6 | 질문과 문서 chunk 검색 이해 | included |
| retrieval/generation 분리 | Day 6 | RAG 실패 원인 분리 | included |
| evaluation | Day 7 | prompt/RAG/model 변경 비교 | included |
| pretraining/fine-tuning/RLHF 개요 | Day 7 | 모델의 지식과 한계 이해 | included |
| agent loop | Day 7 | context gathering, action, verification 흐름 이해 | included |

## 의도적으로 뒤로 미룬 심화 이론

| 개념 | 미룬 이유 | 이후 학습 시점 |
| --- | --- | --- |
| transformer 수식 | 사전준비 단계에서는 활용 판단에 비해 부담이 큼 | 1주 이후 |
| attention 세부 계산 | 개념 감각은 유용하지만 구현 수준은 당장 불필요 | 1주 이후 |
| tokenizer 내부 구현 | token 개념만 먼저 충분 | API 비용/최적화 학습 시 |
| model training loop | LLM 활용 과정의 직접 선행 지식은 아님 | PyTorch 보충과 함께 |
| fine-tuning 실습 | API/RAG/평가 후에 다루는 것이 효율적 | 프로젝트 이후 |
| RLHF/RLAIF 세부 과정 | 모델 사용 판단에는 개요만 필요 | 모델 평가 심화 시 |
| inference optimization | 배포/비용 최적화 단계에서 필요 | 서비스 운영 학습 시 |

## 누락 점검 결과

현재 계획은 LLM 활용 과정에 필요한 최소 이론을 모두 포함한다.

남은 위험은 이론을 별도 강의처럼 길게 다루는 것이 아니라, 실습과 연결하지 못하는 것이다. 따라서 운영 원칙은 다음과 같다.

1. 이론 설명은 10~20분 이내로 제한한다.
2. 각 이론은 반드시 당일 실습의 실패 가능성과 연결한다.
3. 사용자가 먼저 자기 말로 설명하게 한다.
4. 수식이나 구현보다 "왜 이 개념이 API/RAG/prompt/eval 판단에 필요한가"를 우선한다.
5. 깊은 transformer/PyTorch 내용은 1주 이후 보충으로 분리한다.
