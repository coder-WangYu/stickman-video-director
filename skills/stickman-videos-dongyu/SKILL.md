---
name: stickman-videos-dongyu
description: "Use stickman-videos-dongyu (Dongyu) when turning copy, notes, articles, or topics into customizable-length English stick-figure videos in Style 2B only (Modern Beanie / Cinematic Story: solid-white-head beanie figure in full-color cinematic narrative environments). Durations are 10-second multiples (30s, 60s, 3min, 5min, default 60s). After Setup: costume fill-in (hat + top only) → copy-ready character prompt (no image yet) → Phase A (English VO + reference translation) → Phase B visuals-only (no spoken audio)."
---

# Stickman Videos Dongyu

## Core contract

Turn one source into a confirmed director's proposal and then N standalone prompts for approximately ten-second Gemini Omni Flash clips (where N = target duration in seconds / 10; default 6 clips for 60 seconds). Preserve the source's meaning while structuring it through a high-completion 5-stage emotional narrative arc.

**Visual style (locked):** this fork supports **only Style 2B (Modern Beanie / Cinematic Story)**. Character = Style 2 Modern Beanie figure (solid opaque white circular head, red beanie, yellow t-shirt defaults, black stick limbs) inside **full-color cinematic narrative environments** with cinematic lighting and depth. If the user asks for Style 1, 2A, 3, 4, or 5, say this fork only supports Style 2B and continue with 2B.

**Default audio / copy / character policy (this fork):**
- **Costume fill-in (this fork, after Setup, before character prompt):** present a short **outfit-only fill-in** (defaults pre-filled). User may change **only hat and top**; head, face, neck, body grammar, proportions, limbs, hands, shorts, and feet stay fixed. Stop until the user confirms or edits the blanks. Then proceed to the character prompt.
- **Character lock (this fork, after costume fill-in, before Phase A):** produce a **copy-ready character prompt** (one pasteable English block) that applies the **confirmed costume** onto the fixed non-costume look. Independent of Phase A—do not bury it inside Phase A. **Do not generate a character image** here. Stop for approval of the **copyable prompt** before Phase A.
- **Phase A (like upstream):** include the full **English VO / 旁白文案 as plain text**, with a reference translation in the user's language, scaled to ~20–25 English words per 10-second clip. Use the **already-approved** character prompt as the visual cast; do not redesign the character here.
- **Phase B (this fork):** generation prompts stay **visuals-only / mute speech**. Do **not** put spoken VO lines, narrator voice profiles, lip-sync speech, dialogue, or dubbing into Omni Flash prompts unless the user explicitly asks to restore voiceover into generation (then apply `references/voice-continuity.md`).
- Optional ambient BGM/SFX for picture rhythm is allowed in prompts; spoken words are not (by default). Narration text approved in Phase A is for humans / later post-production VO, not for the video model by default.
- **Do not yet** generate or wire a character reference image into Phase B / Flow—that comes later.

## Setup gate

Require these before planning:

- source material
- aspect ratio: `16:9` or `9:16`
- target duration: in multiples of 10 seconds (e.g. `30s`, `60s`, `90s`, `3min`, `5min`; default: `60s` / 6 clips if unspecified)

**Visual style is fixed to Style 2B (Cinematic Story)** — do **not** ask for a style menu or offer Styles 1, 2A, 3, 4, or 5. State once that the visual style is locked to Style 2B (Modern Beanie figure in full-color cinematic narrative environments). If the user requests another style, reply that this fork only supports Style 2B and proceed with 2B.

If aspect ratio is missing, ask for all missing items (source / aspect ratio / duration as needed) in one concise message and stop. If duration is omitted, default to 60 seconds (6 clips). If a user provides a duration not divisible by 10, round to the nearest 10-second multiple. Never select an aspect ratio silently. Do not re-ask choices already supplied.

Urgency, generation cost, client pressure, and requests to "pick normal settings" do not waive this gate.

## Workflow

1. **Costume fill-in (after Setup, before character prompt — hat + top only):**
   - Present a **fill-in form** with only two editable fields. User may change **帽子 and 上衣 only**; do not ask to redesign head, face, neck, proportions, limbs, hands, shorts, or feet.
   - **Editable blanks** (defaults pre-filled; user may overwrite or reply「默认」):
     - 帽子 / Headwear: `bright red beanie (smooth rounded knit, no pom-pom)`
     - 上衣 / Top: `yellow short-sleeve t-shirt`
   - **Locked (never offer as blanks):** 下装 `black shorts`, 脚 `simple oval feet`, 手 `slightly flattened solid black oval palm hands`, body proportions (slightly smaller head, opaque solid white cylindrical neck, slightly longer legs).
   - Fixed non-costume look (not editable in this step): slightly smaller solid opaque white circular head, short opaque solid white cylindrical neck fused seamlessly to the head (same continuous white as the face, no gap, thin black outline), simple black-dot eyes + simple cartoon mouth, black stick arms, slightly longer black stick legs (not chibi), slightly flattened solid black oval palm hands (no separate fingers), black shorts, simple oval feet.
   - State clearly: 本步只能改帽子和上衣，其余保持不变. **Stop** until the user confirms or returns filled blanks. Do **not** emit the character prompt or Phase A yet.
2. **Character lock (after costume confirm, before Phase A — copy-ready prompt only):**
   - Output a **single copy-ready character prompt** (English, one fenced code block) that freezes the fixed non-costume look **plus the confirmed costume**. Style 2 fixed base: slightly smaller solid opaque white circular head, short opaque solid white cylindrical neck fused seamlessly to the head (same continuous white as the face, no gap, thin black outline), simple black-dot eyes + simple cartoon mouth, black stick arms, slightly longer black stick legs (not chibi), slightly flattened solid black oval palm hands (no separate fingers)—**swap only** the approved headwear and top into the prompt; keep default black shorts, oval feet, and flattened black oval palm hands.
   - Format: one contiguous prompt paragraph (or short labeled blocks if multiple cast members), **no** prose inside the copy block. A one-line label outside the fence is fine (e.g. "角色提示词（可复制）").
   - **Do not** generate any character reference image in this step.
   - Show the copyable prompt and **stop for explicit approval**. If rejected, revise the prompt (and return to step 1 if they want a different outfit); do **not** start Phase A until approved.
   - Image generation / Flow reference wiring comes later when the user asks—not in this step.
3. Read `references/storyboard-template.md` and `references/style-catalog.md`. Using the **approved character prompt**, structure the narrative with the **5-Stage High-Completion Heartbeat Engine** and produce Phase A in the user's language **with English VO script text and a reference translation**. Place the Style 2 figure inside **full-color cinematic narrative environments (2B)**. Reuse the locked character look; do not redesign cast. Do **not** require narrator voice casting for generation by default.
4. Stop after the director's proposal and request explicit approval of Phase A (storyboard + VO/旁白文案).
5. If the user changes ratio, duration, narration, scene structure, or global direction, recompose Phase A and request approval again. Style remains 2B (do not offer other styles). If they change **hat/top only**, return to step 1 then regenerate step 2. If they change non-costume cast/look, return to step 1–2 as needed before a new Phase A.
6. Only after the character lock **and** the current Phase A are approved, read `references/omni-flash-prompt-contract.md` and produce Phase B (**visual prompts only; mute speech by default**). Use the approved VO text to keep visual beats aligned—do **not** inject spoken VO into generation prompts unless voiceover-into-generation was restored. Every clip uses Style 2 character anchors inside 2B full-color cinematic settings.
7. Use `references/examples.md` only when a concrete end-to-end example would resolve ambiguity. When citing examples for Phase B, strip their spoken voice blocks unless the user restored voiceover into generation. Prefer 2B/cinematic examples; ignore other-style branches.

Topic approval, schedule pressure, or approval of an older draft is not approval of costume, character lock, or Phase A. Costume confirm alone is not character-lock approval; character-lock approval alone is not Phase A approval.

## Output rules

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
- Enforce Style 2 character consistency from `references/style-catalog.md` (apply confirmed costume in place of default beanie/shirt/shorts when different):
  - Clip 1: `A minimalist 2D animated stick figure with a slightly smaller solid opaque white circular head (filled white face plate, thick black outline; never hollow, never transparent, never see-through), with a short opaque solid white cylindrical neck fused seamlessly to the bottom of the head (same continuous filled white as the face plate flowing into the neck—no gap, no floating head, not a disconnected piece; not a stick line, not gray; thin black outline on the neck; neck clearly visible above the shirt collar—never head glued flat onto the shoulders without a neck), simple black-dot cartoon eyes and a simple black-line cartoon mouth that changes expression by clip, wearing a bright red beanie (smooth rounded knit, no pom-pom) and a yellow t-shirt, with simple black stick arms, black shorts, and slightly longer black stick legs (not chibi, not stubby), simple oval feet and slightly flattened solid black oval palm hands (soft pancake/disc palms—not round balls, no separate fingers). Simple black lines, vibrant colors, smooth 2D animation style.`
  - Clips 2–N: `The same minimalist 2D animated stick figure with the same slightly smaller solid opaque white circular head (filled white face, thick black outline; never hollow or transparent), the same short opaque solid white cylindrical neck fused seamlessly to the head (same continuous white as the face, no gap, thin black outline), bright red beanie and yellow shirt, black stick arms, black shorts, and the same slightly longer black stick legs (not chibi)... Simple black lines, vibrant colors, smooth 2D animation style.`
  - **Solid opaque white circular head** (filled face, thick black outline)—never hollow or transparent.
  - **Every clip names a beat-matched simple cartoon expression** (dot/arc eyes + simple mouth shapes). No realistic pupils/irises/skin. Expression changes must not redesign head fill, beanie, shirt, or proportions.
- **Style 2B environment (required):** specify a rich full-color narrative setting and cinematic lighting/depth while preserving the 2D animated stick-figure character design. Do **not** use Style 2A studio-grid / cyan glass UI requirements.
- Avoid abstract liquid/shape morphing. Drive motion with concrete character actions (leaping, touching objects, drawing luminous lines, opening doors, walking into depth) with timed beats across `[0–3s]`, `[3–7s]`, and `[7–10s]`. Never leave the character idle.
- **Mute speech by default:** every Phase B prompt must forbid spoken dialogue, voiceover, narration, lip-sync speech, and on-screen speech bubbles. Do not include a narrator voice block. Optional ambient BGM/SFX may support mood; do not mix "voice-first" instructions.
- Never place technical color notation (hex, RGB, Pantone) inside generation prompts.
- Default generated clips to no visible words, letters, numbers, or interface copy. Put optional two-to-five-word overlays in a separate post-production note.
- Match every clip ending to the next clip opening through action, an important prop, screen direction or a planned cut.
- Do not invent unsupported facts, statistics, quotations, or product claims.

## Revision rules

Recompose rather than rename:

- `16:9`: stage action across left, center, and right; use lateral tracking and negative space.
- `9:16`: use depth, stacked motion, vertical reveals, and interface-safe placement.

Theme, ratio, or duration changes require a fresh visual balance check. Style stays 2B. A global change invalidates prior approval.

## Final check

Apply the checklist in the loaded reference. Repair any failed condition before responding.
