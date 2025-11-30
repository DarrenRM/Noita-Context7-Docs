---
title: Smoke Particle 01
category: particles
---

# Smoke Particle 01

This document describes the configuration for a basic smoke particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: Specifies the texture file for the particle.
    *   `data/particles/smoke_01.png`
*   **offset\_x**: Horizontal offset for the sprite's origin.
    *   `8`
*   **offset\_y**: Vertical offset for the sprite's origin.
    *   `8`
*   **default\_animation**: The name of the animation to play by default.
    *   `smoke`

## Animation Definition

The `RectAnimation` element defines the specific animation frames and timing.

### Key Attributes:

*   **name**: The identifier for this animation.
    *   `smoke`
*   **pos\_x**: X-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   `0`
*   **pos\_y**: Y-coordinate of the top-left corner of the animation frames within the sprite sheet.
    *   `0`
*   **frame\_count**: The total number of frames in the animation.
    *   `6`
*   **frame\_width**: The width of each individual animation frame.
    *   `16`
*   **frame\_height**: The height of each individual animation frame.
    *   `16`
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.09`
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
    *   `8`
*   **loop**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`