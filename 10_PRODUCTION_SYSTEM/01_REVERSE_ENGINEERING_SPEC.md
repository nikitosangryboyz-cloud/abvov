# Reverse Engineering Spec — VK Covers

## Purpose

Turn a visual reference into a measurable composition blueprint before creating a new design.

The reference controls **composition logic**. Client content, imagery, branding and copy are replaced unless explicitly requested otherwise.

## Base canvas

Default VK Desktop: **1920×768**.

All measurements must be recorded as percentages first, then converted to pixels when building in Figma.

```text
x% = left edge / canvas width
 y% = top edge / canvas height
w% = element width / canvas width
h% = element height / canvas height
```

## Mandatory element inventory

Every reference must be decomposed into:

1. Background / environment
2. Main subject or product
3. Secondary subjects / props
4. Eyebrow / micro-label
5. Main headline
6. Subheadline
7. Supporting copy
8. CTA / badge / pill
9. Logo / brand mark
10. Decorative graphics
11. Light / texture / particles
12. Footer / location / contacts
13. Safe-zone conflicts

## Per-element record

For every visible element record:

```text
ID:
TYPE:
ROLE:
X:
Y:
WIDTH:
HEIGHT:
ANCHOR:
ALIGNMENT:
ROTATION:
Z-INDEX:
VISUAL_WEIGHT:
CROP_BEHAVIOR:
RELATIONSHIPS:
```

### Anchor vocabulary

- left
- right
- top
- bottom
- center
- optical-center
- baseline
- edge-bleed
- object-relative

### Relationship vocabulary

- centered-on
- aligned-to
- offset-from
- overlaps
- frames
- balances
- intersects
- follows
- mirrors

## Composition hierarchy

Assign each element one level:

### L1 — Dominant
The element seen first from a distance. Usually one subject or one headline.

### L2 — Primary support
The other half of the main visual story: secondary headline, person, product, vehicle, etc.

### L3 — Information
Subtitles, location, service descriptors, badges.

### L4 — Decoration
Lines, particles, textures, glows, small symbols.

## Blueprint output

Before Figma assembly produce:

```text
CANVAS
PRIMARY AXIS
PRIMARY SUBJECT
TEXT ZONE
SECONDARY ZONES
DECORATIVE ZONES
SAFE ZONE
VISUAL WEIGHT
```

## Reference adaptation rule

Do not reproduce the source artwork as a finished copy. Preserve the **layout logic** while replacing:

- business
- copy
- logo
- photography
- products
- colors when appropriate
- decorative language

## Quality gates

Reject the blueprint if:

- there is no obvious primary focal point;
- headline and subject compete equally without intentional reason;
- more than 3 major focal zones exist;
- text is too small for VK cover viewing;
- important content sits outside safe zones;
- the layout becomes a generic card/grid instead of the reference composition;
- decorative elements are added without a compositional role.

## Final principle

**We do not ask “what style is this?” first. We ask “where is every element, what is it aligned to, and what visual job does it perform?”**
