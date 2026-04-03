# Generic Agent Adapter

This adapter is for agent frameworks other than Codex/OpenAI or Claude.

## Adapter Role

Treat [../core/specification.md](../core/specification.md) as the canonical source of truth. This adapter exists only to describe the minimum runtime contract needed to use the workflow in other agent environments.

## Minimum Runtime Expectations

- The runtime can receive student work and optional rubric or assignment context as text or file content.
- The runtime can produce plain-text or Markdown output.
- The runtime can keep a stable instruction source, either by reading the repository file directly or by loading an equivalent mirrored copy.

## Adapter Rules

1. Load [../core/specification.md](../core/specification.md) first.
2. Keep runtime-specific instructions limited to file-loading, packaging, or configuration concerns.
3. Do not replace the canonical workflow with framework-specific prompting conventions.
4. Preserve the canonical rules on evidence, grading restraint, tone, language, and output consistency.
5. Use [../references/feedback-guidelines.md](../references/feedback-guidelines.md) only as supporting guidance, not as a replacement for the core specification.
