# known-unknowns [![skills.sh](https://skills.sh/b/wang-cankun/known-unknowns)](https://skills.sh/wang-cankun/known-unknowns/known-unknowns)

[English](./README.md) | [简体中文](./README_CN.md)

An agent skill for the moment when you know a discussion matters but do not yet know what to ask. Ordinary AI conversations fail in two places:

- **You know more than you can say.** You can recognize the right feel, distinction, or tradeoff, but cannot recall the words for it.
- **You cannot ask about an option you have never encountered.** The useful part of the possibility space never enters the conversation.

So this skill gives the agent a different job: contribute the vocabulary, options, and probes that let you see one more aspect of the problem before it asks the next question.

## Install

```bash
npx skills@latest add Wang-Cankun/known-unknowns   # add -g to install across projects
```

## The map

|                          | You know it                          | You do not know it                                  |
| ------------------------ | ------------------------------------ | --------------------------------------------------- |
| **You are aware of it**  | Known knowns: stated and confirmed   | Known unknowns: named gaps                          |
| **You are not aware of it** | Unknown knowns: felt but unworded | Unknown unknowns: options you would never ask about |

Each cell suggests a move: **confirm and compress** what is settled, **investigate** a named gap, **lend words** you can recognize rather than recall, and **give a tour** of options you would never think to ask about.

## How a session runs

- **Draft-first opening** — the agent sketches the full map from your topic and its own domain knowledge. The first map is allowed to be wrong: correcting a concrete proposal beats answering a blank interview.
- **One aspect per turn** — every turn redraws the compact map, contributes something substantive to one cell, then asks exactly one question.
- **Closing brief** — after a frame-break check (is there an assumption outside the map that could change the conclusion?), you leave with the vocabulary you recognized, the choices you settled, and the remaining darkness — ready to paste into a future prompt.

## Try it

```text
$known-unknowns I know which interfaces feel calm, but I cannot explain why. Help me find the vocabulary.
```

```text
$known-unknowns Tour the approaches I may not know exist for adding memory to an AI assistant.
```

```text
$known-unknowns Help me decide whether to accept this role. Probe the assumptions I may be missing.
```

The skill conducts the discussion in the language you choose.

## License

MIT
