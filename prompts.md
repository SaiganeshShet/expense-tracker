# Prompt library

Use these templates for scoped work. Replace bracketed text before submitting.

## New feature

**Context:** [Relevant app behavior, files, and existing conventions.]

**Goal:** [One feature to implement.]

**Constraints:** [Scope boundaries, dependencies, accessibility, and design constraints.]

**Acceptance criteria:** [Observable outcomes, each verifiable by a test.]

**Examples:** [Representative user input and expected UI or state.]

First return a brief implementation plan and wait for approval. Then implement only the approved scope on the current task branch, run relevant tests and lint, and summarize the changes and checks for the PR.

## Bug fix

**Context:** [Where the bug occurs and the relevant code.]

**Goal:** Fix [specific incorrect behavior] while preserving [expected behavior].

**Constraints:** [Avoid unrelated changes; identify any files or APIs that must not change.]

**Acceptance criteria:** [Reproduction and corrected behavior expressed as testable outcomes.]

**Examples:** [Steps to reproduce, actual result, and expected result.]

First return a brief diagnosis and fix plan; wait for approval before editing. Add or update a regression test, run relevant checks, and summarize the fix for the PR.

## Refactor

**Context:** [Code to refactor and why.]

**Goal:** Improve [specific structure or maintainability concern] without changing behavior.

**Constraints:** Do not change public behavior, UI, or dependencies unless explicitly approved.

**Acceptance criteria:** [Tests and checks that demonstrate behavior is unchanged.]

**Examples:** [Before/after structure or representative call sites.]

First return a plan and wait for approval. Make only the approved structural changes, run the relevant tests and lint, and summarize the result for the PR.

## Generate tests

**Context:** [Feature, implementation, and existing test setup.]

**Goal:** Add tests for [specific behavior and important edge cases].

**Constraints:** Do not modify production code or weaken assertions unless asked. Use stable, user-visible behavior and repository test conventions.

**Acceptance criteria:** [Each test's setup, action, and exact expected result.]

**Examples:** [Inputs and expected outputs, including invalid cases.]

First propose the test cases and wait for approval. Then add the tests, run them, and explain what each test proves. Reject tests that pass without exercising the stated behavior.

## Review diff

**Context:** [Task requirements and any relevant design constraints.]

**Goal:** Review the proposed diff for correctness, regressions, missing tests, and scope.

**Constraints:** Do not edit files. Report only actionable findings supported by the diff.

**Acceptance criteria:** Findings include severity, file and line, impact, and a concise fix suggestion; if none are found, say so.

**Examples:** [Known edge cases or acceptance criteria to verify.]

Inspect the complete diff and relevant tests. Separate confirmed issues from questions, and do not claim a test or command passed unless it was run.

## Commit message

**Context:** [What changed and why.]

**Goal:** Write one concise commit subject in imperative mood.

**Constraints:** Do not claim work that is not present in the diff; keep the subject within 72 characters.

**Acceptance criteria:** The subject describes the main change, uses the repository's commit style, and contains no trailing period.

**Examples:** `Add category filter to expense list`

Inspect the staged diff first. Return only the proposed subject unless asked for a body.

## Add expense: five-part feature prompt

**Context:** This is a React + Vite expense tracker. `src/App.jsx` owns expense state; the form accepts a title, amount, and one of Food, Travel, Bills, or Other.

**Goal:** Let a user add a valid expense and see it appear in the expense list.

**Constraints:** Keep state in `App`; use the existing component and styling conventions; do not add dependencies; do not store invalid expenses; provide accessible labels and validation feedback.

**Acceptance criteria (all must be tested):**

1. Submitting title `Lunch`, amount `12.50`, and category `Food` adds exactly one expense displaying those values.
2. Submitting a whitespace-only title does not add an expense and exposes a validation message.
3. Submitting a non-numeric amount does not add an expense.
4. Submitting an amount of `0` or a negative amount does not add an expense.
5. After a successful submission, the form is ready for another expense.

**Examples:** `Lunch`, `12.50`, `Food` is accepted; an empty title, `abc`, `0`, or `-5` is rejected and leaves the expense count unchanged.

First provide an implementation plan and wait for approval. Then implement only this feature on its task branch, add tests for every acceptance criterion, run relevant checks, and summarize the changes and test results for the PR.
