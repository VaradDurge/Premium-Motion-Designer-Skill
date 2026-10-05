# Motion craft

Read this before writing animation code. Timing below assumes **30 fps**. Multiply frame counts by 2 at 60 fps. Design in frames, then convert.

Motion is authored. A move has a role (reveal, respond, connect, emphasize, exit), a curve, and a moment where it stops.

## Hierarchy of a frame

At any instant, one thing is primary. Everything else is quieter, later, or still.

- Do not start type, shape, camera, and background in the same 4 frames.
- Secondary motion has less amplitude than the primary move.
- Decoration that moves independently of the idea gets cut.

## Curves

Use one easing family for the film, with these roles. Do not invent a new curve per object.

| Role | Frames | Curve | What it should feel like |
|---|---|---|---|
| Press, toggle, tick | 6–10 | `cubic-bezier(0.2, 0.8, 0.2, 1)` | Immediate, slightly soft |
| Element arrives | 12–18 | `cubic-bezier(0.16, 1, 0.3, 1)` | Fast commitment, long settle |
| Element leaves | 8–14 | `cubic-bezier(0.7, 0, 0.84, 0)` | Hesitates a hair, then gets out |
| Move across the frame | 18–36 | `cubic-bezier(0.65, 0, 0.35, 1)` | Departs and arrives |
| Scene morph on one object | 20–40 | same ease-in-out | The silhouette continues |
| Hold on a word or a number already understood | 12–30 | none | A beat, not a sentence |
| Hold on a sentence or a claim | 45–90 | none | Long enough to read aloud once |

Linear is for a mechanical wipe, a progress fill, a scrub, or a constant-speed tracking move. Linear on a UI element floating into center looks unfinished.

### Springs

Use a spring when the object is physical: a knob, a card docking, a toggle, a sticker.

- One overshoot, about 4–8% of the travel. Damping ratio about 0.75, so it settles inside the move and does not ring.
- It is fully settled before the next idea starts.
- If it is still oscillating at the cut, increase damping or shorten the idea. Do not cut mid-bounce unless the bounce is the joke.

### Anticipation, stretch, and follow-through

- Before a large move, 2–4 frames of counter-motion: a 4px wind-up, a scale to 0.98, a tracking loosen.
- On a fast move, stretch along the direction of travel. On impact, squash. Keep the area looking constant. A button label does not squash. A ball, a knob, a sticker, or a word used as an object can.
- The hit itself can be a snap: most of the travel happens in a few frames, then a short settle. Mechanical UI (a toggle, a check, a lock) wants snap. Organic arrivals want the long ease-out.
- Paths of long moves arc. Offset the midpoint by 8–15% of the straight-line distance, perpendicular to the path. A short UI move stays straight.
- The primary object lands first. The label follows 3–5 frames later. A caption, if it deserves to exist, follows 6–8 frames later.
- Connected parts (a shadow, an underline, a cursor ring) arrive late and smaller.
- If the film shows a curve, the motion has to match that curve. A graph that says "ease" over a linear move is a lie.

### Stagger

- 2–4 frames between siblings.
- Stagger to show rank, not to wave through a long list.
- If more than five items need to enter, the layout is wrong. Show the group as one object, then isolate the one that matters.

## What moves, and what must not

Prefer transforms: position, scale, rotation, crop. They stay sharp.

Opacity may ride along: 0→1 during the first 20% of an arrival, 1→0 during the last 30% of an exit. A fade with no transform is the default failure.

Do not use blur as a transition. Motion blur is a shutter on something already moving fast: short, directional, gone when the object rests. A whole frame dissolving through blur means the cut was avoided.

Do not animate shadow, glow, and blur together to fake depth. A real change of scale or a second plane does that job.

Snap type to whole pixels when it rests. Subpixel type that never settles looks nervous.

## Cuts

- **Hard cut** when the idea changes. Color-field cuts (paper → ink → one saturated field) are a complete transition.
- **Morph or match cut** when an object continues. It holds its screen position into the next shot. A window, a word, or a cursor can be that object.
- **Dissolve** almost never. If you want softness, hold on a quiet frame instead.

The opening can breathe. The first idea should be readable inside two seconds, and the first hard cut can wait until that idea has landed. Showreels may cut faster, but each frame is still a finished poster.

Match continuity objects within a few pixels across a cut. A "same object" that jumps is a slideshow.

## Type

Type is layout, not subtitles.

- Few words. A claim is a sentence. A beat is often 1–4 words.
- One accent word, the rest in ink or paper.
- Mask reveal: the type is already in place; a window opens over it.
- Crop: let the frame edge cut through a word so it feels like an object passing through, then settle to the full word.
- Tracking: start slightly open, settle to the real tracking. Do not animate tracking for its entire life.
- Shared baseline across a sequence so the eye does not re-hunt.
- Per-letter animation only when the letters are the subject. Otherwise it is noise.
- Do not put a paragraph on a moving frame.

End lockups are designed: a name, a one-line meaning, a stable position. They do not fade up from nothing in the center because the timeline ran out.

## Numbers

- One number on screen, large enough to read in a second.
- If a value changes, it counts or it snaps. It does not sit inside a chart nobody can read.
- Before and after use the same position and the same type style, so the change is the only event.
- Invent no metric. If you do not have a real figure, show the mechanism instead.

## Cursor and interaction

When a hand or cursor causes the product to respond:

- Move on an ease, on a simple path. A long move can take a slight arc. A short move is straight.
- Arrive, hold 4–8 frames, then click.
- The click is a small scale pulse on the target (to about 0.96 and back), plus an optional tick in sound.
- After the click, the cursor gets out of the focal point or stays dead-still. It does not orbit the UI.
- The result of the click is the next shot's idea.

## Camera

A camera exists to reveal information or to land on proof.

- A push-in is an 8–15% scale change over 24–48 frames, ease-in-out, and it arrives on the proof. A push that never lands is banned.
- Two or three depth planes are enough for parallax. More planes look like a template.
- Wide frames orient. Close frames prove. Do not stay wide while type becomes unreadable.
- Do not orbit 3D objects to generate energy.

## Color as editing

- For a launch or a demo, the ground is the product's canvas. Stay on it.
- For a showreel, the ground may be paper, ink, or a flat field, and a full-frame color change can be the cut.
- One accent does the semantic work: the active control, the proof, the one word. Use more only when they are the real brand.
- A giant blurred gradient behind every beat is the failure mode, even if the brand has a gradient on the website. A gradient is allowed when it is the object (a data field, a material, a light on a product), not the wallpaper.
- Semantic red and green only when the product means danger or success.

## Sound

- Music or tone carries the film. Voice is optional. If both voice and type exist, they must not say the same line at the same time.
- Sound effects on the events that matter: click, lock, number landing, cut into the proof.
- No sound on every keyframe.
- A short silence before the claim makes the claim land.
- Generate or use audio you have rights to. Do not drop in a track you cannot use.

## Layout systems

Pick one and repeat it:

- **Product crop:** the real layout, large, with nav and sidebars gone. This is the launch grid.
- **Poster:** type in one zone, a single object in the other, a small caption, the same margins every time. Showreels only.
- **Stage:** a persistent frame (a window, a device, a crop) so hard cuts feel like one reel.
- **Chapter:** a quiet corner label (section name) used on every beat or not at all. Do not invent new chrome per shot.
- **Registration marks** (crop marks, ticks) only as a motif that appears enough times to be a system.

Changing the grid every beat is the catalog look.

## Build rules for code timelines

- Drive animation from the frame number. CSS transitions will not render deterministically.
- Clamp interpolations. An overshoot is deliberate, not an accident of an unclamped spring at the edit point.
- Keep durations and curves in one module. Scenes import them.
- Settle state first: render the hero frame at its rest pose, then add the in and out.
- Check the rest pose at full resolution. Then check it in motion.
- At the last frame of a scene, every animated value is at rest unless a continuity object is mid-flight on purpose.

## A move, decided

Example, not a shot to copy:

A cursor eases onto a real control in 18 frames, holds 6 frames, and clicks. The control changes to the product's next real state over the following 8 frames. That new state holds for 48 frames. Nothing else moves. Then a hard cut. The cursor does not wander. Opacity is not the event. The state change is.

That is a designed second. A number fading up in the center of a gradient is not.
