# Quality gate

Watch the rendered frames. Do not grade the source.

Export a contact sheet, or a still at every second. Every note names a frame: "frame 420: the claim is still arriving." A review that only reads the source fails.

At 1920×1080, UI and labels are at least 24px and claims are much larger. Keep type and UI inside a 64px inset. At 30fps, a sentence holds 45–90 frames. 12–30 frames is only a word or a number already understood.

## Story

- Can a viewer say the product's value after one watch, in one sentence?
- Is there a hero moment you could point to on the timeline?
- Does the first two seconds contain a readable idea?
- Does the last frame belong to the product, not the tool that made the film?

## Truth

- Are the UI states real or faithful?
- Are the numbers real? If a number is abstract, is that obvious?
- Did any shot invent a feature?

## Design

- Could you name the ground, the accent, the type, and the motif?
- Does every beat use that system?
- Does the settled frame of each beat work with the motion turned off?
- Is there a stretch that is just centered type on a soft gradient?

## Motion

- Does each moving object have one role: reveal, respond, connect, emphasize, or exit?
- Are the curves doing different jobs, or is everything the same fade?
- Is there a hold long enough to read the claim?
- Does something survive at least one cut?
- Is anything still bouncing, blurred, or mid-fade at a cut where it should have settled?

## Product

For a launch or a demo, all three are required:

- Readable product UI is on screen for at least half the runtime. A type reel with a short UI insert fails.
- The product appears before the logo.
- One state change is caused by a cursor or by data, and the new state is held long enough to read.

Also:

- Is the mechanism visible, not only named?
- Would a cropped component have been clearer than the full screen?
- If it plays on X, a site hero, or Product Hunt, does it still communicate with the sound off?

## Technical

- No jitter, clipping, collisions, or type on fractional pixels at rest
- Export size, frame rate, and audio match the brief
- Safe areas respected for the target format
- Vertical or square versions are recomposed, not cropped

## The generic-AI test

Find the five seconds a motion designer would identify as generated: centered fade, blob background, tiny dashboard, glass card parade, wandering cursor, fake chart, logo fade, every effect at once.

Fix those seconds first.

## Note scoring

After the watch pass, mark each note:

- **Fix now** — thesis, truth, legibility, continuity, or the generic-AI test
- **Later** — polish that can wait for a second render
- **Skip** — taste that does not serve the thesis

Only "fix now" goes into the next render. Then watch again.
