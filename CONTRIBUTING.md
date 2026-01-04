# Contributing to @workbench/core

This document defines the rules for contributing to the @workbench/core repository.

It is the single source of truth for:
- architecture constraints
- coding rules
- lifecycle and cleanup requirements

These rules apply to all contributors, including automated agents (Cursor Agent).

---

## Hard constraints (must follow)

1. No Node-only imports in core
- Do NOT import `fs`, `path`, `os`, `child_process`, etc.
- Do NOT assume DOM APIs exist.
- Core must remain environment-agnostic.

2. No side effects on import
- Do NOT start timers, open connections, or register global listeners during module evaluation.
- Keep module top-level code pure.

3. Explicit lifecycle & cleanup
- All resources created during runtime must be registered for cleanup.
- If you add any listener, timer, or handle, ensure there is a corresponding cleanup path.

4. Public API control
- Only export intended public symbols from `src/index.ts`.
- Internal helpers must live under `src/internal/*` and must NOT be exported.

5. Type safety
- Keep TypeScript strictness enabled.
- Avoid `any`. Use `unknown` and narrow when needed.

6. Keep changes minimal and scoped
- Do not refactor unrelated code.
- If refactoring seems necessary, create an issue first.
- Do not rename exported symbols unless explicitly requested or approved.

---

## Preferred patterns

### Installable lifecycle pattern
If you implement installables-related code, prefer:
- `register(ctx)` for pure registration
- `start(ctx)` for side effects
- `stop(ctx)` for cleanup

### Receipts and rollback
If adding registration APIs (e.g. slots), return a handle/receipt with:
- `unregister()` or
- `dispose()`

### Error handling
- Throw structured errors (e.g. `WorkbenchError`) for system-level failures.
- Never allow uncaught exceptions to crash the host process.
- Catch errors at well-defined boundaries where applicable.

---

## Deliverables for each task

When implementing an issue:
- Ensure `npm run build` passes.
- Ensure `npm run typecheck` passes.
- Update or add minimal documentation if public API or behavior changes.
- Update exports only when required.

---

## What NOT to do

- Do not add heavy dependencies without explicit instruction.
- Do not introduce protocol-specific code (MCP, tRPC, etc.) into core.
- Do not add CLI or application-specific code into core.

---

## Communication

- If an assumption is required, choose the simplest reasonable one and document it in code comments.
- Prefer clear, minimal comments explaining *why*, not *what*.
