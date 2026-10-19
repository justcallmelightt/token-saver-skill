[English](README.md) | [한국어](README.ko.md)

# Token Saver Skill

An Agent Skill for cutting avoidable context gathering, repeated tool work, and overlong answers—without treating brevity as more important than correctness.

## What it is (and is not)

[`token-saver/SKILL.md`](token-saver/SKILL.md) gives an agent a lightweight workflow for using fewer unnecessary tokens during a task. It does not change a model's tokenizer, guarantee lower API billing, or reduce tokens hidden inside a platform's reasoning or tool infrastructure. A short task may not benefit because loading the Skill has its own token cost.

The central trade-off is deliberate: do not save tokens by skipping necessary source inspection, tests, safety checks, or details the user asked to keep. For complex or high-stakes work, the right answer can require more tokens.

## Contents

- [`token-saver/SKILL.md`](token-saver/SKILL.md) — portable Skill instructions.
- [`token-saver/agents/openai.yaml`](token-saver/agents/openai.yaml) — optional OpenAI/Codex UI metadata; the core Skill does not depend on it.

## Install/use

Use the `token-saver/` directory as the Skill folder in an Agent Skills-compatible client. For clients with a skills installer, select the `token-saver` skill from this repository; otherwise, copy the folder into that client's documented skills directory. Keep the directory name and the frontmatter `name` as `token-saver`.

This repository is private for initial review. No public release or measured savings claim is being made yet.

## How to evaluate it

Compare the same representative tasks with and without the Skill, using the same model and settings:

1. A direct factual question that should need no tools.
2. A small code change that needs one relevant file inspection and a focused test.
3. A verbose tool output where only a specific error or result matters.
4. A broad or high-stakes request where required detail and checks must not be cut.

Track input and output tokens separately if the client exposes them, note tool calls and elapsed time, and score whether the result remains correct and complete for the request. Include the Skill's instruction overhead. Do not infer token savings from a shorter-looking transcript alone.

## Feedback wanted

Please review whether the guidance actually changes agent behavior, where it over-compresses or adds friction, and whether the evaluation cases reflect real work. The next iteration should be based on those observations rather than an unsupported savings percentage.
