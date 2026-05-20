# Day 7 LLM Theory Lite - Eval And Agent Loop

## 적용 학습법

- 기본: 평가표 설계
- 보조: 실패 원인 분류

## 목표

미니 프로젝트를 만들 때 evaluation, 모델 학습 방식 개요, agent loop를 최소 이론으로 연결한다.

## 실습 1 - evaluation이 필요한 이유

아래 prompt v1과 v2 중 무엇이 더 좋은지 감으로 말하지 말고 평가 기준을 만든다.

```text
v1: FAQ를 보고 답변해줘.
v2: FAQ 문서에 있는 근거만 사용하고, 근거가 없으면 문서에서 확인할 수 없다고 답해줘.
```

질문:

1. 비교할 테스트 질문 3개를 제안하라.
2. 각 질문에서 기대 근거는 무엇이어야 하는가?
3. 어떤 답변을 실패로 볼 것인가?

## 실습 2 - pretraining / fine-tuning / RLHF 역할 구분

아래 설명을 각각 어느 개념과 연결할 수 있는지 고른다.

```text
1. 대량 텍스트를 통해 언어 패턴과 일반 지식을 배운다.
2. 특정 작업이나 형식에 더 잘 맞게 조정한다.
3. 사람이 선호하는 답변 방식에 더 가깝게 만든다.
```

답변 형식:

```md
1:\n+2:\n+3:\n+```

추가 질문:

1. 이 과정을 거친 모델도 왜 최신 사내 문서는 모를 수 있는가?
2. 그래서 RAG나 tool use가 필요한 이유는 무엇인가?

## 실습 3 - agent loop

아래 agent 흐름에서 빠진 단계를 찾는다.

```text
1. 사용자 요청을 받는다.
2. 바로 파일을 수정한다.
3. 사용자에게 완료했다고 말한다.
```

질문:

1. context gathering 단계가 빠지면 어떤 문제가 생기는가?
2. verification 단계가 빠지면 어떤 문제가 생기는가?
3. 좋은 agent loop를 4단계로 다시 작성하라.

## 완료 기준

- evaluation이 prompt/context 변경의 품질을 판단하는 기준임을 설명할 수 있다.
- pretraining, fine-tuning, RLHF의 역할을 아주 간단히 구분할 수 있다.
- agent loop에서 context gathering과 verification이 필요한 이유를 설명할 수 있다.
