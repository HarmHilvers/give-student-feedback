# Acceptance Criteria

These criteria define when this repository is considered compatible and non-regressive across supported agent runtimes.

## Canonical Core

- Pass: [../core/specification.md](../core/specification.md) exists and is the documented source of truth.
- Pass: central workflow, rules, output modes, and portability guidance live in the canonical core.
- Fail: the primary workflow exists only in a runtime-specific adapter.

## Adapter Thinness

- Pass: adapters primarily reference the canonical core and add only runtime-specific loading or packaging guidance.
- Pass: Codex/OpenAI support remains present.
- Pass: Claude support exists as a dedicated adapter.
- Pass: a generic adapter exists for other runtimes.
- Fail: an adapter introduces a conflicting workflow, grading rule, or output structure without updating the canonical core.

## Behavioral Consistency

- Pass: all runtimes preserve evidence-based feedback.
- Pass: all runtimes preserve the default feed up / feed back / feed forward structure for general feedback unless the user asks for another format.
- Pass: all runtimes preserve strengths plus improvement points unless the user requests a narrower mode.
- Pass: grading is justified and not fabricated when criteria are incomplete.
- Pass: output remains respectful, direct, and focused on the work.
- Pass: output defaults to the user's language.
- Fail: any runtime defaults to invented grades, invented rubric criteria, or unsupported assumptions about the student.

## Portability

- Pass: tool and OS assumptions are described portably, with fallbacks when direct file access is unavailable.
- Pass: the repository can be used through direct file loading or through a semantically equivalent mirrored copy of the canonical core.
- Fail: successful use depends on a single vendor runtime, a single operating system, or a single tool integration.

## Documentation

- Pass: [../README.md](../README.md) documents the runtime model, Codex/OpenAI usage, Claude usage, generic usage, and repository structure.
- Pass: [../docs/compatibility-contract.md](../docs/compatibility-contract.md) defines the cross-agent contract.
- Fail: supported runtimes are unclear or require reading adapter files to understand the repository model.

## Regression Boundary

- Pass: the repository change remains documentation and configuration oriented, without unnecessary functional rebuilds.
- Fail: the repository introduces large new framework-specific logic where lightweight adapters and documentation would be sufficient.
