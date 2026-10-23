# Omni Flash Production Prompt Contract

Use this contract only after explicit approval of the current Phase A. Refer to `references/style-catalog.md` for full style specifications and prompt blueprints.

**Default (this fork): visuals-only.** Do not apply `voice-continuity.md`. Do not include English dialogue, narrator voice blocks, or dubbing instructions. Every prompt must mute speech.

Style 3 (Prehistoric Hand-Drawn / Dark Comedy): read `prehistoric-dark-comedy.md` and apply its override rules. Repeat the full approved cast descriptions for all visible roles, white filled heads, expressive cartoon faces, hair/clothing, earthy setting and layout in every prompt. Do not apply generic face/hair/texture bans or idle bans to its deliberate reaction beats. Use story-appropriate ambient music instead of mandatory piano. Explicitly identify intended time jumps; otherwise match adjacent states. Technical output specs are targets, not guarantees of interface capabilities.

Style 4 (Cozy Storytelling / 治愈故事风): read `cozy-storytelling.md`. Repeat full character anchors, but give each segment its approved new setting. Describe each scene opening as a recognizable new location, then connect action/prop/screen direction or a named time cut. Do not repeat one global room layout, inherit Style 1's no-face/filled-body bans, or require hand-drawn/paper aesthetics. Keep movable-object appearance separate from initial positions and timed state changes.

Style 5 (Historical Cartoon / 历史卡通风): read `historical-cartoon.md` for its standalone prompt order and overrides. Repeat the full frozen drawing anchor, visible cast cards and approved era pack in every clip. Keep solid oval eyes and black stick limbs, with historical costume and colored painterly scenery. Do not inherit Style 1's hollow-head/no-face/no-clothes contract or generic piano, three-color, four-device and no-idle requirements. Follow its era score, physical beats and planned cuts; do not shorten approved anchors to meet an arbitrary character budget. Omit voice blocks under the default policy.

## Production package order

Deliver these sections in order:

1. Global continuity block
2. N standalone English prompts (where N = target duration / 10; default 6 clips for 60s)
3. Stitching guide
4. Optional ambient music/SFX note (no voice / no VO)

## Global continuity block

State the chosen aspect ratio (`16:9` or `9:16`), target duration, selected visual style, character anchor design, palette or environment definition, **silent / no-voiceover policy**, optional ambient audio mood, and continuity strategy. Treat this block as a review summary; each prompt still repeats all critical locks.

## Standalone prompt order

Write every prompt in this order:

1. Output specification: approximately ten seconds, chosen aspect ratio (`16:9` or `9:16`), 720p target, 24 FPS; **no spoken dialogue or voiceover** (ambient SFX/BGM optional)
2. Environment and background definition:
   - For Style 1 Light: flat, uniform, digitally pure-white canvas with no shading or 3D depth
   - For Style 1 Dark: flat, uniform, pitch-black canvas with pure white line art
   - For Style 2A (Studio Tech): modern bright white studio space with subtle light-gray perspective grid lines on the floor plane, high-key lighting, clean white negative space, sleek glowing cyan/blue glass elements
   - For Style 2B (Cinematic Story): rich full-color cinematic environment with volumetric lighting and depth of field
   - For Style 4 (Cozy Storytelling): full-color 2D cartoon environment and a segment-specific setting, with varied wide/close/moving shots; new segment means an intentional scene change unless otherwise approved
3. Character lock:
   - For Style 1: repeat the concise frozen character anchor from `style-catalog.md`, including the chosen polarity and expression setting; no "same character" shortcuts, numeric anatomy recipes, skeleton/rig definitions or pen paths. Keep the circular head hollow, proportions and line weight stable, and only the current pose of each of the two arms and two legs. A raised arm replaces its old lowered line. Keep accents on props/graphics, never recolor the figure. Do not let action or camera wording redefine the drawing; preserve rich motion and effects separately.
   - For Style 2 (Modern Beanie Zeke):
     - First clip: `A minimalist 2D animated stick figure with a solid opaque white circular head (filled white face plate, thick black outline; never hollow, never transparent, never see-through), simple black-dot cartoon eyes and a simple black-line cartoon mouth that changes expression by clip, wearing a bright red beanie (smooth rounded knit, no pom-pom) and a yellow t-shirt, with simple black stick limbs and shorts, simple oval feet and three-fingered cartoon hands. Simple black lines, vibrant colors, smooth 2D animation style.`
     - Subsequent clips: `The same minimalist 2D animated stick figure with the same solid opaque white circular head (filled white face, thick black outline; never hollow or transparent), bright red beanie and yellow shirt, black stick limbs and shorts... Simple black lines, vibrant colors, smooth 2D animation style.`
     - After the frozen anchor, add one line: `Expression this clip: …` naming a simple cartoon face matched to the beat/mood/environment (and optional beat-by-beat tweaks). Never use a hollow or transparent head.
   - For Style 4: repeat its full frozen character anchor from `cozy-storytelling.md`, including white head/torso fill, dark limbs and simple facial marks. Location and expression changes do not redesign the character.
4. Palette and accent roles (expressed only with ordinary color names, no hex or technical codes)
5. Composition strategy for the chosen ratio (`16:9` or `9:16`)
6. First-frame state inherited from the previous clip
7. `[0–3s]`, `[3–7s]`, and `[7–10s]` visual beats (picture-only; not tied to spoken lines)
8. Explicit mute-speech lock (required): `No voiceover, no narration, no spoken dialogue, no lip-synced speech, no speech bubbles, no dialogue boxes.`
9. Optional ambient BGM/SFX only (no "voice-first" mix). Subsequent clips may continue the same instrumental bed from clip 1.
10. Final-frame transition state inherited by the next clip
11. Negative constraints (including style-specific clutter/deformation bans)

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
- Drive motion with concrete character actions (leaping, touching glass, drawing luminous lines, opening heavy doors).
- Ensure continuous character engagement; never leave the character standing idle or staring at the camera for multiple seconds.

## Speech and visual text

Default is **silent picture**:

```text
No voiceover, no narration, no spoken dialogue, no lip-synced speech. Strictly no speech bubbles, no dialogue boxes.
```

Do not quote VO lines. Do not include a narrator voice profile.

Default every generated clip to no visible words, letters, numbers, captions, subtitles, interface copy, palette labels, production annotations, logos, or watermarks. Require icon-only message bubbles, content cards, clocks, meters, and notifications. Put optional approved phrases in a separate post-production overlay list outside the prompts.

## Palette notation

Use ordinary descriptive color names such as vivid red, electric blue, or warm gold. Never put hexadecimal, RGB, HSL, Pantone, or other technical color notation in a generation prompt. Models may reproduce prominent notation literally as unwanted interface text.

## Ambient audio (optional, non-speech)

If ambient bed is desired:

1. Clip 1 may establish a quiet instrumental theme.
2. Clips 2–N may continue the identical instrumental bed (tempo/instrumentation), with synchronized crisp SFX on physical actions.
3. Never instruct the model to speak, narrate, or dub.

## Negative contract

Forbid:

- photorealism and unwanted 3D humanoid rendering
- photorealistic facial features (pupils, irises, realistic lips, skin) or hair unless approved; Style 2 still requires its solid white cartoon face and named simple expressions
- extra limbs, malformed anatomy, disconnected lines, or changed proportions
- broken or changing line weight
- **For Style 1**: do not reject allowed occasional simple line expressions as character drift; filled heads, sudden head/body proportion changes, duplicated/retained limb poses, body silhouettes, separate hand/foot shapes and detached body lines remain failures. Inspect actual footage at reaches, releases, turns and walking poses, and compare clips. State the scope of inspection: sparse keyframes cannot prove the absence of brief errors.
- inverted theme polarity or unexplained colors
- unintended characters or irrelevant spectacle
- visible words, letters, numbers, technical color notation, palette labels, interface copy, captions, subtitles, logos, or watermarks
- any spoken dialogue, voiceover, narration, or lip-synced speech
- speech bubbles, comic dialog balloons, or visual text boxes
- **For Style 2A specifically**: `strictly minimalist studio aesthetic, no circuit board textures, no sci-fi wall panels, no spaceship corridors, no cracked concrete, no grunge textures`
- **For Style 2B specifically**: `no photorealistic human skin, no 3D humanoid CGI models, no chaotic line glitches`

## Stitching guide

List all N clips in order. For every cut, repeat the ending state and its continuing action/prop/direction, or state the approved location/time change. Style 4 changes scenery intentionally rather than requiring identical backgrounds. Include any trim or match-cut note needed for assembly; inspect actual generated joins rather than assuming requested wipes landed on the last frame.

## Phase B checks

- The user approved the current Phase A.
- Exactly N standalone prompts are present (matching approved Phase A duration).
- Each prompt repeats ratio (`16:9` or `9:16`), style/theme, character, palette, mute-speech lock, transition, and negative locks.
- Style 1 prompts repeat one identical full character block and contain no contradictory appearance instructions. Simple-expression allowance agrees with the negative constraints. Generated consistency is checked separately from prompt compliance.
- Each prompt has all three timed beats and at least four relevant visual devices.
- Every ending connects to the next opening through a planned action/prop/direction or an approved location/time cut. Style 4 does not repeat one room unless requested.
- No English VO / narrator voice block / dubbing instructions appear in prompts (unless the user restored VO).
- Mute-speech lock is present in every prompt.
- Standalone prompts contain no hexadecimal, RGB, HSL, Pantone, or other technical color notation.
- Style 2 prompts feature the verified character anchor (solid opaque white head), a named clip expression, and anti-clutter negative constraints. No hollow/transparent head wording remains.
- Generated scenes contain no visible writing; optional overlay phrases are listed separately for post-production.
