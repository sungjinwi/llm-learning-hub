# Commit Message Guidelines

이 repo의 커밋 메시지는 나중에 학습 기록을 다시 볼 때 이해하기 쉽도록 한글 중심으로 작성한다.

## 기본 형식

```text
짧은 한글 헤더

- 핵심 변경 1
- 핵심 변경 2
- 필요한 경우 이유 또는 영향 1개
```

## 작성 원칙

- 헤더는 한글로 작성한다.
- `Python`, `LLM`, `RAG`, `API`, `JSON`, `NotebookLM`, `OpenAI`, `LangChain`처럼 기술 용어는 영어 그대로 둔다.
- 바디는 2-4개 bullet로 간결하게 작성한다.
- 바디에는 단순 파일 목록보다 변경 이유, 학습 흐름, 영향이 드러나게 쓴다.
- 한 커밋에는 하나의 목적만 담는다.
- 이미 GitHub에 push된 커밋 메시지를 고치려면 history rewrite와 force push가 필요하므로 먼저 사용자 확인을 받는다.

## 좋은 예시

```text
Day 1 Python core 학습 기록 추가

- Python core 완료 상태와 학습 로그를 반영
- active recall 문제, 약점 해결 기록, NotebookLM용 요약을 추가
- LLM 과정 대비 리뷰와 자주 하는 실수 문서를 함께 정리
```

```text
LLM 활용 과정 중심으로 커리큘럼 개편

- Week 1을 API, prompt, embedding, RAG 중심으로 재구성
- 기존 PyTorch 중심 실습을 보충 주제로 이동
- 공식 문서 우선 확인 정책과 LLM 실습 파일을 추가
```

```text
공식 문서 기반 학습 규칙 보강

- OpenAI API, LangChain, Pandas 등은 공식 문서 확인을 우선하도록 명시
- 문서 기반 실습도 출력 예측과 최소 예제로 연결
- 학습 로그에 참고 문서와 확인 항목을 남기도록 정리
```

## 피해야 할 예시

```text
Update files
```

이유: 무엇을 왜 바꿨는지 알 수 없다.

```text
Fix
```

이유: 수정 범위와 영향이 전혀 드러나지 않는다.

```text
커리큘럼 수정
```

이유: 헤더만으로는 어떤 방향으로 수정했는지 부족하다. 바디가 있으면 사용할 수 있다.

## 기존 커밋 메시지 수정 기준

기존 커밋 메시지는 수정할 수 있다. 방법은 `git rebase` 또는 history rewrite 후 `git push --force-with-lease`를 사용하는 것이다.

하지만 이미 원격에 올라간 커밋을 수정하면 다른 환경의 clone이나 branch와 히스토리가 달라질 수 있다. 따라서 이 repo에서는 다음 기준을 따른다.

- 아직 push하지 않은 커밋: 필요하면 메시지를 바로 고친다.
- 이미 push한 개인 작업 커밋: 사용자가 명시적으로 원하면 고친다.
- 다른 사람이 기반으로 삼았을 수 있는 커밋: 특별한 이유가 없으면 고치지 않는다.
- force push가 필요하면 작업 전에 커밋 목록과 바꿀 메시지를 먼저 보여준다.
