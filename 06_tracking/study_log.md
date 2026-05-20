# Study Log

## 2026-05-19

- 시스템 생성:
- 현재 Day:
- 오늘 학습:
- 막힌 부분:
- 다음 행동:

## 2026-05-20

- 질문 유형과 선택한 학습법: Day 1 시작 요청 -> 소크라테스식 문답 + 능동적 회상
- 현재 Day: Day 1 - Python Core
- 오늘 학습: 변수, 타입, 조건문, 반복문, list, dict, function 진단 시작
- 막힌 부분: dict의 순서 보존과 key 중복 기준 구분 필요
- 교정 진행: `items["a"] = items["a"] + 5` 문제에서 우변 선계산, value 갱신, dict 전체 출력까지 정확히 설명함
- active recall 결과: 출제문 누락 가능성이 확인되어 리스트 인덱싱 오답 판정은 취소. parameter/argument 구분은 추가 설명 필요.
- 운영 보정: 코드 출력 예측 문제는 변수 정의를 포함한 실행 가능한 전체 스니펫으로 출제해야 함.
- active recall 재출제 결과: dict value 갱신, 반복문 출력, 조건문 return 흐름은 통과. parameter/argument는 서로 반대로 답해 추가 교정 필요.
- parameter/argument 교정 결과: `introduce(name, age)`의 parameter와 `introduce("Kim", 30)`의 argument를 정확히 구분함.
- 작은 구현 실습 결과: `student["score"] >= 60` 조건과 `student["name"]` append를 정확히 작성함. 예상 출력의 리스트 표기만 보정 필요.
- class 최소 개념 결과: `Student("Lee", 55)` 객체 생성, `student.name`, `student.is_passed()` 출력 흐름을 정확히 설명함.
- Day 1 파인만식 요약 결과: function, parameter/argument는 정확. list/dict/class 설명은 표현 보정 필요.
- Day 1 보정 완료: list는 순서와 인덱스, dict는 key-value와 key 접근, class는 객체 설계도로 정확히 재설명함.
- NotebookLM/슬라이드용 요약 생성: `05_outputs/summaries/2026-05-20_day1_python_core_slide_notes.md`
- 커리큘럼 개편: 모두의연구소 LLM 서비스 개발 과정에 맞춰 Week 1을 Python/Pandas/PyTorch 중심에서 Python 실전 도구, API, prompt, embedding, RAG, 미니 LLM 프로젝트 중심으로 재구성함.
- 신뢰성 규칙 추가: API, 라이브러리, 보안, 평가 지표, 최신 모델처럼 정확도가 중요한 주제는 공식 문서를 우선 확인하도록 운영 규칙과 라우터에 반영함.
- 세부 실습 재점검: 기존 Day 2~7의 NumPy/sklearn/PyTorch 중심 실습 파일을 제거하고, Python 실전 도구, Pandas 평가 데이터, API 응답 파싱, prompt 평가, RAG retrieval 점검, FAQ QA 미니 프로젝트 실습으로 교체함.
- 다음 행동: Day 2 시작 전 Day 1 복습 3문제
