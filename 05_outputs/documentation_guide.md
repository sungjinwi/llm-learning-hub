# Documentation Guide

작성일: 2026-05-20

## 목적

이 문서는 `D:\llm-learning-hub`와 `D:\llm-interaction-engineering`의 학습 기록을 나중에 NotebookLM, 슬라이드, 블로그, 포트폴리오 문서로 변환하기 위한 가이드다.

## 문서화 원칙

학습 기록은 단순히 "무엇을 했다"가 아니라 다음 질문에 답해야 한다.

1. 왜 이 주제를 배웠는가?
2. 어떤 문제를 풀었는가?
3. 어떤 개념을 오해했는가?
4. 어떻게 교정했는가?
5. 다음 주제와 어떻게 연결되는가?
6. 실무나 프로젝트에서는 어디에 쓰이는가?

## 문서화 소스 우선순위

| 우선순위 | 파일/폴더 | 사용 목적 |
| --- | --- | --- |
| 1 | `05_outputs/summaries/` | 하루 학습을 NotebookLM이나 슬라이드로 변환 |
| 2 | `06_tracking/study_log.md` | 날짜별 학습 흐름 확인 |
| 3 | `06_tracking/weak_points.md` | 오개념, 교정, 복습 문제 추출 |
| 4 | `06_tracking/progress_dashboard.md` | 전체 진도와 완료 증거 확인 |
| 5 | `03_subjects/*/notes/` | 개념 설명 문서화 |
| 6 | `03_subjects/*/exercises/` | 실습 문제와 코드 예시 추출 |
| 7 | `D:\llm-interaction-engineering\05_outputs/` | prompt/context/harness 실습 산출물 추출 |

## 하루 학습 문서화 템플릿

```md
# YYYY-MM-DD 학습 회고 - <topic>

## 1. 오늘의 목표

## 2. 배운 핵심 개념

## 3. 수행한 실습

## 4. 내가 처음 이해한 방식

## 5. 틀렸거나 헷갈린 부분

## 6. 교정 후 이해

## 7. 코드, prompt, context, harness 예시

## 8. LLM 활용 과정과의 연결

## 9. 다음 복습 문제

## 10. 한 문장 요약
```

## 슬라이드 구성 템플릿

10장 내외로 만들 때는 아래 순서를 사용한다.

1. 오늘의 주제와 목표
2. 왜 이 개념이 필요한가
3. 핵심 개념 1
4. 핵심 개념 2
5. 실습 문제
6. 내가 한 답변 또는 코드
7. 틀린 부분과 교정
8. 실제 LLM/API/RAG/Prompt 활용과의 연결
9. 다음에 다시 풀 문제
10. 오늘의 결론

## NotebookLM 입력용 구성

NotebookLM에 넣을 때는 너무 많은 raw 파일을 한꺼번에 넣기보다 아래 순서로 넣는다.

1. 해당 날짜의 `05_outputs/summaries/*.md`
2. 관련 개념 노트 `03_subjects/*/notes/*.md`
3. 관련 실습 파일 `03_subjects/*/exercises/*.md`
4. 약점 기록 `06_tracking/weak_points.md`
5. 필요한 경우 interaction lab 산출물

권장 질문:

```text
이 학습 기록을 바탕으로 10장짜리 복습 슬라이드 목차를 만들어줘.
각 슬라이드는 핵심 개념, 실습, 오개념 교정, 다음 복습 문제를 포함해줘.
```

## Cross-repo 문서화

`D:\llm-interaction-engineering`에서 연결 실습을 수행한 날에는 메인 문서에 아래 섹션을 추가한다.

```md
## Interaction Engineering 연결

- 연결 repo:
- 연결 파일:
- 연결 이유:
- 수행한 실습:
- 배운 판단 기준:
- 메인 학습에 반영할 점:
```

예:

```md
Day 6 RAG 학습 중 검색된 chunk를 prompt에 넣는 방식이 중요해져서
`D:\llm-interaction-engineering`의 context packet 실습으로 연결했다.
그 결과 context, question, instruction, source를 분리해야 한다는 기준을 추가했다.
```

## 블로그/포트폴리오 변환 구조

학습 내용을 외부 공개 문서로 바꿀 때는 개인 대화 전체를 노출하지 말고, 판단 기준과 산출물 중심으로 재구성한다.

권장 구조:

```md
# LLM 학습 기록: <topic>

## 문제의식

## 배운 개념

## 실습 예시

## 실수와 교정

## 실제 프로젝트 적용 포인트

## 다음 학습 계획
```

주의:

- API key, 개인 경로, 계정 정보는 제거한다.
- AI와의 대화 전문을 그대로 공개하지 않는다.
- 코드와 prompt는 필요한 부분만 정리한다.
- 공식 문서나 외부 출처를 사용한 경우 링크를 남긴다.

## 좋은 문서화의 기준

문서화 결과물은 아래 조건을 만족해야 한다.

- 처음 보는 사람이 오늘 무엇을 배웠는지 알 수 있다.
- 코드나 prompt 예시가 최소 1개 이상 있다.
- 오개념과 교정 내용이 포함되어 있다.
- 다음 학습으로 이어지는 질문이 있다.
- 출처가 필요한 내용은 링크가 있다.
- 개인 정보와 secret이 없다.

## 마무리 체크리스트

문서화 전에 확인한다.

- [ ] summary 파일이 있는가?
- [ ] 약점과 교정이 기록되어 있는가?
- [ ] 실습 코드 또는 prompt 예시가 있는가?
- [ ] 다음 복습 문제가 있는가?
- [ ] interaction lab 연결이 있었다면 요약했는가?
- [ ] 공개하면 안 되는 정보가 제거되었는가?
