---
name: communication
description: Apply communication frameworks to produce clear feedback, concise synthesis, and structured messages.
compatibility: opencode
metadata:
  audience: general
  workflow: communication
---

# Communication

## What this skill does

Use this skill to convert reasoning into communication that is clear, concise, and actionable.

This domain is both a primary domain for message drafting and a downstream packaging layer for outputs from systems thinking, decision making, and problem solving.

## When this domain is appropriate

Use it when the user is mainly asking:

- how to give feedback to a person
- how to summarize analysis for a stakeholder
- how to turn a recommendation into a clear memo or update
- how to structure a message for fast understanding

Do not use it as the primary tool when the real need is diagnosing the problem or making the decision itself.

## Routing logic

- feedback on observable behavior -> `frameworks/situation-behavior-impact.md`
- conclusion-first memo, update, or recommendation -> `frameworks/minto-pyramid.md`

## Domain handoffs

Use this skill after another domain when the reasoning exists but the message is weak.

- systems-thinking -> `minto-pyramid.md` for system insight summaries
- decision-making -> `minto-pyramid.md` for recommendations and tradeoff briefs
- problem-solving -> `minto-pyramid.md` for proposed solution summaries
- interpersonal issue identified elsewhere -> `situation-behavior-impact.md`

## Execution policy

Before applying a framework:

1. Identify audience, objective, and tone.
2. Confirm whether the message is feedback or synthesis.
3. Separate observed facts from interpretation.
4. Follow the selected framework file's process exactly.
5. End with copy-ready language when possible.

## Output contract

- `Goal:`
- `Chosen framework:`
- `Why this framework:`
- `Audience:`
- `Inputs:`
- `Reasoning:`
- `Final message:`
- `Recommended next action:`

## Framework references

- `frameworks/situation-behavior-impact.md`
- `frameworks/minto-pyramid.md`
