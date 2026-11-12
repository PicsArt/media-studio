---
name: film-cutting
description: Cut a film's accepted takes into one scene - the montage bootstrap with hard cuts, separate dialogue and ambience, and diagnosing a bad join before choosing the smallest repair. Use when a film's takes are assembled into a cut, a cut is changed or fixed from notes ("fix my film"), or a join between two shots is repaired.
user-invocable: false
---

# Film edit

The cut is built from the selects, never from the raw pile, and it stays editable: clips, not a
flattened strip. Read `references/join-repair.md` before you change a join between two takes.

Every clip goes into the cut once, in story order, with hard cuts between clips. The user's own trims and splits are
theirs: made in the editor, each is recorded on its clip and kept as it is, never recomputed or reset. Never replace a
clip with a trimmed export: that welds the handles shut.

## Assembly

Build the cut with `picsart_scene_apply_template`: `uri: "scene://montage"`,
`mode: "bootstrap"`, and `parameters`:

- `clips`: one per generation, in story order. Each is a full clip: `duration` (the file's probed
  duration) and `content: { kind: "media", assetId: "<the take's url>", assetType: "video",
  trim: { in: 0, out: <that duration> }, fit: "cover" }`. Without `assetType: "video"` the file is read as a still and the trim is ignored.
  This URL-in-`assetId` form is the template's input, not a scene document's;
- `transition: ""`, for hard cuts. The template's default is a crossfade;
- `width` and `height`: the film's frame.

Probe every distinct file with `picsart_media_probe` for its real size and duration first.
Then change the scene with `picsart_scene_patch`, as scene-building-basics says. Never set the
composition's duration: it comes from the track. The result is reviewed as the scene object.

**Sound.** Dialogue and ambience or music on **separate audio layers**, so a J or L cut is possible
and a bed can carry across picture cuts. A bed does not repair a changed or invented line.

**Seams.** A hard cut, within a scene and between scenes. A transition only when the user asks for
one, never to hide a discontinuity, and chosen as scene-building-basics says.


## Joins and moves a viewer reads as glitches

quality-review's cut check finds these in the scene; build the cut so it finds none.

- **One take per shot.** Never cut between two takes of the same shot, jump inside one shot, or
  join two shots of the same size and angle, and never hide a cut under a quick zoom, a whip or a
  transition. A cut to a different shot of the same place is coverage, as Seams says.
- **No short dissolves between takes.** A dissolve of 0.3 s or less shows both takes at once. Cut hard.
- **Every code move eases.** A zoom, a pan or a camera move starts from rest and stops at rest
  eased (`ease_in_out`), never `linear` from a standstill or on a `step` key, unless it starts and
  ends on a cut.
- **No code zoom over a still picture.** A zoom over a still image, or over a video held past the
  end of its source, reads as idle from 0.8 s: cut to a moving moment instead.
- **A screen holds still under 1.8 s.** Past that, the viewer thinks the video paused.
- **Allowed spans are locked.** Each screen clip placed in the cut is an allowed span: write
  `allowed-spans.json` as `[{ start, end, file, reason }]`, in seconds on the cut's timeline, as you
  place the clips, and rewrite it on every re-cut. Never cut, re-time or zoom inside a span.
- **A rule is never passed by adding a move.** A cut, push-in or zoom added to get past a check
  makes the picture busier and the story harder to follow;
  cut less,
  or take another moment.

## The review

The whole cut is reviewed once through; never one review per clip.


- The user's own edits are taken as picsart-video-rules says for an editor reply of `needs_changes`.
- Each comment is located on its clip and its source seconds, diagnosed, and applied; compatible
  notes are combined, and what the user asked to keep is kept. A trim or split is applied only when
  the user asks for it.
- Once the user calls the cut final, no picture changes unless they ask.

## Cleanup

When a
shot cannot be made clean, offer the honest fallbacks in the review: a cut around it (a cutaway, a
tighter trim) the user approves, or their acceptance of the flaw, in words. Never cut around a
glitch silently.

## Traps

- Exporting to answer "what if", which picsart-video-rules's Preview and export does not allow: change the
  scene and review it.
- A cut built from raw takes instead of selects.
- A flattened strip that cannot be recut.
- Deleting or overwriting an old take: every version stays, and the record keeps it.
