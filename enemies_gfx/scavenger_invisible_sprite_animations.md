---
title: Scavenger Invisible Sprite Animations
category: data/enemies_gfx/
---

---

# Scavenger Invisible Sprite Animations

This document details the sprite animations for the "Scavenger Invisible" enemy in Noita, as defined in the `scavenger_invis.xml` file. This file specifies the visual frames and timing for various actions the enemy performs.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its general properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/scavenger_invis.png` - The path to the sprite sheet containing all animation frames.
*   **offset\_x**: `7` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **pos\_x**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: The number of frames that fit horizontally in a single row of the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping animations.

### Defined Animations:

| Animation Name   | Description        | Frame Count | Frame Width | Frame Height | Frame Wait | Loop | Y-Position | Events