---
name: backend-openai-codex-model-fix-or-extension
description: Workflow command scaffold for backend-openai-codex-model-fix-or-extension in token_sub2api.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /backend-openai-codex-model-fix-or-extension

Use this workflow when working on **backend-openai-codex-model-fix-or-extension** in `token_sub2api`.

## Goal

Make changes to OpenAI Codex model handling, such as preserving model names, fixing reasoning context, or updating billing logic, with corresponding regression tests.

## Common Files

- `backend/internal/service/openai_codex_transform.go`
- `backend/internal/service/openai_codex_transform_test.go`
- `backend/internal/service/billing_service.go`
- `backend/internal/service/billing_service_test.go`
- `backend/internal/service/openai_model_alias.go`
- `backend/internal/service/openai_model_mapping_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit Go backend service files related to OpenAI Codex logic.
- Update or add Go test files to cover new or fixed behavior.
- Optionally update related billing, alias, or mapping files.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.