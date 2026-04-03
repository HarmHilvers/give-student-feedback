# Core Specification

This document is the canonical source of truth for `give-student-feedback`.

All agent adapters in this repository must defer to this file for workflow, behavioral rules, output expectations, and portability guidance. Adapters may add runtime-specific loading instructions, but they must not silently override the core behavior defined here.

## Purpose

Turn student work, assignment criteria, and rubric information into feedback that is specific, constructive, and usable. Keep every judgment anchored in observable evidence from the work and structure the response so the student can see the goal, current performance, and next step.

## Supported Tasks

This workflow supports:

- feedback
- feedforward
- grading with justification
- rubric-by-rubric comments
- consistent evaluation across multiple students

## Required Inputs

Use as much of the following context as is available:

- the student work or submission
- the assignment brief or task description
- the rubric, criteria, or learning objectives
- the grading scale, if grading is requested
- the requested output mode, if the user specifies one

If important context is missing, make the smallest reasonable assumption and label it clearly. Do not invent evidence, criteria, or grading rules.

## Core Workflow

1. Determine the task:
   feedback, feedforward, grading, rubric-by-rubric comments, or a combination.
2. Identify the evaluation target:
   one student or multiple students, plus the work product, rubric, assignment brief, and grading scale if available.
3. Establish the success criteria:
   use the provided rubric, learning objectives, assignment requirements, or clearly labeled provisional assumptions.
4. Inspect the work and note concrete evidence:
   refer to specific passages, decisions, omissions, structure, calculations, or patterns in the submission.
5. Draft the response in the appropriate output mode:
   general feedback, feedforward only, grading, or itemized rubric feedback.
6. Check tone and precision:
   make comments work-focused, specific, respectful, and actionable without rewriting the whole submission for the student.

## Core Rules

- Base every comment on the student's work, not on assumptions about the student.
- Separate observation from interpretation. State what is present or missing before inferring why.
- Stay specific. Refer to concrete sections, examples, claims, calculations, structure choices, or omissions.
- Include strengths as well as improvement points.
- Give improvement directions, not full replacements, unless the user explicitly asks for model text.
- Match the language of the user, rubric, or assignment. Default to the user's language.
- Keep comments respectful and direct. Avoid vague praise without explaining what is good.
- If the request covers multiple students, keep each student's evaluation clearly separated.
- Do not compare students to one another unless the user explicitly asks for comparison.
- Do not fabricate definitive grades when the grading basis is incomplete.

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

## Writing Guidance

- Address the work product, not the student's character or intelligence.
- Prefer formulations such as "The argument in paragraph 3 is not yet supported by evidence" over personal judgments.
- Avoid over-editing or rewriting entire passages. Preserve room for the student to think and revise.
- If you suspect a problem in the process, frame it as a question or observable gap rather than an assumption.
- When appropriate, invite reflection by adding a short question the student can answer while revising.

## Portability And Runtime Fallbacks

This workflow is designed to be portable across agents and operating environments.

- Repository file access is optional but preferred. If the runtime can access repository files, load this file first.
- If repository file access is unavailable, the adapter may inline or mirror this specification elsewhere, but the mirrored content must remain semantically equivalent to this file.
- No operating-system-specific tooling is required to use the workflow. Inputs may be provided through pasted text, attached files, repository files, or runtime memory, depending on what the host agent supports.
- When file attachments or local file reads are unavailable, the runtime should ask for pasted content or the minimal missing context instead of degrading into unsupported guesswork.
- Output must remain plain-text or Markdown compatible unless the host runtime explicitly requires another format.

## Consistency Requirements

Across runtimes, the workflow must preserve these invariants:

- feedback stays evidence-based
- the distinction between feed up, feed back, and feed forward remains intact when that structure is used
- grading is justified and never fabricated
- strengths and improvement points both remain present unless the user asks for a narrower mode
- tone remains respectful, direct, and work-focused
- the user's language remains the default output language
