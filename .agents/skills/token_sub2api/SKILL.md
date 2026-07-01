```markdown
# token_sub2api Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill provides guidance for contributing to the `token_sub2api` Go codebase. It covers the project's coding conventions, commit patterns, and the main workflows for updating frontend localization and maintaining backend OpenAI Codex model logic. By following these patterns, you can ensure consistency and reliability in your contributions.

## Coding Conventions

### File Naming

- Use **snake_case** for all file names.

  **Example:**
  ```
  openai_codex_transform.go
  billing_service_test.go
  ```

### Import Style

- Mixed import style is used; both grouped and single-line imports are present.

  **Example:**
  ```go
  import (
      "context"
      "fmt"
      "github.com/some/package"
  )
  ```

### Export Style

- Use **named exports** for functions, types, and variables that need to be accessed outside their package.

  **Example:**
  ```go
  // Exported function
  func TransformCodexModel(input string) string {
      // ...
  }

  // Unexported (internal) function
  func transformHelper() {
      // ...
  }
  ```

### Commit Patterns

- Follows **Conventional Commits**.
- Prefixes: `fix`, `feat`
- Commit message length: ~50 characters

  **Example:**
  ```
  feat: add support for new OpenAI Codex model
  fix: correct billing logic for Codex usage
  ```

## Workflows

### frontend-i18n-localization-update

**Trigger:** When updating, fixing, or cleaning up localized UI strings (e.g., English/Chinese) in the frontend.  
**Command:** `/update-i18n`

1. **Edit Vue component files** to update or fix UI strings.
   - Example: Update text in `frontend/src/components/MyComponent.vue`
2. **Update i18n locale files** with new or corrected translations.
   - Files: `frontend/src/i18n/locales/en.ts`, `frontend/src/i18n/locales/zh.ts`
   - Example:
     ```ts
     // en.ts
     export default {
       greeting: "Hello, world!",
     }
     // zh.ts
     export default {
       greeting: "你好，世界！",
     }
     ```
3. **Optionally update composables or utility files** related to localization.
   - Example: `frontend/src/composables/useI18n.ts`
4. **Optionally update or add related frontend tests.**
   - Example: `frontend/src/components/MyComponent.spec.ts`

### backend-openai-codex-model-fix-or-extension

**Trigger:** When fixing, extending, or adjusting OpenAI Codex model support (model names, reasoning context, billing), and verifying with tests.  
**Command:** `/fix-openai-codex`

1. **Edit Go backend service files** related to OpenAI Codex logic.
   - Example: `backend/internal/service/openai_codex_transform.go`
2. **Update or add Go test files** to cover new or fixed behavior.
   - Example: `backend/internal/service/openai_codex_transform_test.go`
3. **Optionally update related billing, alias, or mapping files.**
   - Files: `billing_service.go`, `openai_model_alias.go`, etc.

   **Sample Code Change:**
   ```go
   // openai_codex_transform.go
   func TransformCodexModel(model string) string {
       switch model {
       case "code-davinci-002":
           return "codex"
       default:
           return model
       }
   }
   ```

   **Corresponding Test:**
   ```go
   // openai_codex_transform_test.go
   func TestTransformCodexModel(t *testing.T) {
       got := TransformCodexModel("code-davinci-002")
       want := "codex"
       if got != want {
           t.Errorf("got %q, want %q", got, want)
       }
   }
   ```

## Testing Patterns

- **Test files** use the pattern `*_test.go` for Go and `*.spec.ts` for frontend.
- **Testing framework** is not explicitly detected, but standard Go `testing` package is likely used for backend.
- Place tests alongside the code they cover.

  **Example:**
  ```
  backend/internal/service/openai_codex_transform.go
  backend/internal/service/openai_codex_transform_test.go
  ```

## Commands

| Command           | Purpose                                                      |
|-------------------|--------------------------------------------------------------|
| /update-i18n      | Update or fix frontend localization/internationalization     |
| /fix-openai-codex | Fix or extend OpenAI Codex model logic in the backend        |
```