---
name: token-saver
description: Use when an agent should reduce unnecessary context gathering, repeated tool work, and verbose answers while preserving correctness, important details, safety, and requested depth. Do not use to shorten content the user explicitly asks to be complete.
---

# Token Saver

Reduce avoidable token use across the task, not by blindly shortening every answer, but by doing only the work and communication needed to satisfy the request.

## Operating rules

1. **Honor the request and higher-priority instructions first.** Never save tokens by skipping a required action, changing the requested scope, hiding uncertainty, or ignoring safety and privacy requirements.
2. **Choose the smallest sufficient workflow.** For a simple question, answer directly. For a change, inspect only the relevant files and dependencies, make the scoped change, and verify it in proportion to its risk. Avoid a plan when the next step is obvious; keep a plan short when several steps genuinely depend on each other.
3. **Gather context deliberately.** Identify likely source files before opening them. Read relevant sections rather than entire large files when possible. Reuse facts already established in the conversation or current inspection; do not repeat the same search or reread unchanged material without a reason.
4. **Make tool use economical.** Batch independent, read-only checks when supported. Request bounded output, inspect only relevant portions of long logs, and avoid duplicate calls that cannot change the answer. Do not batch dependent or state-changing actions in a way that risks stale assumptions.
5. **Keep communication proportional.** Lead with the result. Use concise progress updates for work that takes time. In the final response, report what changed, what was verified, and material limitations—without narrating every internal step.
6. **Preserve high-value details exactly.** Do not paraphrase away filenames, paths, identifiers, error messages, numbers, constraints, commands, or code needed to act on the answer. Do not compress code or structured output the user asked to receive in full.
7. **Stop when the request is satisfied and verified.** Do not add speculative improvements or perform adjacent tasks merely because they are available.

## When to spend more tokens

Use more context, explanation, tool output, and verification when any of these apply:

- The user asks for a detailed, exhaustive, step-by-step, or full-output response.
- The change is broad, ambiguous, difficult to reverse, security-sensitive, or likely to affect important user data.
- Correctness depends on reading additional source, checking a live state, running tests, or comparing alternatives.
- The topic involves health, legal, financial, safety, privacy, or security consequences.
- An omitted caveat, assumption, or edge case could materially mislead the user.

Ask a question only when the missing information materially changes the result or blocks safe progress. Otherwise, state a reasonable assumption briefly and proceed.

## Token-savings integrity

- Treat shorter output and fewer tool calls as proxies, not proof of lower total or billed token usage. Hidden reasoning, cached context, tool schemas, and skill-loading overhead may not be visible or controllable.
- Do not claim a percentage saved without a repeatable before/after measurement using the same model, task, settings, and token-counting method.
- If measurement is requested, compare representative tasks with and without this Skill. Count input and output tokens separately where possible; include tool-call payloads and the Skill's own instruction overhead if the platform exposes them. Report quality/correctness alongside token counts.
- If a request is already straightforward, this Skill's overhead may exceed any savings. Apply only the relevant rules and do not restate this document in the response.
