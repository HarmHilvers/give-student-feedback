# give-student-feedback

Draft, refine, and structure written feedback, feedforward, rubric-aligned comments, and grading notes for student work.

## Runtime Model

This repository uses a thin multi-agent runtime model:

- `core/specification.md` is the canonical, vendor-neutral source of truth.
- `agents/` contains thin runtime adapters that point back to the canonical core.
- `references/` contains supporting pedagogical guidance.
- `docs/` contains compatibility and regression documents for cross-agent use.

The workflow is intentionally agent-agnostic. Runtime-specific files exist only to help a host agent load and apply the same core behavior consistently.

## Installation And Use For Codex/OpenAI

Codex can use this repository as a skill repository entry, with `SKILL.md` acting as the Codex/OpenAI adapter and `core/specification.md` as the canonical core.

Global install:

```bash
git clone https://github.com/HarmHilvers/give-student-feedback.git ~/.codex/skills/give-student-feedback
```

Project-local install:

```bash
mkdir -p .agents/skills
git clone https://github.com/HarmHilvers/give-student-feedback.git .agents/skills/give-student-feedback
```

For OpenAI-aligned runtimes that consume adapter metadata, use `agents/openai.yaml` together with the canonical core file. The adapter should remain thin and defer to `core/specification.md`.

## Use For Claude

Use `agents/claude.md` as the Claude-specific adapter and load `core/specification.md` first.

If the Claude runtime supports repository files or project knowledge, point it at the canonical core file directly. If it does not, mirror the canonical core into the runtime's instruction mechanism without changing its semantics.

## Use For Other Agents

Use `agents/generic.md` as the minimum adapter for other frameworks.

Any compatible runtime should:

- load `core/specification.md` as the primary instruction source
- accept student work and optional rubric or assignment context
- produce plain-text or Markdown output
- preserve the canonical behavior around evidence, tone, grading restraint, and language defaults

## Compatibility And Regression Documents

- `docs/compatibility-contract.md` defines the cross-agent compatibility contract.
- `docs/acceptance-criteria.md` defines explicit acceptance and non-regression criteria.

## Principles

- Base every comment on observable evidence in the work.
- Focus on the work product, not the student as a person.
- Separate observation from interpretation.
- Be specific and actionable.
- Include strengths as well as improvement points.
- Suggest directions for revision without rewriting the full submission unless explicitly requested.
- Follow the user's language by default.

## Repository Structure

- `core/specification.md` - canonical vendor-neutral workflow and behavior
- `SKILL.md` - Codex/OpenAI adapter
- `agents/openai.yaml` - OpenAI-aligned metadata adapter
- `agents/claude.md` - Claude adapter
- `agents/generic.md` - generic adapter for other runtimes
- `references/feedback-guidelines.md` - supporting pedagogical guidance
- `docs/compatibility-contract.md` - cross-agent compatibility contract
- `docs/acceptance-criteria.md` - explicit acceptance and regression criteria
