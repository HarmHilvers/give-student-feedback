# Cross-Agent Compatibility Contract

This document defines the compatibility contract for all runtimes that use `give-student-feedback`.

## Scope

The contract applies to:

- Codex and other OpenAI-aligned runtimes
- Claude and Claude-based runtimes
- generic agent frameworks that can load instructions and produce text output

## Canonical Source Contract

- [../core/specification.md](../core/specification.md) is the single canonical source of truth for workflow, rules, output behavior, and portability expectations.
- Agent adapters must reference the canonical core instead of redefining it.
- If a runtime requires mirrored instructions outside this repository, the mirrored instructions must remain semantically equivalent to the canonical core.

## Adapter Contract

- Adapters must stay thin and runtime-specific.
- Adapters may define loading order, file attachment expectations, or runtime packaging notes.
- Adapters must not silently change the core workflow, grading rules, language defaults, or evidence requirements.
- Adapters may add runtime-specific guardrails only when they do not conflict with the canonical core behavior.

## Input Contract

Compatible runtimes must accept, directly or indirectly:

- student work or submission content
- optional assignment brief or task description
- optional rubric, criteria, or learning objectives
- optional grading scale
- optional instruction about output mode

If some inputs are missing, the runtime must preserve the canonical fallback behavior:

- make only minimal reasonable assumptions
- label assumptions clearly
- avoid fabricated evidence or fabricated grading standards

## Output Contract

Compatible runtimes must preserve these behaviors:

- comments are grounded in observable evidence from the work
- strengths and improvement points are both represented unless the user requests a narrower mode
- feed up / feed back / feed forward remains the default general-feedback structure
- grading is justified and clearly marked as provisional when the basis is incomplete
- responses stay respectful, direct, and focused on the work rather than the student's character
- the user's language remains the default output language

## Portability Contract

- The workflow must not depend on a specific operating system, shell, or toolchain.
- Repository file access is preferred but not required.
- If direct file access is unavailable, the runtime must use a semantically equivalent copy of the canonical core or request the missing content from the user.
- Plain text and Markdown are the baseline supported output formats.

## Non-Goals

This contract does not require:

- identical wording across runtimes
- identical UI affordances or host application integrations
- runtime-specific examples, scaffolding, or wrapper code inside this repository

It does require equivalent behavior at the level of workflow, guardrails, and output semantics.
