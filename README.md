# known-unknowns

An agent skill that turns "I want to talk this through with an AI" into a guided discussion, using the Rumsfeld Matrix as the map:

|                   | you know it                        | you don't know it                            |
| ----------------- | ---------------------------------- | -------------------------------------------- |
| **aware of it**   | known knowns — stated and confirmed | known unknowns — named gaps                  |
| **unaware of it** | unknown knowns — felt but unworded | unknown unknowns — options you'd never ask about |

## Why

Two failure modes wreck cross-domain conversations with an AI:

1. **You have the feeling but not the words.** An engineer discussing UI animation knows exactly which motion they like — and cannot describe it. Asking them "what effect do you want?" is useless: they can't *recall* the term. But they can *recognize* it instantly when shown "staggered entrance? spring easing?".
2. **You don't know the option exists.** You never ask about what you've never heard of, so your requests stay conservative forever.

This skill gives the agent one move for each: **lend words** (named candidates + concrete examples, answered by pointing) and **give a tour** ("you didn't ask, but X is possible").

## How a session runs

1. **Draft-first opening** — the agent sketches an initial map from your topic and its own domain knowledge, and asks you to correct it. Correcting a wrong map is faster than filling a blank one.
2. **One cell per turn** — each turn redraws the full compact map (`✓` confirmed · `?` gap · `!` assumption · `~` dark), then asks exactly one question, always with named candidates. Open-ended blanks are off the menu.
3. **Closing brief** — when the dark cells are dug out (or you call it), you get a distilled brief: the vocabulary you recognized and the choices you settled, phrased to paste verbatim into a future prompt to any agent.

Typical uses: articulating taste for generation tasks, discovering what a tool or AI can actually do, surveying an unfamiliar ecosystem before choosing, and weighing open decisions whose real trade-offs you haven't put into words.

## Install

Clone (or symlink) into your agent's skills directory — for Claude Code:

```sh
git clone https://github.com/Wang-Cankun/known-unknowns.git ~/.claude/skills/known-unknowns
```

The skill is model-invoked: it fires when you signal discussion intent ("let's discuss…", "help me think through…"), or you can invoke it by name.

## License

MIT
