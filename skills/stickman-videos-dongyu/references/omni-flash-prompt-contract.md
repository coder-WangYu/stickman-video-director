# Omni Flash Production Prompt Contract

Use this contract only after explicit approval of the current Phase A. Refer to `references/style-catalog.md` for Style 2B specifications and prompt blueprints.

**This fork is Style 2B only (Modern Beanie / Cinematic Story).** Ignore Style 1 / 2A / 3 / 4 / 5 branches in any examples or legacy notes. Do not require reading `prehistoric-dark-comedy.md`, `cozy-storytelling.md`, or `historical-cartoon.md` for normal runs.

**Default (this fork): visuals-only.** Do not apply `voice-continuity.md` unless the user restores VO into generation. Do not include English dialogue, narrator voice blocks, or dubbing instructions. Every prompt must mute speech.

## Production package order

Deliver these sections in order:

1. Global continuity block
2. N standalone English prompts (where N = target duration / 10; default 6 clips for 60s)
3. Stitching guide
4. Optional ambient music/SFX note (no voice / no VO)

## Global continuity block

State the chosen aspect ratio (`16:9` or `9:16`), target duration, visual style **Style 2B (Cinematic Story)**, character anchor design (with confirmed costume), cinematic environment mood, **silent / no-voiceover policy**, optional ambient audio mood, and continuity strategy. Treat this block as a review summary; each prompt still repeats all critical locks.

## Standalone prompt order

Write every prompt in this order:

1. Output specification: approximately ten seconds, chosen aspect ratio (`16:9` or `9:16`), 720p target, 24 FPS; **no spoken dialogue or voiceover** (ambient SFX/BGM optional)
2. Environment and background definition — **Style 2B only**: rich full-color cinematic environment with volumetric lighting and depth of field (name the specific setting per clip)
3. Character lock — Style 2 Modern Beanie figure:
   - First clip: `A minimalist 2D animated stick figure with a slightly smaller solid opaque white circular head (filled white face plate, thick black outline; never hollow, never transparent, never see-through), with a short opaque solid white cylindrical neck fused seamlessly to the bottom of the head (same continuous filled white as the face plate flowing into the neck—no gap, no floating head, not a disconnected piece; not a stick line, not gray; thin black outline on the neck; neck clearly visible above the shirt collar—never head glued flat onto the shoulders without a neck), simple black-dot cartoon eyes and a simple black-line cartoon mouth that changes expression by clip, wearing a bright red beanie (smooth rounded knit, no pom-pom) and a yellow t-shirt, with simple black stick arms, black shorts, and slightly longer black stick legs (not chibi, not stubby), simple oval feet and slightly flattened solid black oval palm hands (soft pancake/disc palms—not round balls, no separate fingers). Simple black lines, vibrant colors, smooth 2D animation style.`
   - Subsequent clips: `The same minimalist 2D animated stick figure with the same slightly smaller solid opaque white circular head (filled white face, thick black outline; never hollow or transparent), the same short opaque solid white cylindrical neck fused seamlessly to the head (same continuous white as the face, no gap, thin black outline), bright red beanie and yellow shirt, black stick arms, black shorts, and the same slightly longer black stick legs (not chibi)... Simple black lines, vibrant colors, smooth 2D animation style.`
   - Swap confirmed costume fields when the user changed them in costume fill-in.
   - After the frozen anchor, add one line: `Expression this clip: …` naming a simple cartoon face matched to the beat/mood/environment (and optional beat-by-beat tweaks). Never use a hollow or transparent head.
4. Palette and accent roles (expressed only with ordinary color names, no hex or technical codes)
5. Composition strategy for the chosen ratio (`16:9` or `9:16`)
6. First-frame state inherited from the previous clip
7. `[0–3s]`, `[3–7s]`, and `[7–10s]` visual beats (picture-only; not tied to spoken lines)
8. Explicit mute-speech lock (required): `No voiceover, no narration, no spoken dialogue, no lip-synced speech, no speech bubbles, no dialogue boxes.`
9. Optional ambient BGM/SFX only (no "voice-first" mix). Subsequent clips may continue the same instrumental bed from clip 1.
10. Final-frame transition state inherited by the next clip
11. Negative constraints (2B anti-clutter / anti-deformation bans)

Make each prompt self-contained and usable without any external context.

## Style language

Use this wording to request density without character drift:

> rapid scene changes, kinetic motion-graphic transformations, and frequent visual events, while preserving an identical stick-figure design, constant line weight, and strict temporal consistency

Avoid `rapid style changes`, which can invite model changes to drawing style, line weight, or character design.

## Timed visual sequence & motion dynamics

Translate the approved storyboard row into three connected physical events:

- `[0–3s]`: establish or inherit the visual premise.
- `[3–7s]`: transform, escalate, or explain the metaphor through character action.
- `[7–10s]`: deliver a climax and create the next transition.

### Anti-Stutter & Anti-Lag Guidelines:
- Do not use abstract liquid or object shape morphing (e.g., stairs melting into a clock), as these cause diffusion latent jitter and frame drops.
- Drive motion with concrete character actions (leaping, opening doors into warm light, running into depth, reaching for props, climbing, turning toward windows).
- Ensure continuous character engagement; never leave the character standing idle or staring at the camera for multiple seconds.

## Speech and visual text

Default is **silent picture**:

```text
No voiceover, no narration, no spoken dialogue, no lip-synced speech. Strictly no speech bubbles, no dialogue boxes.
```

Do not quote VO lines. Do not include a narrator voice profile.

Default every generated clip to no visible words, letters, numbers, captions, subtitles, interface copy, palette labels, production annotations, logos, or watermarks. Require icon-only message bubbles, content cards, clocks, meters, and notifications. Put optional approved phrases in a separate post-production overlay list outside the prompts.

## Palette notation

Use ordinary descriptive color names such as vivid red, electric blue, warm gold, dusk amber. Never put hexadecimal, RGB, HSL, Pantone, or other technical color notation in a generation prompt. Models may reproduce prominent notation literally as unwanted interface text.

## Ambient audio (optional, non-speech)

If ambient bed is desired:

1. Clip 1 may establish a quiet instrumental theme matching the cinematic mood.
2. Clips 2–N may continue the identical instrumental bed (tempo/instrumentation), with synchronized crisp SFX on physical actions.
3. Never instruct the model to speak, narrate, or dub.

## Negative contract

Forbid:

- photorealism and unwanted 3D humanoid rendering
- photorealistic facial features (pupils, irises, realistic lips, skin) or hair unless approved; Style 2B still requires its solid white cartoon face and named simple expressions
- hollow or transparent head
- extra limbs, malformed anatomy, disconnected lines, or changed proportions
- broken or changing line weight
- unintended characters or irrelevant spectacle
- visible words, letters, numbers, technical color notation, palette labels, interface copy, captions, subtitles, logos, or watermarks
- any spoken dialogue, voiceover, narration, or lip-synced speech
- speech bubbles, comic dialog balloons, or visual text boxes
- pure-white studio grid / cyan holographic UI (not 2B)
- `no photorealistic human skin, no 3D humanoid CGI models, no chaotic line glitches`

## Stitching guide

List all N clips in order. For every cut, repeat the ending state and its continuing action/prop/direction, or state the approved location/time change. Include any trim or match-cut note needed for assembly; inspect actual generated joins rather than assuming requested wipes landed on the last frame.

## Phase B checks

- The user approved the current Phase A.
- Exactly N standalone prompts are present (matching approved Phase A duration).
- Each prompt repeats ratio (`16:9` or `9:16`), Style 2B, character, cinematic setting, mute-speech lock, transition, and negative locks.
- Each prompt has all three timed beats and at least four relevant visual devices.
- Every ending connects to the next opening through a planned action/prop/direction or an approved location/time cut.
- No English VO / narrator voice block / dubbing instructions appear in prompts (unless the user restored VO).
- Mute-speech lock is present in every prompt.
- Standalone prompts contain no hexadecimal, RGB, HSL, Pantone, or other technical color notation.
- Style 2B prompts feature the verified character anchor (solid opaque white head), a named clip expression, full-color cinematic environment, and anti-clutter negative constraints. No hollow/transparent head wording remains. No 2A studio-grid / cyan UI requirements.
- Generated scenes contain no visible writing; optional overlay phrases are listed separately for post-production.
