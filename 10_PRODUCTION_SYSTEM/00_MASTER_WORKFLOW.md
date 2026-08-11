# VK Design Studio — Master Workflow

## Mission

Create premium VK community artwork from strong references, with the assistant handling the design production and the owner focusing on client acquisition and approval.

## Pipeline

```text
CLIENT
  ↓
BRIEF + ASSETS
  ↓
REFERENCE
  ↓
REVERSE ENGINEERING
  ↓
COMPOSITION BLUEPRINT
  ↓
ART DIRECTION
  ↓
IMAGE / 3D ASSET
  ↓
FIGMA ASSEMBLY
  ↓
TYPOGRAPHY + TOKENS
  ↓
QC
  ↓
DESKTOP 1920×768
  ↓
MOBILE 1080×1920
  ↓
AVATAR / MENU / POSTS
```

## Definition of done

A cover is ready only when:

- the composition clearly follows the approved reference logic;
- every important element has a deliberate position;
- typography is readable and intentional;
- imagery has controlled scale/crop/depth;
- the result does not look like a generic AI banner;
- the important content survives VK safe-zone constraints;
- the Figma file remains editable where practical.

## Production rule

**Reference first. Style second. Decoration last.**

Do not start by selecting random colors, icons or cards. Start by mapping the geometry of the reference.

## Client project folder

```text
08_PROJECTS/
└── CLIENT_NAME/
    ├── 00_BRIEF.md
    ├── 01_REFERENCES/
    ├── 02_BLUEPRINT/
    ├── 03_ASSETS/
    ├── 04_FIGMA/
    ├── 05_EXPORTS/
    └── 06_QC.md
```
