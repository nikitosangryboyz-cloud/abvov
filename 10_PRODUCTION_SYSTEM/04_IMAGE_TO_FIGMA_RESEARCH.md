# Image → Figma Research Workflow

## Purpose

Use image-to-Figma/open-source research as a reference for reconstructing visual layouts, not as an assumption that every raster image can be perfectly converted into semantic Figma layers.

## What we want from the workflow

Given a reference image, identify and recreate:

- large text blocks;
- simple geometric shapes;
- cards/badges;
- logos when supplied separately;
- image frames;
- decorative vectors when recognizable;
- approximate layer order.

## What should remain separate

Photographic content should normally be treated as an image asset rather than falsely reconstructed as hundreds of vector shapes.

## Fallback strategy

If automatic image-to-Figma conversion is unavailable or inaccurate:

1. Use the reference only for measurement.
2. Create the Composition Blueprint manually.
3. Generate/source the new hero image separately.
4. Rebuild typography natively in Figma.
5. Rebuild simple shapes natively.
6. Keep complex photography/3D as a single placed image.
7. Compare the Figma result with the blueprint.

## Layer confidence

Every reconstructed element can be classified:

- **HIGH** — text/shape can be recreated exactly as a native layer.
- **MEDIUM** — position/size can be recreated, visual appearance approximated.
- **LOW** — complex texture/photo/3D should remain raster.

## Reference reconstruction principle

The goal is not pixel-for-pixel tracing. The goal is an editable design whose **geometry, hierarchy and visual relationships** reproduce the reference logic.

## Integration with our system

```text
REFERENCE IMAGE
      ↓
ELEMENT DETECTION
      ↓
COMPOSITION BLUEPRINT
      ↓
CONFIDENCE CLASSIFICATION
      ↓
NATIVE FIGMA LAYERS + IMAGE ASSETS
      ↓
TYPOGRAPHY TOKENS
      ↓
VISUAL QC
```

## Important limitation

Open-source image-to-Figma projects are treated as research components. They must not override our measured Composition Blueprint or produce generic auto-layout substitutions.
