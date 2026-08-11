# Open-Source Design Toolkit

Curated open-source projects selected for the VK social-media design workflow.

## Goal

The target output is not generic UI. The target is premium VK community artwork like the reference library in `02_COMPOSITION_SYSTEM`: strong composition, large typography, controlled hierarchy, cinematic/editorial imagery, and editable Figma layers where practical.

## Selected stack

| Priority | Project | Why we need it |
|---|---|---|
| 1 | Figma MCP Server | Lets AI work with Figma design context and supports design-to-Figma workflows. |
| 2 | Tokens Studio for Figma | Stores typography, color, spacing and other design decisions as reusable tokens and can sync them with GitHub. |
| 3 | Design MD / SKILL generator | Extracts Figma styles and layout signals into DESIGN.md/SKILL.md so AI can follow a consistent visual system. |
| 4 | Image-to-Figma Component Converter | Research reference for turning raster references into editable Figma layers/components. |
| 5 | AI Happy Design | AI-agent-oriented CLI approach for programmatically creating structured Figma designs and exporting them for verification. |
| 6 | Figma Community Resources | Official index of open-source Figma plugins, including color, design-system, export, icon and utility tools. |
| 7 | OpenLark Social Media Cover Generator | Useful reference for generating social-media cover graphics from structured HTML and exporting them as images. |
| 8 | Builder.io HTML to Figma | Useful reference for converting structured HTML layouts into editable Figma designs. |
| 9 | InStretch Design | Reference architecture for organizing a complete social-media identity: covers, menu, buttons, highlights, widgets and service cards. |
| 10 | Business Design Kit | Reference architecture for managing brand assets, typography, color concepts, social graphics and templates in one dashboard. |

## What we actually use

### Core

- Figma MCP
- Tokens Studio
- Design MD / SKILL workflow
- Our own Reverse Engineering + Composition Blueprint system

### Supporting research

- Image-to-Figma
- AI Happy Design
- HTML-to-Figma
- Figma Community Resources
- Social Media Cover Generator

### Architecture references

- InStretch Design
- Business Design Kit

## Important distinction

These projects are building blocks and references. They do not replace our composition system or automatically produce the exact reference-quality VK covers we want.

Our own pipeline remains:

```text
CLIENT BRIEF
    ↓
REFERENCE IMAGE
    ↓
REVERSE ENGINEERING
    ↓
COMPOSITION BLUEPRINT
    ↓
ART DIRECTION
    ↓
IMAGE / OBJECT GENERATION
    ↓
FIGMA ASSEMBLY
    ↓
TYPOGRAPHY + SPACING TOKENS
    ↓
SAFE-ZONE CHECK
    ↓
VISUAL QC
    ↓
VK DESKTOP + MOBILE
```

## Quality target

The visual target is the reference board supplied by the owner of this repository: premium, dense-but-controlled VK covers with strong photography/3D objects, expressive typography, clear hierarchy, intentional negative space, and no generic AI-banner look.
