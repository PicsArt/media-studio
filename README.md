# Picsart Media Studio for Claude

Create, edit, preview and render videos and images in Claude, in plain language. This plugin gives Claude the skills to use the Picsart Media Studio connector well: it turns your requests into editable scenes built from your own clips and photos, media from Picsart Drive, text and Picsart templates, and saves finished renders to your Picsart Drive.

Media Studio doesn't generate or alter media with AI. Claude can use AI to understand your media, for example to transcribe speech or find the subject of a shot. Every change to the media itself is an algorithmic edit or your own.

## Install

**In Claude:** open the directory, find Picsart Media Studio, and add the plugin. It connects the Picsart Media Studio connector, which asks you to sign in to Picsart.

**In Claude Code**, run:

```
/plugin marketplace add PicsArt/media-studio
/plugin install picsart-media-studio@picsart-media-studio
```

Then ask *"Show me what Picsart Media Studio can do."*

## Skills

<!-- generated-skills:start -->

Use cases, the entry points a user asks for:

| Skill | Description |
|---|---|
| [`animate-design`](./skills/animate-design) | Turn static material into a real motion-designed video. |
| [`edit-footage`](./skills/edit-footage) | Make videos from the user's own footage, or copy a reel's structure onto their script. |
| [`get-started`](./skills/get-started) | Get started with Picsart Video. |
| [`make-cartoon`](./skills/make-cartoon) | Make a short cartoon clip with a character the user picks or describes. |
| [`make-screen-videos`](./skills/make-screen-videos) | Turn a screen recording of an app or site into videos. |
| [`recreate-video`](./skills/recreate-video) | Rebuild a reference video as an editable animated scene that moves and looks like it. |

Skills the use cases load:

| Skill | Description |
|---|---|
| [`app-ui-animation`](./skills/app-ui-animation) | Build a phone or web UI in a scene with scrolling, carousels, button feedback, cursor paths and clicks, context menus, drag-and-drop, synchronized controls, bottom sheets and frosted-glass panels. |
| [`asset-audit`](./skills/asset-audit) | Audit media assets BEFORE they enter scene cards, boxes or looks. |
| [`caption-decorations`](./skills/caption-decorations) | Author and validate scene caption decorations, choosing between measured procedural decoration presets and arbitrary scene artwork. |
| [`character-rigging`](./skills/character-rigging) | Build and animate a 2D cartoon character in a scene. |
| [`custom-transitions`](./skills/custom-transitions) | How to write a new scene transition as an inline JSON definition. |
| [`design-layer-import`](./skills/design-layer-import) | Bring a design or static assets into a scene as LAYERS, not flat frames, whenever they are going to move. |
| [`edit-on-your-computer`](./skills/edit-on-your-computer) | Edit footage on the user's own computer. |
| [`edit-pipeline`](./skills/edit-pipeline) | Run an edit of the user's footage as fixed stages, with a project record (standing decisions, approvals, the pace, a locked meaning map, every version), resume from the first stage not done, and the gate rules every check follows. |
| [`face-hiding`](./skills/face-hiding) | Hide the faces in a video or photo by blurring or pixelating them. |
| [`figma-storyboard-animation`](./skills/figma-storyboard-animation) | Turn a Figma storyboard of static frames into an animated scene. |
| [`film-cutting`](./skills/film-cutting) | Cut a film's accepted takes into one scene. |
| [`film-finishing`](./skills/film-finishing) | Finish a film after picture lock. |
| [`footage-analysis`](./skills/footage-analysis) | Watch the user's own talking footage and turn it into facts you can build on. |
| [`footage-reframing`](./skills/footage-reframing) | Put the user's own footage in a frame of another shape. |
| [`large-scene-assembly`](./skills/large-scene-assembly) | Build large editable scenes by decomposing a timeline into bounded scenes and reusable components, defining timing and asset contracts, then assembling and safely consolidating them. |
| [`linked-element-motion`](./skills/linked-element-motion) | Keep related scene elements aligned and moving together, including container resizing, shared fades, content reveals and sibling reflow. |
| [`motion-design-craft`](./skills/motion-design-craft) | The craft of adding motion to any scene, whatever the video. |
| [`motion-intent`](./skills/motion-intent) | Choose and diagnose scene motion from communication intent before selecting presets or keyframes. |
| [`motion-pattern-library`](./skills/motion-pattern-library) | Worked scene motion patterns for entrances, exits, stagger, directional nudges, emphasis, ambient life, springs, arcs, layered beats, parenting, parallax, focus, wipes, drawn strokes, and cartoon fast motion (smears, multiples, speed lines). |
| [`motion-review`](./skills/motion-review) | Review an existing scene for motion that is confusing, mistimed, distracting, broken at a seam, or unnecessarily expensive. |
| [`motion-scene-continuity`](./skills/motion-scene-continuity) | Plan and diagnose continuity across scene beats and scene boundaries—semantic handoffs, dominant direction, shared visual carriers, causal action/reaction, intentional resets, and seam verification. |
| [`motion-tracking-from-video`](./skills/motion-tracking-from-video) | Measure what objects visibly do in a video. |
| [`photo-slideshow`](./skills/photo-slideshow) | Build a photo promo or slideshow in a scene. |
| [`picsart-video-rules`](./skills/picsart-video-rules) | The rules every Picsart Video use case follows. |
| [`quality-review`](./skills/quality-review) | Check work before the user sees it. |
| [`quick-merge-and-export`](./skills/quick-merge-and-export) | The shortest path from media URLs to a rendered file. |
| [`realistic-color-grade`](./skills/realistic-color-grade) | Make a video's colours look more realistic and natural with the ai_realism look. |
| [`reel-structure`](./skills/reel-structure) | Read a reference reel's structure and format, never its content. |
| [`reference-fragment-matching`](./skills/reference-fragment-matching) | Rebuild a reference video as a scene one fragment at a time. |
| [`resting-frame-rules`](./skills/resting-frame-rules) | Keep every element whole or gone whenever motion stops. |
| [`retention-hooks`](./skills/retention-hooks) | Keep a short video watched to the end with open loops. |
| [`scene-3d-authoring`](./skills/scene-3d-authoring) | Build a 3D scene (a composition whose space is 3d). |
| [`scene-animation-reference`](./skills/scene-animation-reference) | How a scene expresses motion. |
| [`scene-building-basics`](./skills/scene-building-basics) | Build and edit a scene with the scene tools. |
| [`scene-template-remix`](./skills/scene-template-remix) | Select, reuse and customize scene catalog items. |
| [`screen-recording-analysis`](./skills/screen-recording-analysis) | Read a screen recording from its pixels. |
| [`screen-recording-layouts`](./skills/screen-recording-layouts) | Lay a screen recording out in a 1080x1920 vertical frame or a 1920x1080 landscape one. |
| [`screen-recording-zoom`](./skills/screen-recording-zoom) | The house zoom for screen footage in a panel. |
| [`screen-ui-redesign`](./skills/screen-ui-redesign) | Recreate the screens of a recording as designed motion UI. |
| [`social-posting`](./skills/social-posting) | Post a finished video to the user's own TikTok, Instagram, YouTube or other connected accounts through the Picsart app's post preview. |
| [`speech-aware-cutting`](./skills/speech-aware-cutting) | Choose the moments of talking footage worth keeping and cut them so no one is clipped mid-sentence. |
| [`spoken-captions`](./skills/spoken-captions) | Put spoken words on screen from the transcript. |
| [`visual-style`](./skills/visual-style) | A video's style, chosen by eye and kept. |

<!-- generated-skills:end -->

## Privacy and support

- Privacy policy: https://picsart.com/privacy-policy
- Support: https://support.picsart.com/hc/en-us/requests/new
- A problem with a skill: open an issue in this repository.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

[MIT](./LICENSE)
