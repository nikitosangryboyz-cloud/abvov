# VK Reference Reverse Engineering — V2

## Source

Seven supplied contact sheets of VK-style community covers were analyzed as the visual reference set. The contact sheets show repeated cover compositions across tattoo studios, automotive, retail, gaming, travel, education, finance, food, beauty, personal brands and services.

## Important source limitation

The supplied material is a set of contact sheets, not the original PSD/Figma files. Therefore exact font family names, exact pixel coordinates, original layer effects, original image sources, and exact canvas dimensions cannot be recovered with certainty. Coordinates below are normalized estimates from the visible cover compositions. They are intended as reconstruction rules, not claims about hidden source files.

The visible cover cards consistently use a very wide panoramic ratio in the contact sheets. For our production, normalize the recovered geometry to the actual VK target canvas (normally 1920×768) while preserving the relative composition.

---

# 1. Core composition DNA observed across the reference set

## 1.1 The cover is built as a single visual scene

The strongest examples do not look like a collection of UI cards. They read as one panoramic art-directed scene containing:

- one dominant visual environment;
- one primary subject or product group;
- one dominant typographic statement;
- a small number of supporting information elements;
- controlled atmosphere and depth.

Do not turn the cover into a grid of independent promotional modules.

## 1.2 Typical visual hierarchy

The recurring hierarchy is:

1. primary subject / face / product / environment;
2. main headline or brand name;
3. secondary statement;
4. one or two proof/value details;
5. small location / contact / CTA / metadata;
6. decorative atmosphere.

The hierarchy is visual first, informational second.

## 1.3 Text is part of the image composition

The reference covers do not treat typography as a separate block placed over a finished photo. Text is integrated into the scene and is positioned relative to the subject, negative space, lighting and visual mass.

## 1.4 Large typography is common

The dominant headline frequently occupies roughly 25–45% of the cover width and 20–55% of the cover height, depending on the composition archetype. Condensed display faces, high-contrast serif faces, bold grotesks and expressive script/display faces are used according to the brand mood.

## 1.5 Human subjects are deliberately cropped

Portraits commonly extend beyond one or more canvas edges. Heads and shoulders can enter from the top or bottom. The subject is not always centered; often the face occupies the central visual axis while typography sits beside it.

## 1.6 Depth is constructed in layers

Typical depth stack:

1. atmospheric/background image;
2. secondary texture or pattern;
3. large environmental objects;
4. main subject;
5. foreground objects or particles;
6. typography;
7. small labels / CTA;
8. glow, grain and final color treatment.

---

# 2. Coordinate system

Use normalized coordinates instead of fixed pixels.

```text
X = 0% left edge → 100% right edge
Y = 0% top edge → 100% bottom edge
```

Every important element should be recorded as:

```text
X
Y
WIDTH
HEIGHT
ANCHOR
ALIGNMENT
Z-INDEX
```

For production on 1920×768, convert percentages to pixels only after the composition is locked.

---

# 3. Composition archetypes recovered from the references

## CT-01 — Left Typography / Right Hero

### Geometry

```text
┌────────────────────────────────────────┐
│ eyebrow / logo     background           │
│                                         │
│ HUGE HEADLINE           HERO SUBJECT   │
│ HUGE HEADLINE           HERO SUBJECT   │
│ subtitle / proof                        │
│ small CTA / metadata                   │
└────────────────────────────────────────┘
```

### Typical zones

- Headline: X 8–45%, Y 20–65%, W 30–42%, H 25–50%.
- Hero subject: X 48–100%, Y 0–100%, W 35–52%, H 75–105%.
- Eyebrow/logo: X 8–40%, Y 7–20%.
- Supporting copy: X 10–45%, Y 65–85%.
- CTA / proof: X 10–55%, Y 75–94%.

### Logic

Heavy typographic mass balances a large photographic subject. Negative space between text and subject is intentional but can be partially bridged by atmosphere or overlap.

---

## CT-02 — Centered Subject / Split Typography

### Geometry

```text
┌────────────────────────────────────────┐
│ small label            small label     │
│                                        │
│ TITLE LEFT     PERSON / OBJECT    TITLE│
│ TITLE LEFT     PERSON / OBJECT    TITLE│
│ subtitle                         CTA   │
└────────────────────────────────────────┘
```

### Typical zones

- Subject: X 40–63%, Y 5–100%, W 20–30%, H 80–105%.
- Left title: X 12–42%, Y 25–65%, W 25–32%.
- Right title/info: X 60–88%, Y 25–70%, W 20–28%.
- Small labels: Y 7–20%.

### Logic

The person/object is the visual anchor. Typography acts as a frame around it rather than competing with it.

---

## CT-03 — Central Brand / Symmetrical Product Group

### Geometry

```text
┌────────────────────────────────────────┐
│                LOGO                    │
│               SUBHEAD                  │
│                                        │
│      OBJECT 1       OBJECT 2           │
│                                        │
│             LOCATION / CTA             │
└────────────────────────────────────────┘
```

### Typical zones

- Logo: X 30–70%, Y 7–28%.
- Subhead: X 35–65%, Y 23–38%.
- Objects: left X 5–50%, right X 50–95%, Y 35–95%.
- Metadata: centered around Y 86–98%.

### Logic

Used strongly by automotive and product presentations. The top center is reserved for brand identity; the bottom becomes the product stage.

---

## CT-04 — Full-Width Hero Scene / Embedded Headline

### Geometry

```text
┌────────────────────────────────────────┐
│ background / atmosphere                │
│                                        │
│ headline        main scene             │
│ headline        main scene             │
│ tags / proof                           │
└────────────────────────────────────────┘
```

### Typical zones

- Headline: X 20–55%, Y 20–60%.
- Main subject: X 48–100%, Y 0–100%.
- Tags: X 20–60%, Y 58–88%.

### Logic

The scene does most of the storytelling. Text is compact and editorial rather than arranged into a conventional sales grid.

---

## CT-05 — Large Script / Editorial Portrait

### Geometry

```text
┌────────────────────────────────────────┐
│                                        │
│ GIANT DISPLAY TYPE       PERSON        │
│ GIANT DISPLAY TYPE       PERSON        │
│ small subtitle          small info     │
└────────────────────────────────────────┘
```

### Typical zones

- Display type: X 8–55%, Y 12–72%.
- Person/group: X 52–100%, Y 0–100%.
- Subtitle: X 25–55%, Y 65–90%.

### Logic

The typography itself is a major graphic object. It can overlap the photography or sit behind it.

---

## CT-06 — Dark Cinematic Personal Brand

### Geometry

```text
┌────────────────────────────────────────┐
│ brand label                            │
│                                        │
│ NAME / TITLE        PERSON             │
│ NAME / TITLE        PERSON             │
│ short description         proof/info   │
└────────────────────────────────────────┘
```

### Typical zones

- Name/title: X 10–48%, Y 18–70%.
- Person: X 45–82%, Y 0–100%.
- Info: X 72–97%, Y 30–80%.
- Brand label: X 15–45%, Y 7–18%.

### Logic

Dark textured environment, controlled rim light, restrained color accents, large display typography and a portrait integrated into the background.

---

## CT-07 — Product + Information Frame

### Geometry

```text
┌────────────────────────────────────────┐
│ small label                            │
│ HEADLINE              PRODUCT          │
│ HEADLINE              PRODUCT          │
│ short offer            QR / CTA        │
└────────────────────────────────────────┘
```

### Typical zones

- Headline: X 7–48%, Y 20–65%.
- Product: X 48–100%, Y 5–100%.
- Offer: X 8–52%, Y 62–88%.
- QR/CTA: X 80–97%, Y 70–95%.

### Logic

Product remains large and tactile. Information is compact and subordinate.

---

## CT-08 — Minimal Light Editorial

### Geometry

```text
┌────────────────────────────────────────┐
│ logo / eyebrow                         │
│                                        │
│ ELEGANT HEADLINE      PERSON / OBJECT  │
│ subtitle              PERSON / OBJECT  │
│ small proof / CTA                        │
└────────────────────────────────────────┘
```

### Typical zones

- Headline: X 8–52%, Y 25–65%.
- Subject: X 48–100%, Y 0–100%.
- CTA: X 10–65%, Y 68–90%.

### Logic

High-key background, soft shadows, restrained palette, generous negative space, serif/editorial typography and clean information pills.

---

# 4. Typography rules observed

## 4.1 Headline scale

The primary word or name is usually the largest element in the typographic hierarchy.

Approximate relative scale:

- primary headline = 100%;
- secondary headline = 55–75%;
- subtitle = 18–35%;
- metadata = 8–18%.

## 4.2 Common display characteristics

Observed typography falls into four families:

1. condensed grotesk / industrial;
2. high-contrast editorial serif;
3. expressive handwritten/script;
4. wide geometric grotesk / futuristic display.

The exact font must not be invented from the contact sheet. Match the visual characteristics instead unless the actual font is known.

## 4.3 Typographic contrast

Strong examples often use one dominant contrast pair:

- condensed + clean sans;
- serif + grotesk;
- script + grotesk;
- ultra-bold + light;
- white + one accent color.

Do not use four or five competing display styles in one cover.

## 4.4 Tracking

Large display type is often tightly tracked. Small labels are more likely to use increased tracking, especially uppercase eyebrow text.

---

# 5. Color system observed

The references repeatedly use one dominant color world plus one accent.

Typical combinations:

- black / charcoal + red;
- black / graphite + violet;
- black / teal + cyan;
- white / cream + muted green;
- warm beige + brown/gold;
- blue / white + electric blue;
- white + magenta;
- dark brown + bronze/orange.

Rule:

```text
DOMINANT ENVIRONMENT 70–90%
ACCENT 5–20%
NEUTRAL TYPOGRAPHY 5–20%
```

The exact percentages vary; the important observation is that accent colors are controlled rather than distributed everywhere.

---

# 6. Photography and object treatment

## Portraits

- isolate or softly blend the subject into the environment;
- use rim light when the background is dark;
- allow the subject to overlap typography when this increases depth;
- avoid a cut-out sticker appearance unless the reference explicitly uses it.

## Products

- products are large enough to be recognized immediately;
- perspective is usually realistic;
- shadows and reflections anchor the product to the scene;
- foreground overlap is frequently used to create depth.

## Environment

- background should carry the brand mood;
- texture is often visible but subordinate;
- atmospheric fog, smoke, particles, light streaks, glow and depth blur are used selectively.

---

# 7. Decorative language

Observed decorative elements include:

- thin geometric lines;
- neon/light arcs;
- technical grids;
- subtle patterns;
- dust/particles;
- smoke/fog;
- torn-paper edges;
- organic leaves/branches;
- badges and pills;
- QR codes;
- location pins;
- small icons;
- handwritten annotations;
- circular framing elements.

Rule: decoration should support the composition's visual rhythm. It must not become a collection of random AI-generated ornaments.

---

# 8. Negative space

Negative space is not empty by accident. It is used to:

- protect headline readability;
- separate face/product from text;
- create a visual pause;
- create contrast against a dense image;
- guide the eye toward the brand name or CTA.

A common mistake is filling every empty area. The references show that controlled emptiness is a major part of the premium appearance.

---

# 9. Information density

The references are information-dense, but density is hierarchical.

Preferred order:

```text
ONE dominant message
+
ONE supporting message
+
1–4 small proof/details
+
optional CTA / location / contact
```

Avoid:

```text
headline + 8 advantages + 4 buttons + 6 icons + 3 cards
```

That turns the cover into a generic advertising banner and is specifically contrary to the strongest references.

---

# 10. Layer model for reconstruction

When rebuilding a reference, use this layer order unless the source clearly differs:

```text
00 Canvas / base color
01 Background image or environment
02 Large background texture
03 Secondary environment elements
04 Atmospheric effects
05 Large decorative geometry
06 Main subject / portrait / product
07 Foreground elements
08 Main headline
09 Secondary headline
10 Subtitle
11 Badges / pills
12 CTA / proof
13 Logo / micro-branding
14 Grain / final color treatment
```

Every layer should have a reason to exist.

---

# 11. Reconstruction procedure

For each new reference:

1. isolate the visible cover from the contact sheet;
2. identify the visual center;
3. identify the dominant subject;
4. identify the dominant text mass;
5. map every major element to X/Y/W/H percentages;
6. identify anchor relationships;
7. identify layer order;
8. identify typographic family and relative sizes;
9. identify color hierarchy;
10. identify atmosphere and depth;
11. identify negative-space zones;
12. assign the closest composition archetype CT-01…CT-08;
13. preserve the geometry when adapting the content;
14. only then create the new visual.

---

# 12. Hard rules for future AI generation

- Do not create a generic marketing banner.
- Do not invent a new composition when a reference is supplied.
- Do not turn the composition into cards or a UI grid unless the reference itself does so.
- Do not distribute text evenly just to fill space.
- Do not make every element equally important.
- Do not use random icons.
- Do not add decorative elements that have no compositional role.
- Preserve the reference's visual center and major negative-space zones.
- Preserve the relative size hierarchy of the main headline and main subject.
- Replace content, not composition, during reference adaptation.
- When exact source data cannot be recovered, mark it as approximate instead of inventing certainty.

---

# 13. Target output for VK

Default production target:

- Desktop: 1920×768.
- Mobile: 1080×1920.
- All critical text and identity elements must be checked against VK safe zones.
- Desktop and mobile should be treated as recompositions of the same art direction, not unrelated designs.

---

# 14. Quality gate

A cover is not approved until all questions are YES:

- Does it read as one scene?
- Is there one clear visual hero?
- Is the headline clearly dominant?
- Is the text positioned relative to the image rather than floating arbitrarily?
- Is the negative space intentional?
- Are there no unnecessary cards or generic UI modules?
- Does the color hierarchy match the intended art direction?
- Are foreground/background layers creating believable depth?
- Does the composition preserve the reference's geometry when adaptation is requested?
- Is every decorative element justified?
- Does it look designed rather than generated?

---

# 15. Reference-set conclusion

Across the supplied reference boards, the strongest common pattern is **art-directed panoramic composition** rather than a fixed visual style. The subject, typography and atmosphere change by niche, but the production logic remains consistent:

```text
SCENE
↓
HERO SUBJECT
↓
TYPOGRAPHIC MASS
↓
SUPPORTING INFORMATION
↓
ATMOSPHERE / DEPTH
↓
MICRO DETAILS
```

This is the core system to preserve in future VK cover production.
