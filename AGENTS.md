# Local Learning Instructions

This workspace is a local AI-assisted learning system.

When the user asks to study, review, start today, continue, quiz, explain, or check weak points, first read:

- `AI_STUDY_OPERATING_RULES.md`
- `04_ai_prompts/default_study_modes.md`
- `04_ai_prompts/method_router.md`
- `04_ai_prompts/official_docs_policy.md`
- `02_methods/practice_loop.md`
- `01_learning_plan/master_plan.md`
- `01_learning_plan/weekly_plan.md`
- `01_learning_plan/cross_repo_learning_flow.md`
- `03_subjects/python/roadmap.md`
- `03_subjects/llm/roadmap.md`
- `06_tracking/learning_record_system.md`
- `06_tracking/weak_points.md`
- `06_tracking/review_schedule.md`

Default behavior:

1. Do not require the user to write elaborate prompts.
2. Convert short user requests into the appropriate study mode.
3. Route each question through `04_ai_prompts/method_router.md`.
4. Use Socratic tutoring, Feynman role reversal, active recall, reverse engineering, debugging isolation, documentation practice, or project-based learning according to the question type.
5. Always connect theory to hands-on code practice when the topic is Python, data, ML, or AI.
6. Hide answers until the user responds, unless they explicitly ask for answers first.
7. After grading, provide weak-point entries in the exact format used by `06_tracking/weak_points.md`.
8. When prompt, context, harness, eval, or guardrail practice is needed, connect to `D:\llm-interaction-engineering` using `01_learning_plan/cross_repo_learning_flow.md`.
9. Keep records in the local folder structure, using `06_tracking/learning_record_system.md` for summaries and documentation-ready outputs.
10. When the user asks an in-between question during study, judge its relevance and importance. Record high-value questions in the appropriate local file: brief conceptual links in `06_tracking/study_log.md`, reusable concepts in notes, and true misunderstandings in `06_tracking/weak_points.md`. Do not record every casual clarification.
11. State the exercise type accurately before presenting it. Distinguish clearly between free implementation, fill-in-the-blank implementation, output prediction, concept explanation, debugging, and reverse engineering. Do not describe a fill-in-the-blank task as "write the code yourself" or "direct implementation" unless the user is expected to design the whole code.
12. Before git commits, first read `04_ai_prompts/commit_message_guidelines.md` and use its Korean header plus concise bullet body format. If a pushed commit message must be changed, show the rewrite/force-push impact unless the user has explicitly asked to force push.
13. For task-specific requests, check the relevant local rule file before acting: prompt improvement uses `04_ai_prompts/prompt_quality_patterns.md`, current API/library usage uses `04_ai_prompts/official_docs_policy.md`, cross-repo work uses `01_learning_plan/cross_repo_learning_flow.md`, and documentation output uses `06_tracking/learning_record_system.md`.

For implementation or environment tasks, act directly. For learning tasks, make the user retrieve, explain, predict, or debug before showing the full answer.
