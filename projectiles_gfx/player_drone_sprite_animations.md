---
title: Player Drone Sprite Animations
category: projectiles_gfx
---

# Player Drone Sprite Animations

This document details the sprite animations for the player drone projectile in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The primary sprite for the player drone is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: Specifies the path to the sprite image file.
    *   `data/projectiles_gfx/playerdrone.png`
*   **offset\_x**: Horizontal offset for the sprite.
    *   `5`
*   **offset\_y**: Vertical offset for the sprite.
    *   `5`

## RectAnimation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation state.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation state (e.g., "stand", "walk", "burn").
*   **frame\_count**: The total number of frames in the animation.
    *   `2` (for all listed animations)
*   **frame\_width**: The width of each individual frame.
    *   `10` (for all listed animations)
*   **frame\_height**: The height of each individual frame.
    *   `10` (for all listed animations)
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
    *   `0.03` (for all listed animations)
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
    *   `2` (for all listed animations)
*   **loop**: Determines if the animation should loop.
    *   `1` (meaning it loops)

### Animation States:

The following animation states are defined:

*   **stand**: Idle standing animation.
*   **walk**: Walking animation.
*   **run**: Running animation.
*   **burn**: Animation for when the drone is burning.
*   **fly\_move**: Animation for flying movement.
*   **fly\_idle**: Animation for when the drone is flying and idle.

Each of these animations uses the same frame dimensions and timing, suggesting a consistent visual style across different states.