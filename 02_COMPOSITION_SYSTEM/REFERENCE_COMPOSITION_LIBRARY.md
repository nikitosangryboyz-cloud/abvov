# REFERENCE COMPOSITION SYSTEM v1.0

## Purpose

This is a geometry-first system for reconstructing VK cover compositions from visual references. The goal is to preserve the placement logic of a reference while replacing its content for a new client/niche.

## Coordinate system

Use normalized percentages instead of fixed pixels whenever possible.

- X = horizontal position from 0% (left) to 100% (right)
- Y = vertical position from 0% (top) to 100% (bottom)
- Also record WIDTH and HEIGHT as percentages of the canvas
- Record ANCHOR and ALIGNMENT
- Record Z-INDEX / visual layer order

Base VK desktop canvas: 1920×768.

```text
X 0%                                  X 100%
┌────────────────────────────────────────┐
│                                        │ Y 0%
│                                        │
│                                        │
│                                        │
│                                        │
└────────────────────────────────────────┘ Y 100%
```

## CT-01 — Cinematic Tattoo

### Composition map
- Small top label: X ~39–59%, Y ~12–21%, width ~22%, centered, very small eyebrow text.
- Main headline: X ~33–65%, Y ~28–62%, width ~35%, 2 lines, large, central.
- Left main object: X ~2–29%, Y ~8–66%, large, partially cropped by edge.
- Right main object: X ~68–98%, Y ~8–90%, large, partially cropped by edge.
- Left badge: X ~14–28%, Y ~58–79%, small, high contrast.
- Right badge: X ~77–89%, Y ~31–53%.
- Subtitle: X ~36–66%, Y ~74–86%, small, centered.

### Logic
Large central headline + two physical objects framing the composition.

## CT-02 — 3D Models / Product

### Composition map
- Main headline: X ~27–68%, Y ~24–59%, 2 lines, large, centered.
- Icon before headline: X ~36–43%, Y ~25–40%, small, directly adjacent to text.
- Left object: X ~4–31%, Y ~30–88%, large, partially exits bottom.
- Right object: X ~70–97%, Y ~18–72%.
- Horizontal CTA panel: X ~29–70%, Y ~67–83%, directly below headline.
- Circular element: X ~77–94%, Y ~68–100%, partially cropped by bottom edge.

### Logic
Central text block is visually squeezed between two objects, with CTA directly underneath.

## CT-03 — Automotive / Symmetrical Products

### Composition map
- Logo: X ~32–69%, Y ~8–25%, large, centered.
- Subtitle: X ~40–61%, Y ~25–37%, centered.
- Vehicle/object 1: X ~8–48%, Y ~40–92%.
- Vehicle/object 2: X ~52–94%, Y ~38–92%.
- Location/caption: X ~35–68%, Y ~89–98%, very small.

### Logic
Symmetrical composition: identity and subtitle above two major objects.

## CT-04 — Gaming / Product + Type

### Composition map
- Left console/product: X ~3–19%, Y ~20–88%, vertical.
- Main headline: X ~14–57%, Y ~30–65%, very large.
- Small brand label: X ~55–72%, Y ~24–40%.
- Main controller/product: X ~73–99%, Y ~10–88%, dominant right-side object.
- Product thumbnails: X ~39–67%, Y ~77–97%.

### Logic
Large typography left/center + dominant product on the right.

## CT-05 — Travel Editorial

### Composition map
- Main headline: X ~23–53%, Y ~15–53%, 2 lines, very large.
- Person: X ~58–89%, Y ~3–100%, main visual, head reaches near top edge.
- Resort/architecture: X ~82–100%, Y ~25–83%.
- Tags: X ~18–57%, Y ~56–82%, multiple small pills.
- Foreground: lower ~10–20%, plants/objects/environment.

### Logic
Text left → person right → environmental elements fill the composition.

## CT-06 — Soft Family / Group

### Composition map
- Decorative symbol: X ~21–40%, Y ~13–38%.
- Logo: X ~9–45%, Y ~42–68%, large.
- Description: X ~18–46%, Y ~69–91%, small.
- People/group: X ~47–93%, Y ~0–100%, dominant visual block; heads approach top edge.

### Logic
Large group on the right + calm textual block on the left.

## CT-07 — Personal Brand / Tattoo

### Composition map
- Main title: X ~14–48%, Y ~18–60%, large, 2 lines.
- Subtitle: X ~15–45%, Y ~60–78%.
- Person: X ~48–78%, Y ~0–100%, primary visual.
- Logo: X ~74–90%, Y ~17–34%.
- Information block: X ~75–96%, Y ~45–78%, small text.

### Logic
Person sits between a large title and a right information column.

## CT-08 — Dramatic Portrait / Split Typography

### Composition map
- Central portrait: X ~43–61%, Y ~18–90%, centered on main axis.
- Left headline: X ~18–44%, Y ~28–58%.
- Right headline: X ~59–82%, Y ~28–58%.
- Top-left label: X ~26–43%, Y ~10–22%.
- Top-right label: X ~62–77%, Y ~10–22%.
- Script subtitle: X ~26–49%, Y ~57–78%.
- CTA: X ~59–79%, Y ~69–91%.

### Logic
TEXT → SUBJECT → TEXT. The central subject is physically framed by typography on both sides.

## CT-09 — Fashion / Editorial

### Composition map
- Huge script headline: X ~10–53%, Y ~14–65%, occupies almost half the height.
- Subtitle: X ~30–52%, Y ~57–76%.
- Location: X ~32–51%, Y ~72–87%.
- People: X ~56–99%, Y ~3–98%, dominant photographic group.

### Logic
Oversized decorative typography left + photographic group right.

## CT-10 — Dark Personal Brand

### Composition map
- Small brand label: X ~22–43%, Y ~8–20%.
- Main title: X ~8–46%, Y ~24–71%, very large, decorative.
- Description: X ~17–47%, Y ~70–89%.
- Person: X ~48–79%, Y ~3–100%.
- Information: X ~75–97%, Y ~37–78%.

### Logic
Huge left title + central person + right information column.

# Required extraction format for every new reference

When a new reference is supplied, do not merely describe its style. Produce a COMPOSITION BLUEPRINT containing:

```text
CANVAS
MAIN OBJECT
SECONDARY OBJECTS
TEXT BLOCKS
BADGES
CTA
DECORATION
SAFE ZONE

For every element:
X
Y
WIDTH
HEIGHT
ANCHOR
ALIGNMENT
Z-INDEX
```

# Workflow rule

1. Reconstruct the reference composition.
2. Separate DESIGN SYSTEM from CONTENT.
3. Adapt content to the new client/niche.
4. Rebuild as editable Figma elements.
5. Check readability, hierarchy, safe zones, object scale, and similarity of composition logic.

Do not mix reference systems automatically. Mix CT templates only when explicitly requested.
