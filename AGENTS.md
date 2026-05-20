# Local Learning Instructions

This workspace is a local AI-assisted learning system.

When the user asks to study, review, start today, continue, quiz, explain, or check weak points, first read:

- `AI_STUDY_OPERATING_RULES.md`
- `04_ai_prompts/method_router.md`
- `02_methods/practice_loop.md`
- `01_learning_plan/master_plan.md`
- `03_subjects/python/roadmap.md`
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
8. Keep records in the local folder structure.

For implementation or environment tasks, act directly. For learning tasks, make the user retrieve, explain, predict, or debug before showing the full answer.
