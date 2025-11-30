---
title: Boss Alchemist Sprite Definitions
category: entities
---

# Boss Alchemist Sprite Definitions

This document details the sprite and animation configurations for the Boss Alchemist entity in Noita. It outlines the visual assets and how they are animated for various actions.

## Sprite Configuration

The main `<Sprite>` tag defines the base image file and its default animation.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_alchemist/boss_alchemist.png` - The primary image file for the Boss Alchemist.
*   **offset\_x**: `32` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `56` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is idle.

## Animation Definitions

The `<RectAnimation>` tags define specific animations, including their source image region, frame timing, and associated events.

### General Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame set within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame set within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (plays once), `1` (or omitted) indicates it loops.

### Defined Animations:

| Animation Name | Frame Count | Frame Wait (s) | Y-Offset (pos\_y) | Loop | Key Events