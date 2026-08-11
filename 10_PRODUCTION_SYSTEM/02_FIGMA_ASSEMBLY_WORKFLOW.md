# Figma Assembly Workflow

## Goal

Produce an editable VK cover in Figma from a Composition Blueprint.

## Layer architecture

```text
VK COVER 1920x768
├── 00_GUIDES
│   ├── Canvas
│   └── Safe Zone
├── 01_BACKGROUND
├── 02_ENVIRONMENT
├── 03_MAIN_SUBJECT
├── 04_SECONDARY_OBJECTS
├── 05_LOGO
├── 06_TYPE
│   ├── Eyebrow
│   ├── Headline
│   ├── Subheadline
│   └── Supporting
├── 07_CTA_BADGES
├── 08_DECORATION
└── 09_QC
```

## Build order

1. Create 1920×768 frame.
2. Add safe-zone guides.
3. Place background/environment.
4. Place the primary subject at the blueprint coordinates.
5. Place secondary objects.
6. Lock the visual hierarchy before adding decoration.
7. Add typography using the approved font set.
8. Match line breaks and text block geometry from the blueprint.
9. Add badges/CTA only where the blueprint requires them.
10. Add decoration last.
11. Compare the result against the reference at thumbnail size.
12. Check the safe zone.
13. Check text readability.
14. Export preview and final assets.

## Typography rule

Typography is treated as geometry, not merely copy.

For every text block specify:

```text
font-family
font-style
font-size
line-height
letter-spacing
case
line-count
width
alignment
position
```

The line breaks should be deliberate and should reproduce the intended visual mass of the reference.

## Image rule

Main imagery should behave as a designed object:

- crop intentionally;
- preserve subject hierarchy;
- allow controlled edge bleed;
- avoid random floating objects;
- use perspective/depth only when it supports the reference composition.

## Decoration rule

Decoration cannot become the design. Every decorative element must either:

- frame the subject;
- guide the eye;
- create depth;
- reinforce the brand/niche;
- balance an empty area.

## QC checklist

### Composition
- [ ] Primary focal point is obvious.
- [ ] Text blocks occupy the intended zones.
- [ ] Subject scale matches the blueprint.
- [ ] Negative space is intentional.

### Typography
- [ ] Approved fonts only.
- [ ] No accidental line breaks.
- [ ] Headline readable from thumbnail.
- [ ] Secondary text does not compete with headline.

### VK
- [ ] 1920×768 desktop canvas.
- [ ] Important content stays in safe zone.
- [ ] Mobile adaptation can be derived without destroying hierarchy.

### Finish
- [ ] No random pills/cards.
- [ ] No generic AI-banner look.
- [ ] No unnecessary icons.
- [ ] No decorative noise.
