---
name: give-student-feedback
description: Draft, refine, and structure written feedback, feedforward, rubric-aligned comments, and grading notes for student work. Use when Codex needs to evaluate one or more student submissions, respond to prompts such as "give feedback on this student's work", "give feedforward", "grade this work", or "give itemized feedback per rubric item", and produce specific, constructive, work-focused comments that help students improve.
---

# Give Student Feedback

This file is the Codex/OpenAI adapter for this repository.

The canonical instructions live in [core/specification.md](core/specification.md). Read that file first and treat it as the source of truth for workflow, rules, output behavior, and portability requirements.

Read [references/feedback-guidelines.md](references/feedback-guidelines.md) when you need pedagogical rationale or sharper wording for feedback principles.

## Adapter Rules

1. Follow [core/specification.md](core/specification.md) as written.
2. Keep this adapter thin. Do not redefine the workflow here unless a Codex-specific integration detail is required.
3. Preserve the canonical output behavior:
   evidence-based comments, clear separation of strengths and improvement points, and feed up / feed back / feed forward structure when applicable.
4. If the runtime can open repository files directly, load the canonical core file instead of copying or paraphrasing it into a new local standard.
5. If the runtime cannot reliably open repository files, inline only the minimal canonical sections needed to preserve behavior.
6. Do not fabricate grades, rubric criteria, or evidence that are not present in the provided material.
7. Match the user's language unless the user explicitly requests another language.
