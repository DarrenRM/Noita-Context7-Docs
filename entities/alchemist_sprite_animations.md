---
title: Alchemist Sprite Animations
category: entities
---

# Alchemist Sprite Animations

This document details the sprite animations for the Alchemist entity in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its default animation.

### Key Attributes:

*   **filename**: `data/entities/animals/parallel/alchemist/sprite.png` - The path to the sprite sheet.
*   **offset\_x**: `32` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `56` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions (`<RectAnimation>`)

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of a single frame in pixels.
*   **frame\_height**: The height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The horizontal starting position of the animation frames on the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.

### Animation Breakdown:

| Animation Name | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Loop | Events