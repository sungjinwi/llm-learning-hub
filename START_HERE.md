# Learning System Start

이 폴더는 Gemini 보고서의 학습법을 실제 운영 가능한 로컬 학습 시스템으로 바꾼 것이다.

## 가장 짧은 사용법

앞으로 학습할 때는 길게 프롬프트를 쓰지 말고 아래처럼 말하면 된다.

```text
오늘 학습 시작
```

또는:

```text
Day 1 시작
Python 변수 복습
어제 내용 점검
내 약점 기준으로 문제 내줘
```

그러면 AI는 `AI_STUDY_OPERATING_RULES.md`를 기준으로 다음 순서를 기본값으로 사용한다.

1. 오늘의 목표 확인
2. 이전 약점과 복습 일정 확인
3. 질문 유형에 맞는 학습법 선택
4. 짧은 사전 진단 질문
5. 개념 설명은 최소화
6. 실제 코드 실습으로 연결
7. 능동적 회상 문제 출제
8. 답변 후 채점
9. 틀린 내용은 `06_tracking/weak_points.md` 형식으로 정리
10. 다음 복습 항목을 `06_tracking/review_schedule.md`에 반영

## 핵심 원칙

AI에게 완성된 답을 먼저 받는 구조가 아니라, AI가 튜터, 출제자, 채점자, 오답 분석가, 복습 관리자로 움직이게 한다.

정답을 바로 보여달라고 하지 않는 한, 먼저 질문하고 답변을 기다리는 방식이 기본이다.

질문 유형에 따라 학습법이 자동으로 바뀐다.

- 개념 질문: 소크라테스식 문답
- 설명이 막힘: 파인만 역할 반전
- 복습 요청: 능동적 회상
- 코드 이해: 역공학
- 에러 해결: 컨텍스트 격리 디버깅
- 라이브러리 사용법: 문서 기반 실습
- 무언가 만들기: 프로젝트 기반 학습

Python, 데이터, LLM, RAG 주제는 이론만 설명하지 않고 반드시 작은 코드 실습으로 이어간다.

OpenAI API, LangChain, LangGraph, Gradio, Pandas, scikit-learn처럼 정확한 사용법이 중요한 내용은 공식 문서를 먼저 확인한 뒤 학습으로 연결한다.

## 주요 파일

- `AI_STUDY_OPERATING_RULES.md`: AI가 이 학습 폴더에서 따라야 할 기본 규칙
- `01_learning_plan/master_plan.md`: 전체 7일 학습 지도
- `01_learning_plan/daily_routine.md`: 매일 반복할 학습 루틴
- `03_subjects/python/roadmap.md`: Python/AI 과목별 진행표
- `03_subjects/llm/roadmap.md`: LLM 활용 과정 대비 진행표
- `04_ai_prompts/default_study_modes.md`: 짧은 명령을 학습 모드로 해석하는 규칙
- `04_ai_prompts/method_router.md`: 질문 유형별 학습법 선택 규칙
- `02_methods/practice_loop.md`: 이론을 코드 실습으로 연결하는 공통 루프
- `06_tracking/study_log.md`: 학습 기록
- `06_tracking/weak_points.md`: 약점 기록
- `06_tracking/review_schedule.md`: 복습 일정
