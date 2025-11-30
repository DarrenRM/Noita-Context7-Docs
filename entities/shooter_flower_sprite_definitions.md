---
title: Shooter Flower Sprite Definitions
category: entities
---

# Shooter Flower Sprite Definitions

This document details the sprite and animation definitions for the Shooter Flower enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The main `Sprite` tag defines the base image and default animation for the entity.

### Key Attributes:

*   **filename**: `data/enemies_gfx/shooterflower.png` - The path to the sprite sheet.
*   **offset\_x**: `15` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `RectAnimation` tags define the different animations used by the Shooter Flower. Each animation is composed of frames from the sprite sheet.

### `stand` Animation

*   **name**: `"stand"`
*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y coordinate on the sprite sheet for this animation.
*   **frame\_count**: `4` - Total number of frames in this animation.
*   **frame\_width**: `30` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.1` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `9` - Number of frames per row on the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true, 0 for false).

### `walk` Animation

*   **name**: `"walk"`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `4`
*   **frame\_width**: `30`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `9`
*   **loop**: `1`

### `attack_ranged` Animation

This animation is specifically for the ranged attack action.

*   **name**: `"attack_ranged"`
*   **pos\_x**: `0`
*   **pos\_y**: `20` - This animation starts on a different row of the sprite sheet.
*   **frame\_count**: `9`
*   **frame\_width**: `30`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.08` - Faster frame wait for a more dynamic attack.
*   **frames\_per\_row**: `9`
*   **loop**: `0` - This animation does not loop.

#### Events for `attack_ranged`

Events trigger specific actions at certain frames within an animation.

| Frame | Name                 | Probability | Check Physics Material |
| :---- | :------------------- | :---------- | :--------------------- |
| `0`   | `attack_shoot_buildup` | `1`         | `0`                    |
| `7`   | `attack_shoot`       | `1`         | `0`                    |