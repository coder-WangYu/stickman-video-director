# Director's Proposal Contract

Use this contract for Phase A **after** the independent **character lock** step (copy-ready character prompt; text only, no image yet) is approved. Present a readable production proposal (**visual plan + English VO 旁白文案 + user-language reference translation**) and stop for confirmation before writing model prompts. Refer to `references/style-catalog.md` for style specifications.

**Default (this fork):** Phase A **must include** the narration script text (English VO + reference translation), like upstream. Reuse the approved character lock; do **not** redefine cast here. Do **not** require narrator voice casting for video generation by default. Spoken audio is omitted from Phase B generation prompts unless the user restores VO into generation (`voice-continuity.md`). Optional ambient BGM/SFX mood may be noted.

For Style 2 (2A/2B), Phase A must note a **solid white filled head** and a **per-clip cartoon expression** in the stick-figure scene column (matched to beat, mood, and environment). Do not plan a hollow/transparent face.

Style 3 (Prehistoric Hand-Drawn / Dark Comedy) is also supported. Before planning it, read `prehistoric-dark-comedy.md`; its cast-card, earthy palette, setup/escalation/payoff and reaction-pause rules override the generic five-stage, mandatory discussion-ending and device-count checks here. Include distinguishable cast cards and a location/prop continuity plan in Phase A. Treat the story as fictional analogy, not invented historical fact.

Style 4 (Cozy Storytelling / 治愈故事风) uses `cozy-storytelling.md`. In Phase A name a different recognizable main setting for each new ten-second segment by default, plus wide/close/moving shots inside it. Lock character design and important props; scenery changes intentionally. Respect an explicit single-location request or approved callback. Do not call this style hand-drawn or require the same table/room across all segments.

Style 5 (Historical Cartoon / 历史卡通风) uses `historical-cartoon.md`. Include its era pack, complete cast cards, location/prop states and **exact narration text** in Phase A. Keep the drawing grammar while adapting clothing, architecture and palette to the era. Its narrative-short ending and physical-action pacing override generic discussion-ending and four-device requirements; reactions may pause deliberately. Separate historical facts from invented comic scenes. Omit spoken voice blocks from later generation prompts under the default mute-generation policy.

## Rewrite the source

Create one natural English narration scaled to approximately 20–25 words per 10-second clip based on the target duration (e.g. ~60–75 words for 30s, ~120–150 words for 60s default, ~360–450 words for 3min, ~600–750 words for 5min), plus a beat-by-beat visual plan for N ten-second clips (N = duration / 10).

- Preserve the source's core claim, names, numbers, and factual meaning.
- Strengthen a weak opening with an immediate hook.
- Remove repetition and secondary branches from long sources.
- Expand short sources with a relevant example, progression, reframe, or callback.
- Prefer clear spoken English to literal translation.
- Simplify wording before increasing speaking speed.
- Do not invent research, statistics, quotations, product claims, or factual details.

Use the user's language for planning explanations. Keep the voiceover script in English and give a reference translation in the user's language.

## Header contract

Present these items in order:

1. English title and reference-language title
2. Core message and opening hook
3. Chosen aspect ratio (`16:9` or `9:16`), target duration (in 10s multiples), and visual style/theme (Style 1 Classic Light/Dark, Style 2A Modern Studio Tech, Style 2B Cinematic Story, Style 3–5 as applicable)
4. English VO word count (~20–25 words × N clips), estimated duration, and a note that **generation stays mute by default** (VO text is for approval / later post VO; no narrator voice casting required unless the user restores VO into generation)
5. Up to three saturated accent colors (for Style 1) or visual palette/environment mood (for Style 2+), named in ordinary language, and what each represents
6. Optional ambient BGM/SFX mood (no spoken generation); or state "silent / SFX-only for generation"
7. Reminder: cast is already locked in the prior character-lock step—cite the approved look; do not redesign

## Narrative patterns: High-Completion 5-Stage Heartbeat Engine

To break through the 60%+ video completion rate threshold, structure every script through this emotional heartbeat progression:

1. **Stage 1: Golden Hook (黄金钩子)**
   - **Timing**: Flexible based on duration (in short 30s/60s videos, delivered rapidly within the first 2–5 seconds / `[0–3s]` of Clip 1; in 3–5min videos, establishes the premise across the first 5–15 seconds).
   - **Goal**: Ask an unexpected, counter-intuitive question or present a striking visual paradox that instantly creates an irresistible information gap. Never open with slow throat-clearing.
2. **Stage 2: Disrupting Assumptions (打破常识)**
   - **Goal**: Articulate the common belief or conventional wisdom that everyone assumes to be true, then shatter it in a single decisive sentence to create cognitive conflict and suspense.
3. **Stage 3: Unveiling Insider Secrets (拉出内幕)**
   - **Goal**: Pull back the curtain on a little-known technical mechanism, hidden friction, or systemic secret that keeps the audience captivated and curious.
4. **Stage 4: Ultimate Truth Revelation (真相揭秘)**
   - **Goal**: Deliver the underlying business logic, scientific mechanism, or human psychological truth with complete clarity. Give the audience the satisfying "aha!" breakthrough.
5. **Stage 5: Elevation & High-Engagement Discussion (升华互动)**
   - **Goal**: Crystallize the takeaway into a memorable punchline (VO + visual), and finish with a provocative discussion prompt for comments. Keep the discussion line in Phase A VO text; do not speak it into Phase B generation prompts.

### Dynamic Clip Allocation by Duration ($N = \text{duration} / 10$)

- **30s (3 clips)**:
  - Clip 1: Lightning hook (0–3s) → Establish conflict
  - Clip 2: Unveil hidden reality & mechanics
  - Clip 3: Ultimate truth + Comment-debate prompt
- **60s (6 clips, default)**:
  - Clip 1: Golden Hook → Premise
  - Clip 2: Disrupt Assumptions
  - Clip 3: Unveil Insider Secrets
  - Clips 4–5: Mechanism & Ultimate Truth
  - Clip 6: Elevation punchline + Irresistible comment question
- **90s (9 clips)**:
  - Clip 1: Golden Hook
  - Clips 2–3: Disrupt Assumptions
  - Clips 4–6: Unveil Insider Secrets
  - Clips 7–8: Ultimate Truth Revelation
  - Clip 9: Elevation & Comment Discussion
- **180s+ (3–5 min)**:
  - Hook (Clip 1) → Assumptions (15–20%) → Insider Secrets (35–40%) → Ultimate Truth (30–35%) → Elevation & Discussion (final 1–2 clips)

## Storyboard contract

Produce exactly N approximately ten-second rows (where N = target duration in seconds / 10; default: 6 rows for 60s):

| Time | Narrative purpose | Stick-figure scene | Motion, camera, and transition | English VO | Reference translation | BGM / SFX |
|---|---|---|---|---|---|---|

Give each row a different narrative job aligned with the 5-stage engine. Allocate approximately 18–25 English words per row while keeping sentence boundaries natural.

## Visual-density recipe

Build every row from three sequential beats:

- `0–3s`: establish or inherit the visual premise.
- `3–7s`: transform, escalate, or explain the metaphor through physical character actions.
- `7–10s`: deliver a climax and create the next transition.

Use at least four relevant devices per row:

- expressive stick-figure action (running, jumping, touching glass, drawing lines)
- environmental transformation
- concrete visual metaphor
- diagram, arrow, or icon-only symbol
- particles, energy, fluid, explosion, or light
- camera push, pull, pan, orbit, shake, or tracking move
- foreground wipe or object crossing the lens
- match cut, shape morph, or motion-matched transition
- interaction with another figure or oversized object

Require a perceptible visual change every two to three seconds. Make every effect clarify or intensify the spoken idea; omit unrelated spectacle. Avoid abstract liquid morphing.

## Palette and text

Keep the background and stick figure monochrome according to the selected theme (for Style 1), or use high-key studio grid / cinematic lighting (for Style 2). Use no more than three saturated accent colors across the video. Assign semantic meaning such as anxiety, danger, energy, discovery, or success.

Name colors only with ordinary descriptive language. Do not use hexadecimal, RGB, HSL, Pantone, or other technical color notation anywhere in the proposal or production prompts.

Default the generated video to no visible words, letters, numbers, captions, subtitles, interface copy, or technical annotations. Make message bubbles, content cards, meters, clocks, and notifications icon-only. After the storyboard, optionally list concise two-to-five-word overlays for post-production, including their target clips and safe placement; never carry those overlays into the video-generation prompts.

## Composition by aspect ratio

- `16:9`: use left-center-right staging, lateral tracking, horizontal match cuts, and deliberate negative space. Reserve clean space for optional post-production overlays when useful.
- `9:16`: use foreground/background depth, vertical reveals, stacked motion, foreground passes, and interface-safe overlay space.

Changing ratio requires new staging, camera paths, transition geometry, and overlay-safe negative space. Changing theme or style requires updated color balance and contrast checks.

## Continuity

End each row with a visible interface that the next row inherits: a pose, moving object, filled frame, travel direction, shape, or camera motion. Name both sides of every connection in the proposal. For Style 4, an approved location cut or time jump may replace literal background matching: state what continues (character, prop, direction or story action) and what changes (place/time). Do not spend all N clips at the same desk unless explicitly requested.

## Confirmation ending

End Phase A by asking the user to:

- approve the current proposal (storyboard + English VO + reference translation) and generate the N Omni Flash prompts;
- revise a named scene or narration passage; or
- change a global setting such as aspect ratio, duration, style, theme, palette, or tone (cast/look changes return to the character-lock step first).

Do not include final model prompts. Character lock was already approved before Phase A. A global change invalidates approval and requires a revised Phase A.

## Phase A checks

- Source, aspect ratio (`16:9` or `9:16`), duration, and style/theme are known.
- Script strictly implements the 5-Stage High-Completion Heartbeat Engine.
- Final clip ends with a provocative, comment-driving discussion prompt (in VO text).
- English narration matches duration (~20–25 words per 10s clip; ~120–150 words for 60s) and a user-language reference translation is present.
- Exactly N storyboard rows have distinct narrative purposes (N = duration / 10).
- Every row has three beats, at least four visual devices, English VO, reference translation, and a transition.
- Phase A notes that Phase B generation stays mute by default (VO text is not spoken into Omni Flash unless restored).
- Approved character lock from the prior independent step is cited; Phase A does not redesign cast.
- Phase B does not yet require generating or citing a character reference image in Flow prompts.
- Visual change occurs approximately every two to three seconds.
- No more than three saturated accent colors are used (for Style 1) or clean palette rules followed (for Style 2).
- No technical color notation is present.
- Any proposed text is clearly separated as a post-production overlay and absent from generated scenes.
- Every adjacent pair has a named continuity connection.
- The ending returns to the central message and CTA.
- No unsupported factual detail was added.
