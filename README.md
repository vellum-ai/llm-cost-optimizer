# LLM Cost Optimizer

A [Vellum](https://vellum.ai) skill that analyzes and reduces LLM spend by mapping call-site overrides to managed model profiles.

## What it does

Vellum assistants run dozens of different LLM calls per conversation — main agent, memory ops, summarization, UI copy, and more. By default, many of these run on your highest-capability (most expensive) model. This skill walks you through pinning each call site to the right model tier so you're not using a sledgehammer to crack a nut.

Typical result: **60-65% reduction in weekly LLM spend** with no meaningful quality loss.

## How to use it

Load the skill in your Vellum assistant:

```
assistant skills load llm-cost-optimizer
```

Then follow the steps in [`SKILL.md`](./SKILL.md):

1. Pull your weekly spend breakdown by call site
2. Read your current overrides
3. Apply the recommended profile assignment
4. Fix common config gotchas
5. Apply the complete turnkey blob (covers all ~40 known call sites)
6. Escalate to Opus on-demand with `/model` when you need it
7. Tune individual call sites if quality degrades

## Model tiers

| Profile | Model | Use for |
|---|---|---|
| `balanced` | Claude Sonnet | Main agent, reasoning, memory consolidation |
| `cost-optimized` | Claude Haiku | Memory ops, summarization, UI copy, background tasks |
| `quality-optimized` | Claude Opus | On-demand only — never pinned |

## Requirements

- Vellum assistant (cloud or local)
- `assistant` CLI

## License

MIT
