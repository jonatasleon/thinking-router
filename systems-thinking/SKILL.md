---
name: systems-thinking
description: Apply systems thinking frameworks to explain patterns, structures, relationships, and feedback loops.
compatibility: opencode
metadata:
  audience: general
  workflow: analysis
---

# Systems Thinking

## What this skill does

Use this skill to explain why a system behaves the way it does.

This domain is for recurring patterns, hidden structures, relationships, and feedback loops. It is not for choosing between options or drafting the final message.

## When this domain is appropriate

Use it when the user is mainly asking:

- why something keeps happening
- how a system works
- what relationships drive the outcome
- whether a loop is stabilizing or compounding

Do not use it when the main task is prioritization, recommendation between options, or interpersonal messaging.

## Routing logic

Choose the framework that matches the user's immediate need:

- recurring event with hidden causes -> `frameworks/iceberg-model.md`
- multiple interacting elements and causal links -> `frameworks/connection-circles.md`
- relationship or dependency mapping without loop focus -> `frameworks/concept-map.md`
- self-correcting or stabilizing dynamics -> `frameworks/balancing-feedback-loop.md`
- compounding or runaway dynamics -> `frameworks/reinforcing-feedback-loop.md`

## Framework chaining

Use more than one framework when the reasoning benefits from a sequence:

- `connection-circles.md` -> `balancing-feedback-loop.md` or `reinforcing-feedback-loop.md` to classify discovered loops
- `iceberg-model.md` -> `connection-circles.md` to move from deeper diagnosis to relationship mapping
- `connection-circles.md` -> `iceberg-model.md` to explain why a mapped loop exists

## Execution policy

Before applying a framework:

1. State the system boundary.
2. Separate facts from assumptions.
3. Choose one framework or a short sequence.
4. Follow the selected framework file's process exactly.
5. End with the highest-leverage intervention or next question.

## Output contract

- `Goal:`
- `Chosen framework:`
- `Why this framework:`
- `Known facts:`
- `Assumptions:`
- `Reasoning:`
- `System insight:`
- `Recommended next action:`

## Framework references

- `frameworks/iceberg-model.md`
- `frameworks/connection-circles.md`
- `frameworks/concept-map.md`
- `frameworks/balancing-feedback-loop.md`
- `frameworks/reinforcing-feedback-loop.md`
