---
title: Wizard Head Sprite Animations
category: entities
---

# Wizard Head Sprite Animations

This document details the sprite animations for the "Wizard Head" entity in Noita, focusing on key attributes for modding.

## Sprite Definition

The primary sprite for the Wizard Head is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_wizard/wizard_head.png` - The texture file used for the sprite.
*   **offset\_x**: `40` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `56` - Vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation.

### Common Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: The X-coordinate of the animation's starting frame on the sprite sheet.
*   **pos\_y**: The Y-coordinate of the animation's starting frame on the sprite sheet.
*   **loop**: `0` indicates the animation plays only once; omitted or `1` indicates looping.

### Notable Animations:

| Animation Name   | Frame Count | Frame Wait (s) | Loop | Key Events