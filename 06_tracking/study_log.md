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
- 커리큘럼 보강: Day 1은 완료 상태로 유지하되, Day 2 시작 전 보충으로 indexing/slicing, string preview, nested data 접근, enumerate를 추가함. 이후 Day 2에는 f-string, `dict.get`, nested JSON 접근을 보강하고, Day 3에는 list/dict comprehension, Day 6에는 slicing과 `range` 기반 chunking 감각을 연결함.
- LLM 이론 보강: 기존 계획은 활용 실습 중심이라 LLM 자체 원리 학습이 약했음. Day 4~7에 `LLM Theory Lite` 보조 트랙을 추가해 token, context window, next-token prediction, temperature, hallucination, embedding, similarity search, grounding, evaluation, agent loop를 실습과 연결하도록 함.
- cross-repo 운영 보강: 메인 학습은 `D:\llm-learning-hub`에서 시작하고, prompt/context/harness/eval 전문 실습은 `D:\llm-interaction-engineering`으로 연결한 뒤 결과 요약을 다시 메인 기록에 남기도록 `cross_repo_learning_flow.md`와 `learning_record_system.md`를 추가함.
- 다음 행동: Day 2 시작 전 Day 1 복습 3문제와 Day 1 보충 4문제

## 2026-05-21

- 질문 유형과 선택한 학습법: 오늘 일정 시작 -> 능동적 회상 + 출력 예측
- 현재 Day: Day 2 시작 전 Day 1 보충
- Day 1 복습 결과: list, dict, class, parameter/argument 구분은 통과. dict는 삽입 순서가 보존되지만 key 기반 접근이 핵심임을 보정.
- Day 1 보충 결과: nested dict/list 접근 경로와 enumerate의 역할은 정확히 설명함.
- 막힌 부분: slicing에서 `end` 인덱스가 포함되지 않는 규칙을 헷갈림. `results[:3]`을 4개로 예측함.
- slicing 재출제 결과: `items[1:4]`, `items[:2]`, `items[3:]`를 모두 정확히 예측함.
- Day 2 pathlib 시작: `/` 연산자가 Path에서 경로 결합으로 동작한다는 점은 추론함. `Path.name`을 확장자 없는 파일명으로 예측해 `name`과 `stem` 구분 보정 필요.
- Day 1 보충 string slicing 결과: `text[:10]` preview는 정확히 예측함. `len(text)` 답변은 개념 오해가 아니라 빠른 풀이 중 실수로 확인되어 약점 기록에서 제외함.
- Day 1 보충 완료 여부: list slicing, string slicing, nested data 접근, enumerate를 모두 진행함.
- 추가 질문 기록 규칙 추가: 사용자가 중간 질문의 기록 여부를 물어봄. 앞으로 AI가 질문의 연관도와 중요도를 판단해 `study_log`, notes, `weak_points`, `review_schedule` 중 적절한 위치에 요약 기록하고, 일회성 확인은 기록하지 않도록 운영 규칙에 반영함.
- 추가 질문: API에서 JSON을 많이 쓰는 이유를 질문함. JSON은 서로 다른 프로그램이 구조화된 데이터를 주고받기 위한 텍스트 기반 공통 형식이며, API 요청/응답 파싱에서 중요하다고 정리함.
- Day 2 JSON 구조 읽기: `json.loads`가 JSON 문자열을 Python `dict`로 변환한다는 점과 출력은 정확히 예측함. JSON `null`이 Python `NULL`이 아니라 `None`으로 변환된다는 점을 보정함.
- 추가 질문: Python에서 null-like 값을 왜 `None`이라고 부르는지 질문함. `None`은 Python의 singleton 객체이며, 값이 없음을 표현하는 언어 고유의 이름이라고 정리함.
- JSON `null -> None` 재출제 결과: `true -> True`, `null -> None`을 정확히 답해 약점은 resolved 처리함.
- Day 2 f-string 결과: 출력 예측은 정확함. f-string을 Python 내부의 `dict`/`list` 처리 결과를 사용자용 문자열, prompt, 로그로 조립하는 도구로 이해함.
- Day 2 nested dict와 `.get()` 결과: nested 접근과 `.get("score", 0)` 출력은 정확히 예측함. 없는 key 직접 접근은 `None` 반환이 아니라 `KeyError` 발생임을 보정함.
- missing key 접근 재출제 결과: 처음에는 `TypeError`로 답했으나, 바로 다음 재출제에서 없는 key 직접 접근이 `KeyError`임을 정확히 설명해 resolved 처리함.
- Day 2 `try/except` 결과: 없는 key 접근이 `KeyError`로 잡히고, 예외 객체를 출력하면 문제 key가 보인다는 흐름을 이해함.
- Day 2 `assert` 결과: 조건이 `True`면 통과하고 `False`면 `AssertionError`가 발생해 이후 print가 실행되지 않음을 정확히 예측함.
- Day 2 파일/JSON 미니 실습 설계: 필요한 import는 `pathlib`, `json`으로 답함. JSON 파일 저장/읽기 함수는 `json.jsonify`, `json.parse`로 답해 Python의 `json.dump`/`json.load`와 구분 보정 필요.
- Python `json.dump`/`json.load`와 `dumps`/`loads` 구분 재출제 결과: 네 함수의 용도는 거의 정확히 답함. `loads`의 인자는 Python dict가 아니라 JSON 문자열이라는 점을 보정함.
- 추가 질문: `dump`와 `dumps`가 왜 s 하나로 구분되는지 질문함. `s`는 string을 뜻하며 `dump/load`는 file object 대상, `dumps/loads`는 string 대상이라고 정리함.
- 파일 입출력 미니 실습: `json.dump(data, file)`과 `json.load(file)` 빈칸을 정확히 채움. `with open(...) as file`은 처음 접한 개념으로 확인되어 파일 자동 닫기와 모드(`w`, `r`)를 짧게 설명하고 실습으로 연결함.
- 다음 행동: `with open` 출력/흐름 확인 후 Day 2 마무리 실습으로 이동.
- 운영 보정: 사용자가 "직접 써보는 단계"라는 안내와 실제 "빈칸 채우기" 문제가 불일치한다고 지적함. 앞으로 문제 유형을 자유 구현, 빈칸 구현, 출력 예측 등으로 정확히 명시하도록 `AGENTS.md`, `AI_STUDY_OPERATING_RULES.md`, `learning_record_system.md`에 반영함.
- Day 2 마무리 빈칸 구현 결과: JSON 파일 저장은 `json.dump(data, file)`, JSON 파일 읽기는 `json.load(file)`, 점수 검증은 `assert loaded["score"] >= 60`으로 정확히 작성함.
- 커리큘럼 상태 점검: 사용자가 오늘 진도와 cross-repo 연결 상태 확인을 요청함. Day 1 보충은 completed, Day 2는 핵심 실습 대부분 완료했으나 `import`/모듈, `venv`/`pip`, 마무리 요약이 남아 in_progress로 정리함.
- Cross-repo 확인: `cross_repo_learning_flow.md`에 Day 4 API 질문 구조화, Day 5 Prompt Engineering, Day 6 Context/RAG, Day 7 Harness 연결 규칙이 이미 있어, 해당 주제가 오면 interaction engineering lab으로 유도하도록 설계되어 있음을 확인함.
- 운영 보정: 커밋 메시지 규칙이 `04_ai_prompts/commit_message_guidelines.md`에 있었지만 필수 확인 목록에 빠져 있어 영어 단문 커밋이 생성됨. `AGENTS.md`와 운영 규칙에 작업별 보조 규칙 확인, commit 전 commit guideline 확인, force push 기준을 추가함.
