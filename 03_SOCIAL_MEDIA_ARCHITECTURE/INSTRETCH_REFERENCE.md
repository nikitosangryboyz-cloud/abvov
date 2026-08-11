# InStretch — Social Media System Reference

Source repository: `Athlete23/instretch-design`

Source: https://github.com/Athlete23/instretch-design

## Purpose

This document records the useful **project architecture and asset taxonomy** found in the InStretch Design System. It is used as a structural reference for our own VK design production system.

We do **not** copy the InStretch brand identity, colors, typography, logos, imagery, or client content. We reuse the organizational idea only.

## Source project profile

The source README describes a visual identity and design-assets repository for InStretch, a women-only fitness and stretching studio in Bryansk, Russia. Its brand documentation includes identity information, colors, typography, logos, brand assets, VK assets, Instagram assets, and bot graphics.

## Useful architecture

```text
logos/
brand/
social-media/
  vk/
    covers/
    menu/
    buttons/
    highlights/
    widgets/
    service-cards/
  instagram/
  bot-graphics/
```

## VK asset taxonomy

### covers/

Dedicated VK community cover and avatar assets.

### menu/

Navigation menu tiles for the VK community.

### buttons/

CTA button variants for VK posts.

### highlights/

Visual icons for story/highlight categories such as halls, information, location, directions and reviews.

### widgets/

Visual widget assets organized by service/class type.

### service-cards/

Commercial offer cards organized by plan/product type, including trial and lead-form visuals.

## Instagram

The source project keeps Instagram highlight sets separate from VK assets. This is useful as a general rule: assets should be grouped by platform rather than mixed together.

## Brand asset architecture

The source project separates:

- logos;
- brand-level assets;
- social-media assets;
- platform-specific assets;
- commercial/service cards.

This separation should be preserved in our system.

## Adaptation for our VK Design Studio

Our production system should use the same high-level separation, but with our own content:

```text
04_BRAND_ASSETS/
  logos/
  brand-elements/

05_SOCIAL_MEDIA/
  vk/
    covers/
      desktop/
      mobile/
    avatars/
    menu/
    buttons/
    highlights/
    widgets/
    service-cards/
    post-templates/

  instagram/
    covers/
    stories/
    highlights/

06_CLIENT_ASSETS/
  photos/
  logos/
  fonts/
  references/
```

## Important production rule

The source project's strongest reusable idea is **not a particular visual style**. It is the systematic organization of a complete social-media identity into reusable asset categories.

For our workflow, every VK client project should be treated as a complete visual system rather than a single cover.

## Our production mapping

```text
CLIENT
  ↓
BRAND ASSETS
  ↓
REFERENCE ANALYSIS
  ↓
COMPOSITION BLUEPRINT
  ↓
VK DESKTOP COVER
  ↓
VK MOBILE COVER
  ↓
AVATAR
  ↓
MENU
  ↓
BUTTONS / CTA
  ↓
WIDGETS / SERVICE CARDS
  ↓
POST TEMPLATES
  ↓
QUALITY CONTROL
```

## Source-derived notes

The source README specifies a VK section containing covers, menu tiles, buttons, highlights, widgets and service cards, and an Instagram section containing highlight sets. It also keeps logos and general brand assets in separate top-level directories.

For exact source asset names and source-specific brand details, see the original repository rather than treating this document as the source of truth.
