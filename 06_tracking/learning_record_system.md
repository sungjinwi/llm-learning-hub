# Learning Record System

작성일: 2026-05-20

## 목적

학습 기록은 나중에 다시 봤을 때 이해 가능해야 하고, NotebookLM, 슬라이드, 회고 문서로 변환하기 쉬워야 한다.

이 repo의 기록은 아래처럼 역할을 나눈다.

## 기록 파일 역할

| 위치 | 역할 | 작성 방식 |
| --- | --- | --- |
| `06_tracking/study_log.md` | 시간순 학습 로그 | 오늘 무엇을 했는지 짧게 기록 |
| `06_tracking/weak_points.md` | 약점과 오개념 | 재출제 가능한 형식으로 기록 |
| `06_tracking/review_schedule.md` | 복습 일정 | 다음에 언제 무엇을 다시 물을지 기록 |
| `06_tracking/progress_dashboard.md` | 전체 진도판 | 영역별 상태와 증거 파일 기록 |
| `05_outputs/summaries/` | NotebookLM/슬라이드용 요약 | 하루 학습을 문서화 가능한 형태로 정리 |
| `05_outputs/projects/` | 프로젝트 회고 | 프로젝트 목표, 구현, 실패, 평가 결과 정리 |
| `03_subjects/*/notes/` | 개념 노트 | 개념을 나중에 다시 읽을 수 있게 정리 |
| `03_subjects/*/exercises/` | 실습 문제 | 정답 숨김, 출력 예측, 빈칸, 평가 문제 |
| `01_learning_plan/cross_repo_learning_flow.md` | repo 간 연결 규칙 | main repo와 interaction lab 전환 기준 |

## 하루 마무리 기록 형식

매일 학습 후 아래 형식으로 요약 문서를 만든다.

파일 위치:

```text
05_outputs/summaries/YYYY-MM-DD_<topic>_summary.md
```

권장 구조:

```md
# YYYY-MM-DD 학습 기록 - <topic>

## 1. 오늘의 목표

## 2. 수행한 실습

## 3. 핵심 개념

## 4. 내가 직접 설명한 내용

## 5. 틀렸거나 헷갈린 부분

## 6. 교정된 설명

## 7. 코드 또는 prompt 예시

## 8. 다음 복습 문제

## 9. 다음 학습과의 연결

## 10. NotebookLM/슬라이드 구성안
```

## Cross-repo 학습 기록 형식

`D:\llm-interaction-engineering`에서 연결 실습을 수행한 날에는 메인 repo 요약에 아래 항목을 추가한다.

```md
## Interaction Lab 연결

- 연결 repo:
- 연결 파일:
- 연결 이유:
- 수행한 실습:
- 메인 학습에 추가된 판단 기준:
- 다음 복습:
```

## 좋은 기록의 기준

나중에 읽었을 때 다음 질문에 답할 수 있어야 한다.

1. 오늘 왜 이 주제를 배웠는가?
2. 어떤 코드를 읽거나 작성했는가?
3. 어떤 개념을 오해했는가?
4. 오해가 어떻게 교정되었는가?
5. 다음 주제와 어떻게 연결되는가?
6. 다시 학습한다면 어떤 문제부터 풀어야 하는가?

## 문서화 적합성 판단

현재 기록 구조는 문서화에 적합하다.

이유:

- `study_log`는 시간순 목차 역할을 한다.
- `summaries`는 NotebookLM이나 슬라이드에 바로 넣을 수 있다.
- `weak_points`와 `review_schedule`은 복습 문제 생성에 적합하다.
- `progress_dashboard`는 전체 진도 현황을 빠르게 보여준다.
- cross-repo 기록 규칙이 있으면 prompt/context/harness 실습이 메인 LLM 학습에서 왜 필요했는지 추적할 수 있다.

보완할 점:

- 매일 마무리 때 summary 파일을 반드시 생성해야 한다.
- interaction lab 실습 결과는 상세 기록은 lab repo에, 요약은 main repo에 남겨야 한다.
- 코드, prompt, context packet, 평가표는 가능한 한 원문 예시를 함께 남겨야 한다.
