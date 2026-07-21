# known-unknowns [![skills.sh](https://skills.sh/b/wang-cankun/known-unknowns)](https://skills.sh/wang-cankun/known-unknowns)

[English](./README.md) | [简体中文](./README_CN.md)

A small, composable agent skill for the moment when you know a discussion matters but do not yet know what to ask.

It uses the Rumsfeld matrix to make tacit knowledge sayable, unseen possibilities visible, and uncertain judgments testable. The goal is not to label everything. The goal is to move the conversation.

## Quickstart (30-second setup)

1. Run the [skills CLI](https://github.com/vercel-labs/skills):

   ```bash
   npx skills@latest add Wang-Cankun/known-unknowns
   ```

2. Select `known-unknowns`, then choose the coding agents where you want it installed.

3. Start a discussion:

   ```text
   $known-unknowns Help me think through whether this product idea is worth building.
   ```

The installer uses project scope by default. Add `-g` if you want the skill available across projects:

```bash
npx skills@latest add Wang-Cankun/known-unknowns -g
```

## What problem does it solve?

Ordinary AI conversations often fail in two places:

- **You know more than you can say.** You can recognize the right feel, distinction, or tradeoff, but cannot recall the words for it.
- **You cannot ask about an option you have never encountered.** The useful part of the possibility space remains outside the conversation.

`known-unknowns` gives the agent a different job: contribute the vocabulary, options, counterexamples, and probes that let you see one more aspect of the problem before it asks the next question.

## The map

| | You know it | You do not know it |
| --- | --- | --- |
| **You are aware of it** | Known knowns: stated and confirmed | Known unknowns: named gaps |
| **You are not aware of it** | Unknown knowns: felt but unworded | Unknown unknowns: options you would never ask about |

Each cell suggests a move:

- **Confirm and compress** what is already settled.
- **Investigate** a named gap with evidence, reasoning, or an experiment.
- **Lend words** by offering concrete candidates the user can recognize, reject, or refine.
- **Give a tour** of an unseen option space, including fit, cost, and tradeoffs.

The compact marks show where each entry is in its lifecycle: `✓` settled, `?` named question, `!` recognition candidate, and `~` unexplored frontier.

## What a session looks like

### 1. Start with a draft map

The agent sketches the full map from your topic and marks its inferences as `!`. The first map is allowed to be wrong: correcting a concrete proposal is usually easier than answering a blank interview.

### 2. Advance one aspect per turn

Every turn redraws the compact map, contributes something substantive to one cell, and asks exactly one question. A recognition question carries a few named candidates; an uncertainty question carries a way to test it.

### 3. Leave with a reusable brief

At the end, the agent audits unresolved entries and performs one frame-break check: is there a plausible assumption or option outside the current map that could change the conclusion? If not, it returns a brief containing the vocabulary you recognized, choices you settled, gaps you deferred, and the remaining darkness.

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

## Manage the installation

List installed skills:

```bash
npx skills@latest list
```

Update this skill:

```bash
npx skills@latest update known-unknowns
```

Remove it:

```bash
npx skills@latest remove known-unknowns
```

To inspect what the repository exposes without installing anything:

```bash
npx skills@latest add Wang-Cankun/known-unknowns --list
```

## Repository layout

```text
.
├── README.md
├── README_CN.md
└── skills/
    └── known-unknowns/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

The repository root is for people; [`skills/known-unknowns`](./skills/known-unknowns) is the installable skill package.

## License

MIT
