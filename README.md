# rumsfeld-matrix

A Claude skill that maps the epistemic terrain of a question before answering it, using the Rumsfeld Matrix:

|                   | you know it                        | you don't know it              |
| ----------------- | ---------------------------------- | ------------------------------ |
| **aware of it**   | known knowns — verified facts      | known unknowns — named gaps    |
| **unaware of it** | unknown knowns — tacit assumptions | unknown unknowns — blind spots |

Instead of answering with uniform confidence, the agent runs a six-step "pump" that moves items from the dark quadrants toward the light ones:

1. **Frame** the claim in one falsifiable sentence.
2. **Known knowns** — every load-bearing fact tagged `verified:<source>` or `assumed`.
3. **Known unknowns** — every gap assigned a move: `lookup`, `ask`, or `flag`.
4. **Unknown knowns** — tacit assumptions surfaced, including what *you* know but haven't told it.
5. **Unknown unknowns** — hunted with probes: premortem, expert lens, inversion, base rate.
6. **Pump, then answer** — lookups executed, asks batched, and the answer ends with a calibration note: **Solid / Open / Dark**.

## When it fires

The skill is model-invoked: Claude reaches for it on its own when a question, decision, or plan carries real uncertainty — or when you ask "what am I missing", about blind spots, risks, or its confidence. You can also invoke it by name.

## Install

Clone (or symlink) into your Claude Code skills directory:

```sh
git clone https://github.com/Wang-Cankun/rumsfeld-matrix.git ~/.claude/skills/rumsfeld-matrix
```

## License

MIT
