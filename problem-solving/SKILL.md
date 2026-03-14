---
name: problem-solving
description: Apply problem-solving frameworks to find causes, break down ambiguity, and generate practical solution paths.
compatibility: opencode
metadata:
  audience: general
  workflow: problem-solving
---

# Problem Solving

## What this skill does

Use this skill when the main task is understanding a problem deeply enough to solve it well.

This domain covers decomposition, root causes, reframing, creative generation, and structured convergence on a solution path.

## When this domain is appropriate

Use it when the user is mainly asking:

- what is causing the problem
- how to break the problem down
- whether this is the right problem to solve
- how to generate better solution paths
- how to resolve conflicting constraints

Do not use it when the user already has clear options and mainly needs a recommendation or a message.

## Routing logic

- root-cause analysis by categories -> `frameworks/ishikawa-diagram.md`
- decompose a broad problem -> `frameworks/issue-trees.md`
- reframe at higher or lower abstraction -> `frameworks/abstraction-laddering.md`
- rebuild from fundamentals -> `frameworks/first-principles.md`
- identify failure paths and safeguards -> `frameworks/inversion.md`
- generate systematic solution combinations -> `frameworks/zwicky-box.md`
- resolve opposing constraints -> `frameworks/conflict-resolution-diagram.md`
- run end-to-end creative problem solving -> `frameworks/productive-thinking-model.md`

## Framework chaining

- `issue-trees.md` -> `ishikawa-diagram.md` when one branch needs root-cause depth
- `abstraction-laddering.md` -> `first-principles.md` when the framing itself is limiting
- `inversion.md` -> `zwicky-box.md` when you need both risk avoidance and creative generation
- `issue-trees.md` -> `productive-thinking-model.md` when a defined branch is ready for solution development

## Execution policy

Before applying a framework:

1. Write the problem in one sentence.
2. Separate known facts from assumptions.
3. Choose the framework that best reduces ambiguity.
4. Follow the selected framework file's process exactly.
5. End with the clearest next investigation, experiment, or solution path.

## Output contract

- `Goal:`
- `Chosen framework:`
- `Why this framework:`
- `Known facts:`
- `Assumptions:`
- `Reasoning:`
- `Result:`
- `Recommended next action:`

## Framework references

- `frameworks/ishikawa-diagram.md`
- `frameworks/abstraction-laddering.md`
- `frameworks/conflict-resolution-diagram.md`
- `frameworks/zwicky-box.md`
- `frameworks/productive-thinking-model.md`
- `frameworks/inversion.md`
- `frameworks/issue-trees.md`
- `frameworks/first-principles.md`
