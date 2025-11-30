---
title: Boss Wizard Helmet Sprite Animations
category: entities
---

# Boss Wizard Helmet Sprite Animations

This document details the sprite animations for the Boss Wizard's helmet entity in Noita. It focuses on the key attributes of the `<Sprite>` and `<RectAnimation>` elements, which are crucial for defining visual behavior.

## Sprite Element

The root element defining the sprite's appearance and base properties.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_wizard/wizard_helmet.png` - The path to the sprite image file.
*   **offset\_x**: `40` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `56` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the entity is spawned.

## RectAnimation Elements

These elements define individual animations, including their frame data, timing, and events.

### General Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **pos\_x**: The X-coordinate of the animation's starting frame on the sprite sheet.
*   **pos\_y**: The Y-coordinate of the animation's starting frame on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **loop**: `0` indicates the animation plays once, `1` (or omitted) indicates it loops.

### Specific Animations and Key Events:

Here's a breakdown of notable animations and their associated events:

| Animation Name   | Frame Count | Frame Wait | Loop | Key Events