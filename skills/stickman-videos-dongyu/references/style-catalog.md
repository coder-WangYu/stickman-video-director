# Style Catalog: Style 2B Only (Modern Beanie / Cinematic Story)

This fork of `stickman-videos-dongyu` supports **only Style 2B**. Do not offer or select Styles 1, 2A, 3, 4, or 5. Character DNA is the Style 2 Modern Beanie figure; environment is always full-color cinematic narrative settings.

---

## 1. Style overview

| Style Key | Style Name | Visual Theme | Best For | Character Design |
|---|---|---|---|---|
| **Style 2B** | Modern Beanie - Cinematic Story (彩色故事风) | Full-color narrative environments, cinematic lighting & depth (warm room, dusk, desert, summit, city night, etc.) | Emotional storytelling, personal growth, motivational journeys, narrative hooks | Solid-white-head beanie figure (red beanie / yellow t-shirt defaults) + simple clip-matched expressions inside rich environmental lighting |

**In plain language:** Pixar-like story short. Immersive full-color scenes (warm lamplit bedroom, dusk window, desert highway, mountain ridge above clouds) + cinematic narrative light—while the character stays a clean 2D stick figure.

---

## 2. Character DNA Anchors (Anti-Deformation Lock)

To prevent character drift, bug-eye deformations, or clothing loss across clips, use these exact character anchors (swap confirmed costume fields when the user changed them in costume fill-in):

**Clip 1 Character Anchor:**
```text
A minimalist 2D animated stick figure with a slightly smaller solid opaque white circular head (filled white face plate, thick black outline; never hollow, never transparent, never see-through), with a short opaque solid white cylindrical neck fused seamlessly to the bottom of the head (same continuous filled white as the face plate flowing into the neck—no gap, no floating head, not a disconnected piece; not a stick line, not gray; thin black outline on the neck; neck clearly visible above the shirt collar—never head glued flat onto the shoulders without a neck), simple black-dot cartoon eyes and a simple black-line cartoon mouth that changes expression by clip, wearing a bright red beanie (smooth rounded knit, no pom-pom) and a yellow t-shirt, with simple black stick arms, black shorts, and slightly longer black stick legs (not chibi, not stubby), simple oval feet and slightly flattened solid black oval palm hands (soft pancake/disc palms—not round balls, no separate fingers). Simple black lines, vibrant colors, smooth 2D animation style.
```

**Subsequent Clips Character Anchor (Clips 2–N):**
```text
The same minimalist 2D animated stick figure with the same slightly smaller solid opaque white circular head (filled white face, thick black outline; never hollow or transparent), the same short opaque solid white cylindrical neck fused seamlessly to the head (same continuous white as the face, no gap, thin black outline), bright red beanie and yellow shirt, black stick arms, black shorts, and the same slightly longer black stick legs (not chibi)... Simple black lines, vibrant colors, smooth 2D animation style.
```

**Face & expression rules:**
- Head is always a **solid opaque white disk** with a thick black outline under the beanie—never a hollow ring, never transparent, never showing background through the face.
- Keep facial marks **simple cartoon**: two black dots or short arcs for eyes; mouth as a simple curve, open O, grin with a small white tooth row only when smiling big, frown, grit, etc. No realistic pupils, irises, eyelids, nose, skin pores, or photoreal lips.
- **Every clip must name one primary expression** matched to that clip's story beat, mood, and environment. Put the expression in both Phase A scene notes and the Phase B prompt's character/action lines.
- Expression may change across the three timed beats inside a clip if the beat demands it; do not leave a blank/neutral face when the beat is emotional.
- Expression changes must not redesign head fill, outline thickness, beanie, shirt, limb style, or proportions.
- **Proportion lock (this fork):** slightly smaller head, short opaque solid white cylindrical neck fused seamlessly to the head (same continuous white as the face, no gap, thin black outline), slightly longer legs—not chibi, not stubby, not oversized head. Keep this silhouette from the frozen anchor; do not drift back to a floating/disconnected neck, head-on-shoulders, or short stubby legs.
- **No Pom-Poms**: Specify smooth rounded beanie top to prevent erratic pom-poms or winter tassels.
- **Always Include Both Beanie and T-shirt** (or the user-confirmed costume substitutes): omitting the shirt results in naked stick bodies; omitting the beanie results in a different character.
- **Anti bug-eye**: never request detailed pupils, irises, eyelashes, or photorealistic facial contours.

---

## 3. Style 2B Environment Specification

```text
in a rich full-color cinematic environment [describe setting: e.g., a dimly lit cozy bedroom with warm lamplight / a vast open desert highway under a glowing dusk sky / a dramatic mountain ridge above rolling golden clouds]. Cinematic volumetric lighting, soft depth of field, atmospheric narrative mood.
```

### Character & style consistency in environment
- The character remains the same minimalist 2D stick figure: solid opaque white circular head, red beanie, yellow shirt (or confirmed costume), black stick limbs; name a beat-matched expression each clip.
- Keep smooth 2D vector aesthetics for the character even within a textured atmospheric background.
- Vary recognizable story locations across clips when the narrative benefits; name location cuts in Phase A.

### Negative constraints
```text
Negative constraints: no photorealistic human skin, no realistic facial rendering (keep simple cartoon face on solid white head), no hollow/transparent head, no 3D humanoid CGI uncanny valley models, no chaotic line glitches, no speech bubbles, no dialogue text boxes. No pure-white studio grid, no cyan holographic UI panels (this fork is cinematic story, not studio tech).
```

---

## 4. Motion dynamics

- Do not use abstract liquid/morphing transformations that trigger latent flicker.
- Drive motion with concrete character actions in cinematic space: running into depth, opening a door into warm light, climbing a ridge, reaching for a glowing prop, turning toward a window, etc.
- **Pacing**: Every 10-second clip must feature distinct actions across `[0–3s]`, `[3–7s]`, and `[7–10s]`. Never let the character stand idle or stare at the camera for multiple seconds.

---

## 5. Audio note (generation default)

This fork's Phase B is **mute speech by default**. Optional ambient BGM/SFX may support mood. If the user restores voiceover into generation, apply `voice-continuity.md`. Do not put spoken VO into prompts by default.

### Optional ambient continuity (when used)
- **Clip 1**: quiet thoughtful instrumental + subtle ambient bed matching the scene mood.
- **Clips 2–N**: continue the identical instrumental bed (tempo/instrumentation), with synchronized crisp SFX on physical actions. No spoken words.

---

## 6. Visual beat pacing template (10-second clip)

```text
Timed Synchronized Visual Beats:
- [0–3s]: [Setup / premise action — character enters, acts, or inherits momentum from previous clip]
- [3–7s]: [Escalation / discovery — character interacts with environment or solves visual obstacle]
- [7–10s]: [Climax & outgoing transition — character delivers payoff and initiates outgoing motion for next clip]
```

Phase A may still map VO text to these beats for human / post VO; Phase B prompts stay picture-only unless VO-into-generation was restored.
