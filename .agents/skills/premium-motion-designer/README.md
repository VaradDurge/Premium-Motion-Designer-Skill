# Premium Motion Designer

A skill for directing and building premium product films: launch videos, SaaS demos, explainers, and showreels. It is a decision system for what to take from a product, what to leave out, and how each second should move.

The default failure it is written to beat: centered type, a soft gradient, everything fading in.

Built from 15 references: 4 posts and 11 films from the Revid Opus motion wall. The list is in `references/reference-pack.md`. Grammar only. Nothing in those films is a template.

## Install

**Claude Code**

```bash
npx skills add VaradDurge/Premium-Motion-Designer-Skill
```

Or copy this repo's skill files into `~/.claude/skills/premium-motion-designer/` (global) or `.claude/skills/premium-motion-designer/` (project).

**Cursor and other agents**

Copy the same files into the agent's skills directory (for Cursor, `.agents/skills/premium-motion-designer/` or your personal skills folder).

Then:

> Use the premium motion designer skill. Make a 25-second launch film for this product, 16:9, for the site hero. Inspect the source and use the real UI. The job, the channel, and the length are set, so decide the rest and write the assumptions. It has to work muted.

## What the model has to do

1. If the prompt names the job, the channel, and the length, proceed and write assumptions for audience, sound, and claims. Ask only when two jobs are both plausible, or when a claim would be invented. X, Product Hunt, and a site hero must work muted.
2. Write a creative note: intent, thesis, what is real, beats, exclusions, visual system, what it will borrow, what it will not copy.
3. Design each beat as a still that works with the motion turned off.
4. Animate only what has a role: reveal, respond, connect, emphasize, exit.
5. Render, watch the frames second by second, and fix only what fails the thesis, the truth, or the generic-AI test.

## Files

- `SKILL.md` — the thinking order and the quality bar
- `references/motion-craft.md` — timing, curves, type, cursor, cuts
- `references/reference-grammar.md` — what strong films have in common, and what not to copy
- `references/creative-system.md` — palette, type, camera, finish
- `references/saas-product-video.md` — how a product film is structured
- `references/research-protocol.md` — how to read a reference
- `references/quality-gate.md` — the review after the render
- `references/reference-pack.md` — films the grammar was learned from
- `examples/argus-brief.md` — the creative note, applied
- `examples/saas-launch.md` — a 30-second launch budget for ordinary software
