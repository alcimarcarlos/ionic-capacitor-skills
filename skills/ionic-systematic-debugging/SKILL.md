---
name: ionic-systematic-debugging
description: "Systematic root-cause debugging protocol for Ionic, Capacitor, and Angular: prohibits guessing, enforces minimal failing unit/integration tests, single-variable fixes, and mobile bridge verification."
license: UNLICENSED
---

# Ionic / Capacitor Systematic Debugging

## Objective

Eliminate guesswork ("shotgun debugging") by enforcing a strict 4-step scientific debugging method for triaging and resolving defects in Ionic Angular apps and Capacitor native bridges.

## Compatibility (Cursor, Codex, Claude Code)

- Strict operational gate: agents must not alter production source code until a minimal failing test reproducer or automated assertion is written.
- Always isolate whether the failure is in the UI layer (Angular/Signals/Zone), Capacitor bridge, or backend API response.

## Mandatory 4-Step Protocol

### Step 1: Formulate Root-Cause Hypothesis
- Inspect the browser/webview console, Xcode/Android Studio logcat, and network tab.
- Determine the failure layer: Angular UI binding, Capacitor Native Plugin, or Laravel HTTP DTO.
- Formulate an explicit hypothesis: *"The bug occurs because service X invokes native plugin Y without checking `Capacitor.isNativePlatform()`, throwing an unhandled rejection on web."*

### Step 2: Create Minimal Failing Reproducer
- Create or add a test in `src/app/...spec.ts` using Jasmine/Karma/Jest that directly triggers the reported condition.
- Run the test:
  ```bash
  npm test -- --include src/app/path/to/bug-reproducer.spec.ts
  ```
- **Verification Gate**: The test MUST fail with the reported error.

### Step 3: Surgical Fix (Single Variable)
- Make the smallest possible change to resolve the root cause.
- Follow the **Minimal Diff Mandate**: never rewrite unaffected components or services.

### Step 4: Non-Regression Verification
- Re-run the reproducer test to verify it passes.
- Run the full test suite and build verification:
  ```bash
  npm test -- --watch=false
  npx ionic build
  ```

## Anti-Patterns (Strictly Forbidden)

- **Shotgun Debugging**: Modifying multiple Angular templates and services without proving the root cause.
- **Unchecked Native Calls**: Invoking `@capacitor/*` plugins without web fallbacks or platform guards.
- **Silent Catch**: Swallowing native bridge exceptions in `.catch(() => {})` without user feedback or state recovery.

## Additional Resources

- Read `reference.md` for triage commands and reproducer templates.
