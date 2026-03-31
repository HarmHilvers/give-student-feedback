# give-student-feedback

Draft, refine, and structure written feedback, feedforward, rubric-aligned comments, and grading notes for student work.

## What it does

This skill helps turn student work, assignment criteria, and rubric information into feedback that is specific, constructive, and usable. It is designed for requests such as:

- giving feedback on a student submission
- writing feedforward
- grading with justification
- giving rubric-by-rubric comments
- evaluating multiple students in a consistent format

The approach is built around concrete evidence from the work itself and the distinction between **feed up**, **feed back**, and **feed forward**.

## Installation

This repository is structured as a Codex skill: a folder with a `SKILL.md` file and optional supporting files. Codex discovers skills either from your global Codex home directory or from a project-local skills folder.

### Option 1: install globally

```bash
git clone https://github.com/HarmHilvers/give-student-feedback.git ~/.codex/skills/give-student-feedback
```

### Option 2: install in a project

```bash
mkdir -p .agents/skills
git clone https://github.com/HarmHilvers/give-student-feedback.git .agents/skills/give-student-feedback
```

After installation, restart Codex or start a new session so the skill can be discovered.

## Input

Provide as much of the following as possible:

- the student work or submission
- the assignment brief or task description
- the rubric, criteria, or learning objectives
- the grading scale, if grading is needed
- whether you want feedback, feedforward, grading, or a combination

## Output

Typical output includes:

- a concise overall judgment
- strengths with evidence from the work
- improvement points with evidence from the work
- 1–3 practical next steps
- grade justification when grading criteria are available

For rubric-based requests, feedback can be organized per criterion.

## Principles

- Base every comment on observable evidence in the work.
- Focus on the product, not the student as a person.
- Separate observation from interpretation.
- Be specific and actionable.
- Include both strengths and improvement points.
- Suggest directions for revision without rewriting the full text.
- Follow the user’s language.

## Default structure

1. **Feed up** — what the work is aiming at
2. **Feed back** — how the current work performs
3. **Feed forward** — what to do next

## Repository structure

- `SKILL.md` — skill instructions and workflow
- `references/feedback-guidelines.md` — feedback principles and rationale
- `agents/` — supporting agent configuration files
