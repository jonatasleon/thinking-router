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

Use this skill when the user needs help choosing how to think before applying a framework.

The router should identify the real task, choose a primary domain, optionally choose a secondary domain, and propose the most likely framework or short framework sequence.

## Domain choices

- `systems-thinking` for patterns, structures, relationships, and feedback loops
- `decision-making` for choosing, prioritizing, sequencing, and acting under uncertainty
- `problem-solving` for decomposition, root-cause analysis, reframing, and solution generation
- `communication` for feedback, synthesis, and conclusion-first messaging

## Routing logic

### Route to systems thinking when the user is asking

- why something keeps happening
- how a system works
- what feedback loops exist
- what hidden structure drives a recurring issue

Likely frameworks:

- `systems-thinking/frameworks/iceberg-model.md`
- `systems-thinking/frameworks/connection-circles.md`
- `systems-thinking/frameworks/balancing-feedback-loop.md`
- `systems-thinking/frameworks/reinforcing-feedback-loop.md`

### Route to decision making when the user is asking

- which option to choose
- what to prioritize
- what kind of decision this is
- what long-term consequences follow from an action
- how fast to move under uncertainty

Likely frameworks:

- `decision-making/frameworks/hard-choice-model.md`
- `decision-making/frameworks/decision-matrix.md`
- `decision-making/frameworks/impact-effort-matrix.md`
- `decision-making/frameworks/second-order-thinking.md`
- `decision-making/frameworks/cynefin-framework.md`

### Route to problem solving when the user is asking

- what is causing the problem
- how to break it down
- whether they are solving the right problem
- how to generate solution paths
- how to resolve conflicting constraints

Likely frameworks:

- `problem-solving/frameworks/issue-trees.md`
- `problem-solving/frameworks/ishikawa-diagram.md`
- `problem-solving/frameworks/abstraction-laddering.md`
- `problem-solving/frameworks/first-principles.md`
- `problem-solving/frameworks/productive-thinking-model.md`

### Route to communication when the user is asking

- how to give feedback to someone
- how to turn analysis into a summary or recommendation
- how to structure a message for fast understanding

Likely frameworks:

- `communication/frameworks/situation-behavior-impact.md`
- `communication/frameworks/minto-pyramid.md`

## Prompt-question routing hints

- "Why is X happening?" -> `systems-thinking` -> `iceberg-model.md`
- "How does this system work?" -> `systems-thinking` -> `connection-circles.md`
- "What kind of decision am I making?" -> `decision-making` -> `hard-choice-model.md`
- "Which option is best?" -> `decision-making` -> `decision-matrix.md`
- "What should I be working on right now?" -> `decision-making` -> `eisenhower-matrix.md`
- "What happens after we do this?" -> `decision-making` -> `second-order-thinking.md`
- "Can I break this problem down?" -> `problem-solving` -> `issue-trees.md`
- "Am I solving the right problem?" -> `problem-solving` -> `abstraction-laddering.md`
- "How do I find the root cause?" -> `problem-solving` -> `ishikawa-diagram.md`
- "How do I give this feedback clearly?" -> `communication` -> `situation-behavior-impact.md`
- "How do I summarize this recommendation?" -> `communication` -> `minto-pyramid.md`

## Multi-domain guidance

Add a secondary domain only when it materially improves the result.

Common combinations:

- `problem-solving` -> `communication` when a solution must be packaged
- `decision-making` -> `communication` when a recommendation must be presented
- `systems-thinking` -> `problem-solving` when diagnosis should be followed by intervention design
- `systems-thinking` -> `communication` when a system insight needs executive summary form

## Output format

- `True goal:`
- `Primary domain:`
- `Secondary domain:` use `none` if not needed
- `Candidate framework(s):`
- `Why this route fits:`
- `Suggested next prompt:`

## Rule of use

Do not stop at naming the domain. Propose the framework or short sequence that should be applied next.
