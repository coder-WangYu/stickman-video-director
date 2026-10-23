---
name: stickman-videos-dongyu
description: "Use stickman-videos-dongyu (Dongyu) when turning copy, notes, articles, or topics into customizable-length English stick-figure videos (in 10-second multiples: 30s, 60s, 3min, 5min, default 60s), kinetic line-animation explainers, motivational shorts, or Gemini Omni Flash prompt packages. Phase A includes English VO script text (plus user-language reference translation); Phase B generation prompts stay visuals-only (no spoken audio / dubbing)."
---

# Stickman Videos Dongyu

## Core contract

Turn one source into a confirmed director's proposal and then N standalone prompts for approximately ten-second Gemini Omni Flash clips (where N = target duration in seconds / 10; default 6 clips for 60 seconds). Preserve the source's meaning while structuring it through a high-completion 5-stage emotional narrative arc.

**Default audio / copy policy (this fork):**
- **Phase A (like upstream):** include the full **English VO / 旁白文案 as plain text**, with a reference translation in the user's language, scaled to ~20–25 English words per 10-second clip. This narration text is required for planning and user approval.
- **Phase B (this fork):** generation prompts stay **visuals-only / mute speech**. Do **not** put spoken VO lines, narrator voice profiles, lip-sync speech, dialogue, or dubbing into Omni Flash prompts unless the user explicitly asks to restore voiceover into generation (then apply `references/voice-continuity.md`).
- Optional ambient BGM/SFX for picture rhythm is allowed in prompts; spoken words are not (by default). Narration text approved in Phase A is for humans / later post-production VO, not for the video model by default.

## Setup gate

Require these before planning:

- source material
- aspect ratio: `16:9` or `9:16`
- target duration: in multiples of 10 seconds (e.g. `30s`, `60s`, `90s`, `3min`, `5min`; default: `60s` / 6 clips if unspecified)
- visual style and theme:
  - `Style 1 (Classic Minimalist)`: light (white background, black figure) or dark (black background, white figure)
  - `Style 2 (Modern Beanie Zeke)`:
    - `Style 2A (Modern Studio Tech)`: pure white high-key studio, subtle light-gray perspective grid, floating cyan/blue glass UI
    - `Style 2B (Cinematic Story)`: full-color narrative environments, cinematic lighting & depth
  - `Style 3 (Prehistoric Hand-Drawn / Dark Comedy)`: expressive white filled heads, black stick limbs, animal-hide costumes and earthy prehistoric settings; story-specific casting
  - `Style 4 (Cozy Storytelling / 治愈故事风)`: expressive minimalist white-filled characters with dark stick limbs in full-color 2D cartoon environments; varied story locations and cinematic shot changes
  - `Style 5 (Historical Cartoon / 历史卡通风)`: white-filled round heads, simple black oval eyes and thin black stick limbs in era-specific costume, with cel shading and full-color painterly historical settings

If aspect ratio or visual style is missing, ask for all missing items in one concise message and stop. If duration is omitted, default to 60 seconds (6 clips). If a user provides a duration not divisible by 10, round to the nearest 10-second multiple. If a user specifies only light or dark theme, default to Style 1. Never select an aspect ratio or style silently. Do not re-ask choices already supplied.

Urgency, generation cost, client pressure, and requests to "pick normal settings" do not waive this gate.

## Workflow

1. Read `references/storyboard-template.md` and `references/style-catalog.md`. Structure the narrative using the **5-Stage High-Completion Heartbeat Engine** (Golden Hook → Disrupting Assumptions → Unveiling Insider Secrets → Ultimate Truth Revelation → Elevation & Interactive Discussion), with timing dynamically scaled to the target duration. Produce Phase A in the user's language **with English VO script text and a reference translation** (original Phase A narration content). Do **not** require narrator voice casting for generation by default.
2. Stop after the director's proposal and request explicit approval of Phase A (including the VO/旁白文案).
3. If the user changes ratio, duration, style, theme, narration, scene structure, or global direction, recompose Phase A and request approval again.
4. Only after approval of the current Phase A, read `references/omni-flash-prompt-contract.md` and produce Phase B (**visual prompts only; mute speech by default**). Use the approved VO text to keep visual beats aligned, and for optional post-production overlay notes—but do **not** inject spoken VO into generation prompts unless voiceover-into-generation was restored.
5. Use `references/examples.md` only when a concrete end-to-end example would resolve ambiguity. When citing examples for Phase B, strip their spoken voice blocks unless the user restored voiceover into generation.

Topic approval, schedule pressure, or approval of an older draft is not approval of the current Phase A.

## Output rules

For Style 3, read `references/prehistoric-dark-comedy.md` before planning. Its casting, story rhythm, palette and continuity rules override the generic no-idle, device-count and five-stage discussion-ending rules below. Use setup → escalation → ironic payoff for narrative shorts; do not force a discussion question into a visual punchline. This is a visual storytelling style, not a claim about actual prehistory.

For Style 4, read `references/cozy-storytelling.md` before planning and prompt assembly. Default each new ten-second segment to a different recognizable story setting, unless the user explicitly requests one location or approves a deliberate return. Preserve characters, drawing grammar, important props and movement direction—not an identical table or background across the whole video. Name the location cuts and any time jumps in Phase A. This is full-color cartoon storytelling, not a hand-drawn/sketchbook mode and not a claim of photorealistic 3D backgrounds.

For Style 5, read `references/historical-cartoon.md` before planning and prompt assembly. Keep its drawing grammar fixed while changing the era pack. Confirm story-specific cast cards, setting, palette, props and **exact narration text** in Phase A; repeat the full approved style and visible cast descriptions in every Phase B prompt. Its historical palette, physical-action pacing and story ending override generic three-color, device-count, no-idle and discussion-ending rules below. Do not apply this style's character rules to Styles 1–4. Still omit spoken voice blocks from Phase B prompts under the default mute-generation policy.

- Structure every script using the 5-stage high-completion flow:
  1. **Golden Hook**: Instant curiosity trigger via a counter-intuitive question or visual paradox. Timing is flexible based on duration (e.g. within the first 2–5 seconds in short videos, up to 10–15s in long videos); never open with generic platitudes.
  2. **Disrupting Assumptions**: State what everyone thinks is true, then shatter it in one sentence to build cognitive conflict.
  3. **Unveiling Insider Secrets**: Pull back the curtain on hidden mechanics, counter-intuitive details, or the real obstacle.
  4. **Ultimate Truth Revelation**: Deliver the underlying business logic or human psychology truth with maximum cognitive payoff.
  5. **Elevation & High-Engagement Discussion**: Conclude with a memorable punchline and an irresistible discussion prompt that sparks debate in the comments (include it in Phase A VO text; do not put spoken lines into Phase B generation prompts).
- Scale English VO word count in Phase A to approximately 20–25 words per 10-second clip across N clips (e.g. ~60–75 words for 30s / 3 clips, ~120–150 words for 60s / 6 clips, ~360–450 words for 3min / 18 clips, ~600–750 words for 5min / 30 clips). Keep a reference translation in the user's language.
- Phase B must **not** re-introduce spoken VO or narrator voice blocks into generation prompts. Carry on-screen action through timed visuals; optional post-production overlay notes may echo short phrases from the approved Phase A VO.
- Give each clip three timed beats, at least four relevant visual devices, and a visual change every two to three seconds.
- Keep character proportions, line weight, and style consistent across all clips.
- For Style 1, freeze the concise character anchor from `references/style-catalog.md` and repeat it verbatim in every clip. Keep two arms and two legs, one current pose per limb, stable proportions and uniform medium line weight; a moving arm replaces its previous pose rather than adding another arm. Keep the figure monochrome and saturated accents on props/graphics. Do not replace the anchor with "same character", ellipses, numeric anatomy recipes, skeleton/path instructions or clip-specific appearance descriptions. Occasional simple line expressions are allowed; the head remains hollow. Keep rich actions and effects separate from character design. Treat generated consistency as a visual acceptance check, not a guarantee from repeated text.
- For Style 1, limit the video to three saturated accent colors named with ordinary descriptive words (e.g. vivid red, electric blue, warm gold). For light theme, enforce a flat, digitally pure-white canvas with no textures, gradients, or 3D depth.
- For Style 2 (Modern Beanie Zeke), enforce character consistency from `references/style-catalog.md`:
  - Clip 1: `A minimalist 2D animated stick figure with a solid opaque white circular head (filled white face plate, thick black outline; never hollow, never transparent, never see-through), simple black-dot cartoon eyes and a simple black-line cartoon mouth that changes expression by clip, wearing a bright red beanie (smooth rounded knit, no pom-pom) and a yellow t-shirt, with simple black stick limbs and shorts, simple oval feet and three-fingered cartoon hands. Simple black lines, vibrant colors, smooth 2D animation style.`
  - Clips 2–N: `The same minimalist 2D animated stick figure with the same solid opaque white circular head (filled white face, thick black outline; never hollow or transparent), bright red beanie and yellow shirt, black stick limbs and shorts... Simple black lines, vibrant colors, smooth 2D animation style.`
  - **Solid opaque white circular head** (filled face, thick black outline)—never hollow or transparent.
  - **Every clip names a beat-matched simple cartoon expression** (dot/arc eyes + simple mouth shapes). No realistic pupils/irises/skin. Expression changes must not redesign head fill, beanie, shirt, or proportions.
- For Style 2A (Modern Studio Tech), enforce: `in a modern bright white studio space with subtle light-gray perspective grid lines on the floor plane. High-key studio lighting, clean white negative space, sleek glowing cyan and electric blue glass holographic UI elements.` Always include negative constraint: `STRICTLY MINIMALIST, NO CIRCUIT BOARD TEXTURES, NO SCI-FI WALL PANELS, NO CRACKED CONCRETE.`
- For Style 2B (Cinematic Story), specify full-color narrative setting and cinematic lighting while preserving the 2D animated stick-figure character design.
- For Style 4, freeze each approved character's complete anchor and repeat it in every clip where that role appears. Separate static design from first-frame positions, timed prop transfers and final states; changing scene does not reset prop ownership. Read its reference for shot variety and visual acceptance checks.
- For all styles, avoid abstract liquid/shape morphing. Drive motion with concrete character actions (leaping, touching glass, drawing luminous lines, opening doors) with timed beats across `[0–3s]`, `[3–7s]`, and `[7–10s]`. Never leave the character idle.
- **Mute speech by default:** every Phase B prompt must forbid spoken dialogue, voiceover, narration, lip-sync speech, and on-screen speech bubbles. Do not include a narrator voice block. Optional ambient BGM/SFX may support mood; do not mix "voice-first" instructions.
- Never place technical color notation (hex, RGB, Pantone) inside generation prompts.
- Default generated clips to no visible words, letters, numbers, or interface copy. Put optional two-to-five-word overlays in a separate post-production note.
- Match every clip ending to the next clip opening through action, an important prop, screen direction or a planned cut. Style 4 uses deliberate scene changes or approved time jumps; it does not require the same background in adjacent clips.
- Do not invent unsupported facts, statistics, quotations, or product claims.

## Revision rules

Recompose rather than rename:

- `16:9`: stage action across left, center, and right; use lateral tracking and negative space.
- `9:16`: use depth, stacked motion, vertical reveals, and interface-safe placement.

Theme, ratio, duration, or style changes require a fresh visual balance check. A global change invalidates prior approval.

## Final check

Apply the checklist in the loaded reference. Repair any failed condition before responding.
