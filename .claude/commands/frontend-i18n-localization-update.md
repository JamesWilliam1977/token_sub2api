---
name: frontend-i18n-localization-update
description: Workflow command scaffold for frontend-i18n-localization-update in token_sub2api.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /frontend-i18n-localization-update

Use this workflow when working on **frontend-i18n-localization-update** in `token_sub2api`.

## Goal

Update or fix localization/internationalization strings in the frontend, often to add, correct, or remove localized UI text in multiple languages.

## Common Files

- `frontend/src/components/**/*.vue`
- `frontend/src/i18n/locales/en.ts`
- `frontend/src/i18n/locales/zh.ts`
- `frontend/src/composables/**/*.ts`
- `frontend/src/components/**/*.spec.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit Vue component files to update or fix UI strings.
- Update i18n locale files (e.g., en.ts, zh.ts) with new or corrected translations.
- Optionally update composables or utility files related to localization.
- Optionally update or add related frontend tests.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.