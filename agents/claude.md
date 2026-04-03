# Claude Adapter

This adapter is for Claude and Claude-based runtimes.

## Adapter Role

Treat [../core/specification.md](../core/specification.md) as the canonical source of truth. This file only explains how Claude should load and apply that core specification.

## Loading Order

1. Load [../core/specification.md](../core/specification.md).
2. Load [../references/feedback-guidelines.md](../references/feedback-guidelines.md) only when pedagogical rationale or wording support is useful.
3. Apply the request using the canonical workflow and rules without redefining them here.

## Runtime Notes

- If the Claude runtime supports project knowledge or repository files, attach or reference the canonical core file directly.
- If the runtime does not support direct file loading, copy only the minimal canonical content needed to preserve behavior.
- Keep the adapter thin. Do not add Claude-specific behavior that changes grading thresholds, output structure, or evidence requirements.
- Preserve the canonical output behavior and language rules across Claude responses.
