# Thinking Router

Give your AI agent a better first move.

`thinking-router` is a `skills.sh`-ready skill collection that helps an agent identify what kind of thinking a request actually needs before it answers. Instead of treating every prompt the same way, it routes the task to the right reasoning mode: communication, decision-making, problem-solving, or systems-thinking.

If your agent tends to answer too fast, use the wrong framework, or mix diagnosis with recommendations, this skill set fixes that.

The idea for this repository is inspired by [Untools](https://untools.co/), a curated collection of thinking tools and frameworks for problem solving, decision making, systems thinking, and communication.

## Why install this

- Route vague or messy prompts to the right thinking style
- Improve answer quality before downstream execution starts
- Separate analysis, prioritization, and communication cleanly
- Get more structured, actionable outputs from the same agent
- Add a lightweight reasoning layer with simple `SKILL.md` files

## Included skills

| Skill | What it does | Best for |
| --- | --- | --- |
| `thinking-router` | Classifies the request and routes it to the best specialized skill | Ambiguous prompts, mixed requests, framework selection |
| `communication` | Turns thinking into clear, top-down communication | Summaries, recommendations, stakeholder-facing messages |
| `decision-making` | Compares options and manages tradeoffs | Prioritization, option selection, uncertainty |
| `problem-solving` | Breaks down messy problems and finds solution paths | Root causes, ambiguity, conflicting constraints |
| `systems-thinking` | Explains patterns, structures, and feedback loops | Recurring issues, hidden dynamics, system behavior |

## Install

```bash
npx skills add jonatasleon/thinking-router
```

Repository: `git@github.com:jonatasleon/thinking-router.git`

## How it works

1. Start with `thinking-router`
2. Identify the user's true goal
3. Route to one primary reasoning category
4. Propose the most likely framework or short framework sequence
5. Apply the specialized skill and its framework protocol
6. Return a clearer, more useful answer

This gives your agent a reasoning layer before it commits to an output.

## Example prompts

Use `thinking-router` when the user is not just asking for an answer, but for the right way to approach the answer.

- "Help me figure out how to think about this stalled initiative."
- "I am not sure whether this is a decision problem or a system problem."
- "Compare these options and recommend one."
- "Why does this issue keep coming back after every fix?"
- "Rewrite this recommendation so it is easier to understand."

## What makes this different

Many skills help an agent do something. This project helps an agent decide how to think first.

That makes it especially useful when:

- the request is ambiguous
- the user mixes multiple goals in one prompt
- the agent tends to skip framing and jump to output
- you want more reliable, category-appropriate reasoning

## Inspiration

This repository takes direct inspiration from [Untools](https://untools.co/), especially its organization of practical thinking frameworks into four areas:

- communication
- decision making
- problem solving
- systems thinking

This project adapts that mental-model-oriented structure into agent skills, so an AI assistant can choose an appropriate reasoning workflow before producing an answer.

This repository is inspired by Untools, but it is not affiliated with or endorsed by Untools.

## Framework architecture

This repository now separates domain routing from framework execution.

- Each top-level skill explains when that domain is appropriate.
- Each domain skill contains routing logic that points to specific framework files.
- Each framework lives in its own file and is written as an operational reasoning protocol, not just a description.
- `thinking-router` can recommend a short framework sequence when one framework alone is not enough.

Every framework file follows the same core structure:

- framework name
- core mental model
- when to use
- when not to use
- key diagnostic questions
- step-by-step reasoning process
- example application

That makes the framework library more composable, easier to extend, and much more explicit for LLM reasoning.

## Project structure

```text
.
|-- communication/
|   |-- frameworks/
|   |   |-- minto-pyramid.md
|   |   `-- situation-behavior-impact.md
|   `-- SKILL.md
|-- decision-making/
|   |-- frameworks/
|   |   |-- confidence-determines-speed-vs-quality.md
|   |   |-- cynefin-framework.md
|   |   |-- decision-matrix.md
|   |   |-- eisenhower-matrix.md
|   |   |-- hard-choice-model.md
|   |   |-- impact-effort-matrix.md
|   |   |-- ladder-of-inference.md
|   |   |-- ooda-loop.md
|   |   |-- second-order-thinking.md
|   |   `-- six-thinking-hats.md
|   `-- SKILL.md
|-- problem-solving/
|   |-- frameworks/
|   |   |-- abstraction-laddering.md
|   |   |-- conflict-resolution-diagram.md
|   |   |-- first-principles.md
|   |   |-- inversion.md
|   |   |-- ishikawa-diagram.md
|   |   |-- issue-trees.md
|   |   |-- productive-thinking-model.md
|   |   `-- zwicky-box.md
|   `-- SKILL.md
|-- systems-thinking/
|   |-- frameworks/
|   |   |-- balancing-feedback-loop.md
|   |   |-- concept-map.md
|   |   |-- connection-circles.md
|   |   |-- iceberg-model.md
|   |   `-- reinforcing-feedback-loop.md
|   `-- SKILL.md
|-- thinking-router-analysis.md
`-- thinking-router/
    `-- SKILL.md
```

Each domain still has one `SKILL.md`, but the actual framework procedures now live in `frameworks/` so they can be referenced, extended, and composed more cleanly.

The analysis and redesign rationale is documented in `thinking-router-analysis.md`.

## Built for

- OpenCode-compatible agents
- `skills.sh` style packaging and installation
- lightweight skill bundles that are easy to inspect and extend

## Extending the collection

Want to add a new reasoning capability?

1. Create a new directory for the skill
2. Add a focused `SKILL.md`
3. Keep the scope narrow and operational
4. Update `thinking-router` if the skill should become a routing destination
5. Update this README with the new use case

## Contributing

Contributions are welcome, especially if they improve routing quality or add a clearly differentiated reasoning capability.

Strong contributions usually:

- improve classification clarity
- add practical, reusable frameworks
- keep instructions concise and actionable
- preserve the modular structure of the collection

For major changes, open an issue first so the routing model stays coherent.

## Status

This project is intentionally small, fast to understand, and easy to extend. It is a solid base for publishing a reasoning-focused skill bundle on `skills.sh`.

## License

This project is licensed under the `MIT` License. See `LICENSE`.
