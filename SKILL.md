---
name: rumsfeld-matrix
description: Map what is known and unknown before answering. Use when a question, decision, or plan carries real uncertainty, when the user asks "what am I missing", about blind spots or risks, or how confident you are — or before committing to a high-stakes recommendation.
---

# Rumsfeld Matrix

Chart the epistemic terrain into four quadrants, then run the pump: each step converts darker quadrants into lighter ones, until whatever stays dark is at least labeled in the answer.

|                        | you know it                       | you don't know it              |
| ---------------------- | --------------------------------- | ------------------------------ |
| **aware of it**        | known knowns — verified facts     | known unknowns — named gaps    |
| **unaware of it**      | unknown knowns — tacit assumptions | unknown unknowns — blind spots |

## Steps

1. **Frame.** State in one sentence the claim, decision, or plan under evaluation. Done when a reader could disagree with the sentence — a frame too vague to disagree with is not a frame.

2. **Known knowns.** List the facts the answer will load-bear on. Tag each `verified:<source>` (checked in this conversation — file, doc, search, test run) or `assumed`. Done when every fact carries a tag, and every `assumed` item has moved to step 3 as a gap — tagging it is what promotes it from tacit to named.

3. **Known unknowns.** List the named gaps. Assign each exactly one move: `lookup` (search, read, or run something), `ask` (only the user can answer), or `flag` (accept it, but it must appear in the final calibration note). Done when no gap is move-less.

4. **Unknown knowns.** Hunt the premises being treated as true without ever being stated. Two hunts:
   - For each known known, ask "what breaks if this is false?" — anything that breaks silently was resting on an unstated premise; state it and tag it like step 2.
   - What does the user know that they haven't said — constraints, prior attempts, context, taste? Each becomes an `ask` move in step 3.

   Done when every load-bearing premise exists on the page rather than only in the reasoning.

5. **Unknown unknowns.** These cannot be listed, only hunted. Run at least two probes:
   - **Premortem** — assume the answer turned out wrong or the plan failed; write the most likely cause.
   - **Expert lens** — what would a domain specialist check first that hasn't come up yet?
   - **Inversion** — argue the opposite conclusion for one paragraph; note what evidence it would need.
   - **Base rate** — how often do things of this class fail, regardless of this instance's details?

   Anything a probe surfaces is promoted to step 3 as a fresh known unknown and gets a move. Done when at least two probes ran and every surfaced item is promoted.

6. **Pump, then answer.** Execute every `lookup` move now; batch the `ask` moves into questions for the user. Then give the answer, ending with a three-line calibration note:
   - **Solid** — the verified knowns the answer rests on.
   - **Open** — the flagged unknowns and pending asks.
   - **Dark** — what the probes could not light up, named as a region ("long-term interactions untested"), not hand-waved.

## Output shape

Show the work compactly: a short quadrant rundown (a few bullets per quadrant, tags visible) before the answer, the calibration note after it. The matrix is the receipt, not the deliverable — the deliverable is an answer whose confidence is earned.
