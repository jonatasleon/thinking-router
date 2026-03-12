---
name: thinking-router
description: Interpret a request, identify the primary thinking category, and route to the best specialized thinking skill.
compatibility: opencode
metadata:
  audience: general
  workflow: routing
---

# Thinking Router

## What this skill does

Use this skill when the user needs help deciding how to think about a request before applying a specific framework.

Your job is to:
- identify the user's true goal
- classify the request into one primary category
- optionally identify one secondary category when it will materially improve the result
- explain why the selected category fits
- recommend the most appropriate specialized skill, or load that standalone skill only through OpenCode's documented `skill` tool when available and permitted

## When to use it

Use this when the user:
- is unsure how to approach a problem
- asks for a thinking framework without naming one
- mixes diagnosis, prioritization, and communication in one request
- needs the right category selected before detailed analysis begins

## When not to use it

Do not use this when the user already clearly wants one category skill and the fit is obvious.

Do not fully execute every downstream framework here. Route first. Keep this skill focused on classification and handoff.

Do not rely on undocumented nested-skill behavior. Only recommend a separate category skill or load that standalone skill through the documented `skill` tool.

## Classification workflow

1. Identify the user's true goal.
2. Determine whether the main need is understanding a system, making a choice, solving a problem, or communicating clearly.
3. Select one primary category.
4. Add one secondary category only if it will materially improve the result.
5. Explain the classification in plain language.
6. Recommend the corresponding category skill, or load that standalone skill through the documented `skill` tool when available and permitted.
7. Tell the user what kind of result the specialized skill will produce.

Ask a clarifying question only if the request is too vague to classify usefully.

## Category definitions

- `systems-thinking`: for patterns, structures, relationships, and feedback loops
- `decision-making`: for choosing, prioritizing, sequencing, and managing tradeoffs
- `problem-solving`: for root causes, decomposition, solution generation, and conflict resolution
- `communication`: for feedback, concise synthesis, and message structure

## Output format

- `True goal:`
- `Primary category:`
- `Secondary category:` use `none` if not needed
- `Why this category fits:`
- `Recommended skill:`
- `Suggested next prompt:`

Keep the output practical. Prefer a short, confident routing decision over a long theory lesson.

## Example triggers

- Help me figure out how to think about this stalled initiative.
- I am not sure whether this is a system problem or a decision problem.
- Route this request to the best thinking framework category.
