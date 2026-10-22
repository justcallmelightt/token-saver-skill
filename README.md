[English](README.md) | [한국어](README.ko.md)

# AGENTS.md

Token Saver is a short [`AGENTS.md`](AGENTS.md) template for reducing avoidable context gathering, repeated tool work, and overlong answers while keeping the checks a task needs.

## Use it in a project

Add the contents of [`AGENTS.md`](AGENTS.md) to the `AGENTS.md` at the root of the project where you want these defaults to apply. If that project already has an `AGENTS.md`, merge the rules into it and keep its existing project instructions. Review the merged instructions for conflicts before using them.

Agents that read `AGENTS.md` will use this file when working inside this repository. Linking to it from another project does not make an agent read it there; put the instructions in the project where the agent works.

Keep always-on instructions short. Put task-specific procedures in Skills, keep each `SKILL.md` entrypoint concise, and move optional detail to separate references. Follow the client's rules for reading a selected `SKILL.md` in full.

## Designed to keep instruction overhead low

This repository ships one compact `AGENTS.md` and no `SKILL.md`. Its rules guide the agent to inspect only relevant context, avoid repeated tool work, and select installed specialized Skills only when the task calls for them. Required Skill instructions are read in full; optional references are loaded on demand. The template also avoids repeating the same rule across instruction files.

This is how Token Saver is designed to reduce avoidable token use, including its own instruction overhead. It does not guarantee lower total or billed tokens; short tasks may still cost more because the template is loaded.

## Evaluate it

Compare representative tasks with and without these instructions, using the same model, settings, and environment. Include a simple question, a focused code change, a task with long tool output, and a broad or high-stakes request. Record result quality and completeness alongside input/output tokens, tool calls, and elapsed time. Include `AGENTS.md`, selected `SKILL.md` files, and optional reference-loading costs where measurable. Do not claim a savings percentage from transcript length alone.
