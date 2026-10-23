# Director's Proposal Contract

Use this contract for Phase A. Present a readable **visual** production proposal and stop for confirmation before writing model prompts. Refer to `references/style-catalog.md` for style specifications.

**Default (this fork):** no voiceover, narration script, narrator casting, or dubbing plan. Story meaning is carried by timed visuals only. Skip `voice-continuity.md` unless the user explicitly restores VO.

For Style 2 (2A/2B), Phase A must note a **solid white filled head** and a **per-clip cartoon expression** in the stick-figure scene column (matched to beat, mood, and environment). Do not plan a hollow/transparent face.

Style 3 (Prehistoric Hand-Drawn / Dark Comedy) is also supported. Before planning it, read `prehistoric-dark-comedy.md`; its cast-card, earthy palette, setup/escalation/payoff and reaction-pause rules override the generic five-stage, mandatory discussion-ending and device-count checks here. Include distinguishable cast cards and a location/prop continuity plan in Phase A. Treat the story as fictional analogy, not invented historical fact.

Style 4 (Cozy Storytelling / 治愈故事风) uses `cozy-storytelling.md`. In Phase A name a different recognizable main setting for each new ten-second segment by default, plus wide/close/moving shots inside it. Lock character design and important props; scenery changes intentionally. Respect an explicit single-location request or approved callback. Do not call this style hand-drawn or require the same table/room across all segments.

Style 5 (Historical Cartoon / 历史卡通风) uses `historical-cartoon.md`. Include its era pack, complete cast cards, location/prop states in Phase A. Keep the drawing grammar while adapting clothing, architecture and palette to the era. Its narrative-short ending and physical-action pacing override generic discussion-ending and four-device requirements; reactions may pause deliberately. Separate historical facts from invented comic scenes. Omit VO/voice profile under the default visuals-only policy.

## Rewrite the source (visual narrative only)

Turn the source into a beat-by-beat **visual** plan for N ten-second clips (N = duration / 10). Do **not** write an English voiceover script or word-count VO.

- Preserve the source's core claim, names, numbers, and factual meaning.
- Strengthen a weak opening with an immediate **visual** hook.
- Remove repetition and secondary branches from long sources.
- Expand short sources with a relevant visual example, progression, reframe, or callback.
- Prefer clear scene actions the audience can understand without hearing speech.
- Do not invent research, statistics, quotations, product claims, or factual details.

Use the user's language for the whole Phase A proposal.

## Header contract

Present these items in order:

1. Title in the user's language (optional English title in parentheses)
2. Core message and opening visual hook
3. Chosen aspect ratio (`16:9` or `9:16`), target duration (in 10s multiples), and visual style/theme (Style 1 Classic Light/Dark, Style 2A Modern Studio Tech, Style 2B Cinematic Story, Style 3–5 as applicable)
4. Estimated clip count N (duration / 10) — **no** narrator voice profile, **no** English word count
5. Up to three saturated accent colors (for Style 1) or visual palette/environment mood (for Style 2+), named in ordinary language, and what each represents
6. Optional ambient BGM/SFX mood only (no spoken lines); or state "silent / SFX-only"

## Narrative patterns: High-Completion 5-Stage Heartbeat Engine

To break through the 60%+ video completion rate threshold, structure every script through this emotional heartbeat progression:

1. **Stage 1: Golden Hook (黄金钩子)**
   - **Timing**: Flexible based on duration (in short 30s/60s videos, delivered rapidly within the first 2–5 seconds / `[0–3s]` of Clip 1; in 3–5min videos, establishes the premise across the first 5–15 seconds).
   - **Goal**: Present an unexpected visual paradox or counter-intuitive situation that instantly creates an irresistible information gap. Never open with slow throat-clearing.
2. **Stage 2: Disrupting Assumptions (打破常识)**
   - **Goal**: Show the common belief visually, then shatter it in one decisive visual beat to create cognitive conflict and suspense.
3. **Stage 3: Unveiling Insider Secrets (拉出内幕)**
   - **Goal**: Reveal a little-known mechanism, hidden friction, or systemic secret through diagrams and character action.
4. **Stage 4: Ultimate Truth Revelation (真相揭秘)**
   - **Goal**: Deliver the underlying logic or psychological truth with complete visual clarity.
5. **Stage 5: Elevation & High-Engagement Discussion (升华互动)**
   - **Goal**: Crystallize the takeaway into a memorable visual punchline, and finish with a provocative discussion prompt noted for post/comments (not spoken into the generation prompt).

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

| Time | Narrative purpose | Stick-figure scene | Motion, camera, and transition | BGM / SFX (optional, no VO) |
|---|---|---|---|---|

Give each row a different narrative job aligned with the 5-stage engine. Do **not** add English VO or reference-translation columns.

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

Require a perceptible visual change every two to three seconds. Make every effect clarify or intensify the **visual** idea; omit unrelated spectacle. Avoid abstract liquid morphing.

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

- approve the current proposal and generate the N Omni Flash prompts;
- revise a named scene; or
- change a global setting such as aspect ratio, duration, style, theme, palette, or tone.

Do not include final model prompts. A global change invalidates approval and requires a revised Phase A.

## Phase A checks

- Source, aspect ratio (`16:9` or `9:16`), duration, and style/theme are known.
- Script strictly implements the 5-Stage High-Completion Heartbeat Engine as **visual** beats.
- Final clip ends with a provocative, comment-driving discussion prompt (planning note / visual CTA only).
- No English VO script, narrator profile, or dubbing plan is present (unless the user restored VO).
- Exactly N storyboard rows have distinct narrative purposes (N = duration / 10).
- Every row has three beats, at least four visual devices, and a transition.
- Visual change occurs approximately every two to three seconds.
- No more than three saturated accent colors are used (for Style 1) or clean palette rules followed (for Style 2).
- No technical color notation is present.
- Any proposed text is clearly separated as a post-production overlay and absent from generated scenes.
- Every adjacent pair has a named continuity connection.
- The ending returns to the central message and CTA.
- No unsupported factual detail was added.
