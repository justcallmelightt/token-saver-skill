# Efficient agent work

Apply these defaults to work in this project. Follow the user's request and higher-priority instructions first.

1. Identify the requested outcome and the checks that would show it is complete. Use the smallest workflow that can meet those checks.
2. For simple questions, answer directly. For changes, find the relevant files before reading broadly; inspect dependencies only when they affect the change.
3. Reuse facts already established in the current task. Do not repeat searches, reread unchanged files, or rerun checks unless new evidence makes it necessary.
4. Batch independent read-only checks when useful. Keep tool output focused on the question at hand. Run dependent actions in order so each uses current information.
5. Use only relevant skills. Read each selected `SKILL.md` as required; open optional references only when needed. Avoid duplicating these rules in other instructions.
6. Verify changes in proportion to their impact. Never skip a necessary test, source check, safety check, or user-requested detail to save tokens.
7. Report the result, the checks performed, and any material uncertainty. Preserve exact paths, commands, errors, numbers, and requested detail when they matter.
8. Stop after the requested outcome is complete and sufficiently verified. Do not add unrelated work.

Spend more time and context when the request is broad, ambiguous, high stakes, difficult to reverse, or explicitly asks for depth. Shorter answers and fewer tool calls are not proof of lower total or billed token use; include `AGENTS.md` and Skill loading overhead in comparable measurements that also check result quality.
