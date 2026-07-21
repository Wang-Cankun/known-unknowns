# known-unknowns

An agent skill that turns "I want to talk this through with an AI" into a guided discussion, using the Rumsfeld Matrix as the map:

|                   | you know it                        | you don't know it                            |
| ----------------- | ---------------------------------- | -------------------------------------------- |
| **aware of it**   | known knowns — stated and confirmed | known unknowns — named gaps                  |
| **unaware of it** | unknown knowns — felt but unworded | unknown unknowns — options you'd never ask about |

## Why

Two especially hard failure modes wreck cross-domain conversations with an AI:

1. **You have the feeling but not the words.** An engineer discussing UI animation knows exactly which motion they like — and cannot describe it. Asking them "what effect do you want?" is useless: they can't *recall* the term. But they can *recognize* it instantly when shown "staggered entrance? spring easing?".
2. **You don't know the option exists.** You never ask about what you've never heard of, so your requests stay conservative forever.

The full matrix gives the agent four moves: **confirm and compress** settled knowledge, **investigate** named gaps, **lend words** for felt-but-unworded knowledge, and **give a tour** of unseen possibilities. Each turn enables one **aspect-seeing** by making something more nameable, visible, or testable; the move is not limited to a fixed scenario list.

## How a session runs

1. **Draft-first opening** — the agent sketches an initial map from your topic and its own domain knowledge, and asks you to correct it. Correcting a wrong map is faster than filling a blank one.
2. **One cell per turn, substance first** — each turn redraws the full compact map (`✓` settled · `?` named question · `!` recognition candidate · `~` unexplored frontier), then contributes real material for one cell before asking exactly one question. Recognition questions carry 2–4 named candidates; other questions use the form that best advances the selected cell.
3. **Closing brief** — when no active mapped entry warrants another turn (or you call it), the agent audits unresolved marks and checks one plausible missing aspect that could change the conclusion. You then get a distilled brief containing recognized vocabulary, settled choices, deferred gaps, and residual darkness, phrased to paste verbatim into a future prompt.

Typical uses include articulating taste, discovering what a tool or AI can do, surveying an unfamiliar ecosystem, and weighing open decisions. These are examples, not branches; any topic that benefits from making an aspect nameable, visible, or testable can use the same loop.

## Install

Clone (or symlink) into your agent's skills directory — for Claude Code:

```sh
git clone https://github.com/Wang-Cankun/known-unknowns.git ~/.claude/skills/known-unknowns
```

The skill is model-invoked: it fires when you signal discussion intent ("let's discuss…", "help me think through…"), or you can invoke it by name.

## License

MIT
