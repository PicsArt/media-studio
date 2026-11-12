---
name: film-finishing
description: Finish a film after picture lock - the takes finished to full quality, colour matched and graded from the scene tools' looks, the soundtrack (the takes' own voices, an ambience or music bed), QC, masters, the archive and any AI disclosure. Use when a film's cut is final and it needs finishing, delivery files or its archive.
user-invocable: false
---

# Film finishing

Picture lock is behind you: nothing here changes the cut. The order is fixed and worth saying to the
user:
For a cut of the user's own footage, the order is **assemble the locked cut at the finish size →
grade → export once → masters → archive.** Read `references/delivery.md` before QC, masters or the archive.


## Colour: match, then grade

The first job is **matching** neighbouring shots
of each scene, and only then the look. The film's tone already lives in its places' pictures, so
the grade refines it and never invents a new one.

- Read the real looks from `picsart_scene_capabilities` with `sections: ["looksCompact"]`
  (never a remembered look name, and never the full `looks` section, which can overflow), and
  return three or four that suit the film's colour.
- The user picks the look: apply each of them to one representative scene and show the versions
  in `picsart_scene_picker`, each card labelled in their terms ("warm dusk", "cool and muted"),
  never a `look:<id>`. Never choose for them or describe the looks in text; grade the film with
  the one they keep and say which (picsart-video-rules, "A choice made by eye").
- Apply with `picsart_scene_apply_preset`, one call per clip layer: it takes `scene` (the assembled
  scene), `layerId` (that clip's layer) and `preset` (`look:<id>`), and changes only that layer. Do the layers of
  one scene first, then the rest of the film. Setting a look is free.
- Check a chosen look on a few frames from two or three scenes with `picsart_scene_contact_sheet`
  before applying it to the film.
- If the user has a colourist, export ungraded and hand off (`references/delivery.md`).

## Sound


- **The takes keep their voices.** A line is never re-recorded here. Where a speaker's timbre drifts
  enough to distract, prefer a retake of the worse clip over pretending a mix exists.
- **Ambience is the glue.**
  A continuous bed under
  each scene hides the level and tone steps. Match levels shot to shot.
- **Music the user brings** comes in with `picsart_drive_upload_ask` and is laid under the takes'
  dialogue and the ambience, never in place of them.
- A film going to festivals or dubbing needs a sound team: it gets the handoff package, never an
  imitation.

## Traps

- Another export per master nobody asked for. Free or not (picsart-video-rules says which tools are), each
  is a render and a file in the user's Drive.
- Music the user brought, shipped without asking whether they hold its rights.
- Archiving the film without its
  asset rows: a film without its means of production
  cannot be revised or continued.
