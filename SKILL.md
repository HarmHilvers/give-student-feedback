---
name: give-student-feedback
description: Draft, refine, and structure written feedback, feedforward, rubric-aligned comments, and grading notes for student work. Use when Codex needs to evaluate one or more student submissions, respond to prompts such as "give feedback on this student's work", "give feedforward", "grade this work", or "give itemized feedback per rubric item", and produce specific, constructive, work-focused comments that help students improve.
---

# Give Student Feedback

## Overview

Turn student work, assignment criteria, and rubric information into feedback that is specific, constructive, and usable. Keep every judgment anchored in observable evidence from the work and structure the response so the student can see the goal, current performance, and next step.

Read [references/feedback-guidelines.md](references/feedback-guidelines.md) when you need the pedagogical rationale or sharper wording for feedback principles.

## Workflow

1. Determine the task:
   feedback, feedforward, grading, rubric-by-rubric comments, or a combination.
2. Identify the target:
   one student or multiple students, plus the work product, rubric, assignment brief, and grading scale if available.
3. Establish the success criteria:
   use the provided rubric, learning objectives, or assignment requirements.
4. Inspect the work and note concrete evidence:
   quote or point to specific passages, decisions, omissions, or patterns in the submission.
5. Draft the response in three layers where applicable:
   feed up, feed back, and feed forward.
6. Check tone and precision:
   make comments work-focused, specific, and actionable without rewriting the whole submission for the student.

## Core Rules

- Base every comment on the student's work, not on assumptions about the student.
- Separate observation from interpretation. Say what is present or missing before inferring why.
- Stay specific. Refer to concrete sections, examples, claims, calculations, structure choices, or omissions.
- Include strengths as well as improvement points.
- Give improvement directions, not full replacements, unless the user explicitly asks for model text.
- Match the language of the user, rubric, or assignment. Default to the user's language.
- Keep comments respectful and direct. Avoid vague praise such as "good job" without explaining what is good.
- If the request covers multiple students, keep each student's evaluation clearly separated and do not compare students to one another unless the user explicitly asks for comparison.

## Output Modes

### General Feedback

Use this structure unless the user asks for another format:

1. Feed up:
   state the relevant goal, learning objective, rubric criterion, or expected standard.
2. Feed back:
   explain how the current work aligns or does not align, using concrete evidence.
3. Feed forward:
   suggest the next revision step or practice focus.

Keep feedforward small enough to act on. Prefer one to three high-value next steps over a long list.

### Feedforward Only

Focus on what the student can do next. Still ground advice in the current work:

- identify the current gap briefly
- give a concrete direction for improvement
- explain why that step matters for the criterion or learning goal

### Grading

Assign a grade only when the basis is explicit enough to defend:

- use the provided rubric, criteria, scale, or grading instructions
- justify each grade with evidence from the submission
- make uncertainty explicit if criteria are incomplete or ambiguous

If formal grading criteria are missing, avoid fabricating a definitive grade. Offer either:

- a provisional judgment labeled as provisional, or
- a feedback-only response plus a short note about the missing criteria needed for formal grading

### Itemized Rubric Feedback

Organize the response by rubric item. For each item, include:

- criterion or rubric item
- current performance
- evidence from the work
- next step

Use a table only if it improves readability for the amount of content. Otherwise use short subsections or bullets.

## Writing Guidance

- Address the work product, not the student's character or intelligence.
- Prefer formulations such as "The argument in paragraph 3 is not yet supported by evidence" over "You were careless here."
- Avoid over-editing or rewriting entire passages. Preserve room for the student to think and revise.
- If you suspect a problem in the process, frame it as a question or observable gap rather than an assumption.
- When appropriate, invite reflection by adding a short question the student can answer while revising.

## Response Patterns

### Single Student

Default to a compact structure:

- summary of overall performance
- 2-4 strengths with evidence
- 2-4 improvement points with evidence
- 1-3 feedforward actions

### Multiple Students

Repeat a consistent structure per student:

- student identifier
- concise overall judgment
- strengths
- improvement points
- feedforward or grade justification

### Limited Context

If the user provides only the work and no rubric:

- infer likely goals from the assignment or genre
- state the assumptions briefly
- avoid false precision in grading

If the user provides only a rubric and asks for a template:

- draft a feedback template aligned to the rubric
- keep placeholders easy to fill with evidence later
