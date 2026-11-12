# Scope and formats

## Scope — phased

- **Phase 1 (now): motion-design static material into an ad/reel.** A Figma design's layers — or
  the user's own uploaded assets — → a composed, animated scene → tuned by eye → rendered. All
  of what follows.

## Formats — scene is the source of truth

Everything is authored and edited as a **scene** — the format the engine natively
supports and the one every `picsart_scene_*` / `picsart_media_*` edit / validate / query tool speaks, and the
one `sceneRef` points at. The **mp4** is *derived* from it at Stage 5 (`export`). The scene
is the single editable source of truth — keep it and edit it; the mp4 is the final
render, never an editing surface.
