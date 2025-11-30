---
title: Big Zombie Torso Sprite Animations
category: entities
---

# Big Zombie Torso Sprite Animations

This document details the sprite animations for the "Big Zombie Torso" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/bigzombietorso.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `20` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each frame in pixels.
*   **frame\_height**: The height of each frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The horizontal starting position of the animation frames on the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates a slight shrink effect for certain animations.

### Animation Details:

| Animation Name | Frame Count | Frame Wait | Pos Y | Loop | Key Events