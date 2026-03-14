# Thinking Router Analysis

## Current Architecture

The repository currently has five top-level skills:

- `thinking-router/SKILL.md`
- `systems-thinking/SKILL.md`
- `decision-making/SKILL.md`
- `problem-solving/SKILL.md`
- `communication/SKILL.md`

### What exists today

- `thinking-router` routes requests into one of four domains.
- Each domain skill contains:
  - a short domain description
  - when to use / when not to use
  - a framework selection list
  - one generic working method
  - one generic output format

### What is working

- The top-level domain split is sound.
- Framework coverage is already aligned with Untools at the inventory level.
- The current skills are easy to read and lightweight.

### What is weak

The current implementation is shallow for LLM reasoning because the frameworks are only named, not operationalized.

Current skills mostly do this:

- identify domain
- choose framework by one-line description
- apply a generic 5-6 step process regardless of framework

That means the framework choice changes the label, but not the actual reasoning behavior.

## Framework Inventory From Untools

### Systems Thinking

1. Iceberg Model
2. Connection Circles
3. Concept Map
4. Balancing Feedback Loop
5. Reinforcing Feedback Loop

### Decision Making

1. Six Thinking Hats
2. Eisenhower Matrix
3. Second-order Thinking
4. Decision Matrix
5. Impact-Effort Matrix
6. Ladder of Inference
7. Hard Choice Model
8. OODA Loop
9. Cynefin Framework
10. Confidence Determines Speed vs. Quality

### Problem Solving

1. Ishikawa Diagram
2. Abstraction Laddering
3. Conflict Resolution Diagram
4. Zwicky Box
5. Productive Thinking Model
6. Inversion
7. Issue Trees
8. First Principles

### Communication

1. Situation-Behavior-Impact
2. Minto Pyramid

## Coverage Comparison

### Inventory coverage

The current repo already includes all Untools frameworks across the four domains.

There is no major framework missing from the current skill set.

### Structural coverage

What is missing is not framework names, but framework architecture:

- no `frameworks/` directories
- no per-framework files
- no reusable framework protocols
- no dynamic framework loading/reference model inside domain skills
- no domain-level orchestration beyond simple framework picking

## Gap Analysis

### 1. The router is only a domain router, not a reasoning router

Current `thinking-router` stops at domain classification.

What it should do:

- classify the true task
- identify primary domain
- identify optional secondary domain
- predict likely framework candidates
- explain why
- hand off with the right inputs

Example:

- current behavior: "Use decision-making"
- better behavior: "Use decision-making -> Hard Choice Model first to classify the decision, then Decision Matrix if options are comparable, then Second-order Thinking to stress-test the winner"

That is a major difference in reasoning quality.

### 2. Frameworks are listed, but not operationalized

Current domain skills reduce frameworks to one-line selectors like:

- "Use `Decision Matrix` for weighted option comparison"
- "Use `Iceberg Model` for event -> pattern -> structure -> mental model analysis"

This is not enough for an LLM.

A real framework file should define:

- the mental move the model must make
- what inputs are required
- what evidence is valid
- what order to reason in
- when to stop
- how to format outputs
- what failure modes to avoid

Without that, the LLM falls back to generic reasoning and merely names the framework.

### 3. All frameworks currently share nearly the same process

Current domain skills use the same structure repeatedly:

- state goal
- choose framework
- explain why
- apply it step by step
- give result
- recommend next action

That is useful as a wrapper, but it is not framework-specific cognition.

Examples:

- `Decision Matrix` should force criteria, weights, scores, and sensitivity checks.
- `Ladder of Inference` should force separation of observation, selected data, interpretation, assumptions, conclusions, and action.
- `Issue Trees` should force MECE decomposition and branch prioritization.
- `Minto Pyramid` should force conclusion-first structure and support hierarchy.

Right now, none of those are encoded strongly enough.

### 4. No framework-specific "When NOT To Use"

Untools gives directional guidance, but the repo does not turn that into operational guardrails.

Examples:

- `Decision Matrix` should not be used when options are not meaningfully comparable.
- `Impact-Effort Matrix` should not be used when impact is too uncertain to estimate.
- `Six Thinking Hats` should not be used when the task is narrow and analytical rather than perspective-balancing.
- `Minto Pyramid` should not be used for emotionally delicate interpersonal feedback.
- `SBI` should not be used when the speaker lacks specific observed behavior.

Framework misapplication is one of the biggest sources of shallow reasoning.

### 5. No diagnostic question sets at framework level

Untools implicitly contains routing prompts, especially in the tools guide. Those should be converted into domain/framework selectors.

Examples:

- "Am I jumping to conclusions?" -> Ladder of Inference
- "What kind of decision am I making?" -> Hard Choice Model
- "Why is X happening?" -> Iceberg Model
- "Can I break this problem down?" -> Issue Trees

This should become explicit selection logic inside each domain skill.

### 6. No chaining or composition model

Real reasoning often needs multiple frameworks in sequence.

Examples:

#### Systems Thinking

- Connection Circles -> identify loops
- Reinforcing/Balancing Feedback Loop -> classify dynamics
- Iceberg Model -> connect loops to deeper structures and mental models

#### Decision Making

- Hard Choice Model -> classify the decision type
- Decision Matrix or Impact-Effort Matrix -> compare options
- Second-order Thinking -> stress-test consequences
- Ladder of Inference -> check assumptions before final recommendation

#### Problem Solving

- Issue Trees -> decompose
- Ishikawa Diagram -> root causes
- First Principles -> rebuild from fundamentals
- Inversion or Zwicky Box -> widen solution search
- Productive Thinking Model -> converge into execution

#### Communication

- upstream domain skill generates reasoning
- Minto Pyramid packages recommendation
- SBI packages behavioral feedback

Current skills treat frameworks as isolated picks rather than composable protocols.

### 7. No common output contract for LLM reasoning quality

To make these useful as LLM reasoning skills, every framework should consistently produce:

- problem/decision/system statement
- known facts vs assumptions
- selected framework and why
- reasoning steps
- intermediate artifacts
- output / recommendation / insight
- confidence or open uncertainties
- recommended next action

The current skills gesture at this, but they do not enforce enough structure.

### 8. Communication is underpowered as a downstream synthesis layer

Communication is currently treated as a standalone skill with only two frameworks.

That is correct at the inventory level, but incomplete architecturally.

Communication should be positioned as:

- a standalone domain when the user's primary need is messaging
- a downstream packaging layer for outputs from other domains

Examples:

- systems analysis -> Minto Pyramid summary
- decision recommendation -> executive brief via Minto Pyramid
- interpersonal issue found during problem-solving -> SBI draft

## Proposed Architecture

### Directory structure

```text
skills/
  thinking-router/
    skill.md

  systems-thinking/
    skill.md
    frameworks/
      iceberg-model.md
      connection-circles.md
      concept-map.md
      balancing-feedback-loop.md
      reinforcing-feedback-loop.md

  decision-making/
    skill.md
    frameworks/
      six-thinking-hats.md
      eisenhower-matrix.md
      second-order-thinking.md
      decision-matrix.md
      impact-effort-matrix.md
      ladder-of-inference.md
      hard-choice-model.md
      ooda-loop.md
      cynefin-framework.md
      confidence-determines-speed-vs-quality.md

  problem-solving/
    skill.md
    frameworks/
      ishikawa-diagram.md
      abstraction-laddering.md
      conflict-resolution-diagram.md
      zwicky-box.md
      productive-thinking-model.md
      inversion.md
      issue-trees.md
      first-principles.md

  communication/
    skill.md
    frameworks/
      situation-behavior-impact.md
      minto-pyramid.md
```

### Domain skill responsibilities

Each domain `skill.md` should do four things well:

#### 1. Explain the domain

- what type of reasoning this domain handles
- what kinds of user goals fit here
- what kinds do not

#### 2. Route within the domain

- map signals/questions/problems to the right framework
- identify when multiple frameworks should be chained
- identify when to hand off to another domain

#### 3. Define execution policy

- gather minimum required inputs
- choose one framework or a sequence
- apply framework-specific procedure
- produce structured output

#### 4. Reference framework files

- explicitly list framework files
- map triggers to file names
- instruct the model to consult the selected framework file before reasoning

## Proposed Behavior by Domain

### Thinking Router

The router should no longer stop at domain classification.

It should produce:

- true goal
- primary domain
- optional secondary domain
- candidate framework(s)
- why those frameworks fit
- recommended next prompt / handoff

### Systems Thinking

Route like this:

- recurring event with hidden causes -> Iceberg Model
- many entities with cause/effect relationships -> Connection Circles
- entity/idea dependency mapping without explicit feedback emphasis -> Concept Map
- self-correcting or stabilizing behavior -> Balancing Feedback Loop
- compounding, runaway, viral, or spiral dynamics -> Reinforcing Feedback Loop

### Decision Making

Route like this:

- first classify decision type -> Hard Choice Model
- compare explicit options with criteria -> Decision Matrix
- quick prioritization by value vs effort -> Impact-Effort Matrix
- urgency vs importance -> Eisenhower Matrix
- long-term consequences -> Second-order Thinking
- assumption-checking -> Ladder of Inference
- different lenses/perspectives -> Six Thinking Hats
- fast iterative action in dynamic context -> OODA Loop
- response style depends on situational complexity -> Cynefin Framework
- speed/quality tradeoff under uncertainty -> Confidence Determines Speed vs. Quality

### Problem Solving

Route like this:

- root causes with category structure -> Ishikawa Diagram
- decompose big problem -> Issue Trees
- redefine the problem at higher/lower abstraction -> Abstraction Laddering
- rebuild from fundamentals -> First Principles
- avoid failure modes -> Inversion
- generate solution space systematically -> Zwicky Box
- resolve conflicting constraints -> Conflict Resolution Diagram
- run full end-to-end creative problem-solving -> Productive Thinking Model

### Communication

Route like this:

- interpersonal feedback on observable behavior -> Situation-Behavior-Impact
- concise recommendation, update, memo, executive synthesis -> Minto Pyramid

## Bottom Line

The current repo does not have an inventory problem. It has an operationalization problem.

The right redesign is not "add more frameworks." It is "turn every framework into a concrete reasoning protocol, and turn every domain skill into a proper framework router."
