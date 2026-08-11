# VK COVER TOOLKIT — GitHub Research

## Purpose

This file collects open-source GitHub projects that can strengthen our VK cover production system.

The goal is NOT to copy another designer's visual style.

The goal is to borrow useful engineering, automation, Figma, banner-generation and design-system ideas, then combine them with our own MASTER REFERENCE SYSTEM.

---

# 1. Priority projects

## A. Banner generation

### Sai1099/Banner_Generation_Tool
https://github.com/Sai1099/Banner_Generation_Tool

**Priority: HIGH**

Why it matters:
- directly targets AI banner generation;
- supports custom banner prompts;
- supports multiple generated variations;
- has a text-overlay stage;
- uses historical banner data and tags as inputs;
- separates banner creation from content generation.

The repository describes a workflow based on historical banner data, AI tagging, banner generation, and multiple text-overlay variations.

Useful ideas for our system:
1. separate visual generation from text generation;
2. generate several composition candidates;
3. keep the banner prompt and text overlay as separate stages;
4. use reference data instead of asking AI for an arbitrary "beautiful banner".

**Important:** we should NOT blindly copy its implementation or assume its current models are optimal. We use the workflow idea.

---

## B. Social-cover automation

### thelzf/socialcover-photoshop-plugin
https://github.com/thelzf/socialcover-photoshop-plugin

**Priority: HIGH**

Why it matters:
- specifically targets social-media covers and banners;
- provides ready-to-use templates;
- focuses on fast, consistent, brand-ready social graphics.

Useful idea for our system:
- treat social covers as a reusable production format;
- separate reusable templates/layout logic from the final visual content;
- keep dimensions and brand consistency as part of the system.

This is particularly relevant because our final workflow is intended for repeated VK cover production.

---

## C. Figma design-system skill

### AmroJSawan/figma-design-system-skill
https://github.com/AmroJSawan/figma-design-system-skill

**Priority: VERY HIGH**

Why it matters:
- gives Claude programmatic Figma control;
- supports design-system creation;
- audits token health;
- supports variables and component repair;
- includes visual validation loops;
- describes a workflow of inspect → create/update → screenshot → validate.

Useful ideas for our VK system:
1. always inspect the current Figma state before writing;
2. use reusable variables/tokens where appropriate;
3. avoid duplicate nodes;
4. validate the result visually after changes;
5. separate design-system rules from individual compositions;
6. make the workflow idempotent so repeated commands do not create duplicates.

This is especially useful for our Figma stage, even though its original purpose is broader design-system work.

---

## D. Figma Plugin DS

### thomas-lowry/figma-plugin-ds
https://github.com/thomas-lowry/figma-plugin-ds

**Priority: MEDIUM**

Why it matters:
- provides a lightweight UI library for Figma plugins;
- contains reusable UI components and styles;
- demonstrates how a Figma plugin interface can be standardized.

Useful ideas:
- if we later build our own VK-cover production plugin, its UI should use reusable controls rather than ad-hoc interfaces;
- useful reference for plugin UI architecture, not for the visual style of the covers themselves.

---

## E. Figma Plugin SDK Design System

### figma-plugin-sdk/design-system
https://github.com/figma-plugin-sdk/design-system

**Priority: MEDIUM**

Why it matters:
- useful reference for building structured Figma-plugin tooling;
- relevant if we turn our cover workflow into an internal production tool.

Potential future use:
- cover presets;
- typography presets;
- safe-zone presets;
- export controls;
- batch creation.

---

# 2. What we should NOT install/copy blindly

GitHub search also returns many generic banner generators and graphic-design repositories.

Do not add a repository to the production system simply because its name contains:
- banner;
- social media;
- design;
- Figma;
- AI.

Before adopting a repository, check:
- activity;
- documentation;
- license;
- actual relevance;
- whether it solves a problem we actually have;
- whether it improves our workflow rather than adding complexity.

---

# 3. Our architecture after this research

The useful ideas above should be integrated into our own workflow like this:

REFERENCES
↓
MASTER REFERENCE ANALYSIS
↓
COMPOSITION BLUEPRINT
↓
TYPOGRAPHY ONLY
↓
BACKGROUND / HERO ONLY
↓
FIGMA ASSEMBLY
↓
VISUAL QC
↓
EXPORT

The important improvement is that typography and background are now intentionally separated.

---

# 4. Core production rules

## Rule 1 — Reference first

Before generating a new cover, read the current MASTER REFERENCE SYSTEM.

## Rule 2 — Do not invent information

Only use the text supplied in the brief unless the user explicitly asks for copywriting.

Do not automatically add:
- benefits;
- icons;
- statistics;
- CTA;
- service lists;
- badges;
- decorative labels.

## Rule 3 — Separate typography and imagery

Typography can be generated/constructed as an independent asset.

Background/hero imagery can be generated separately.

The final composition is assembled in Figma.

## Rule 4 — Figma is the assembly layer

Use Figma for:
- editable typography;
- precise coordinates;
- scaling;
- spacing;
- layer order;
- final image placement;
- export.

## Rule 5 — Visual validation

After assembly, inspect the complete cover at 100% and at reduced size.

The cover must remain readable and visually coherent from a distance.

---

# 5. Immediate implementation priorities

### Priority 1
Master Reference System — already created.

### Priority 2
Typography library for our covers:
- condensed display;
- grotesk;
- editorial serif;
- script/accent;
- bold italic/display.

### Priority 3
Composition library based on the user's own references.

### Priority 4
Figma reusable cover frames:
- 1920×768 desktop;
- safe zones;
- typography groups;
- background placeholder;
- export frame.

### Priority 5
Automated visual QC checklist.

### Priority 6
Only after the above: consider building a dedicated Figma plugin for rapid cover production.

---

# 6. Selected GitHub sources

1. https://github.com/Sai1099/Banner_Generation_Tool
2. https://github.com/thelzf/socialcover-photoshop-plugin
3. https://github.com/AmroJSawan/figma-design-system-skill
4. https://github.com/thomas-lowry/figma-plugin-ds
5. https://github.com/figma-plugin-sdk/design-system

---

# 7. Bottom line

There is no single GitHub repository that already contains the exact "AI → VK cover → Figma → same designer style" system we need.

The strongest approach is to combine:

- our own reference-derived visual system;
- banner-generation workflow ideas;
- social-cover automation ideas;
- Figma design-system automation;
- precise Figma assembly;
- visual QC.

Our MASTER REFERENCE SYSTEM remains the authority for visual decisions.

GitHub projects are supporting infrastructure, not the source of our creative style.
