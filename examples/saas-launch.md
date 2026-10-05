# Example frame budget: a collaboration tool

Not a shot list. Not Argus. Use it to see what a launch budget looks like when the product is ordinary software.

The mechanism: a scattered thread becomes one owned task. The real UI is a message, then a task row. No second palette.

```
JOB: Launch
FORMAT: 30s / 16:9 / 30fps / music, mute-safe
UI SHARE: 720/900
BEATS:
  0–90f    role=respond  The message is on screen, large. Cursor arrives.
  90–180f  role=respond  Click. The message becomes a task in the same place.
  180–420f role=reveal   The task sits in the list. Hold. This is the mechanism.
  420–600f role=emphasize One real count changes, same position. Hold.
  600–750f role=reveal   One sentence, 60 frames of hold, product still visible behind or beside it.
  750–900f role=exit     Name and one line. Smaller than the sentence.
```

Readable UI is the subject from frame 0 through 600. The sentence does not replace the product. The logo does not open the film.
