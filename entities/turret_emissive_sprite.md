---
title: Turret Emissive Sprite
category: entities
---

---

# Turret Emissive Sprite

This document describes the sprite data for the "turret_emissive" enemy in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the turret.

### Key Attributes:

*   **filename**: `data/enemies_gfx/turret_emissive.png` - The path to the sprite sheet image.
*   **offset\_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `16` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The sprite sheet contains multiple animations defined by `<RectAnimation>` tags.

### `stand` Animation

This animation represents the turret in its idle or standing state.

*   **name**: `"stand"`
*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet.
*   **pos\_y**: `0` - Starting Y coordinate on the sprite sheet.
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `24` - Width of each individual frame.
*   **frame\_height**: `18` - Height of each individual frame.
*   **frame\_wait**: `0.16` - Delay between frames in seconds.
*   **frames\_per\_row**: `6` - Number of frames that fit horizontally on the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true, 0 for false).

### `attack_ranged` Animation

This animation depicts the turret performing a ranged attack.

*   **name**: `"attack_ranged"`
*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet.
*   **pos\_y**: `18` - Starting Y coordinate on the sprite sheet (below the 'stand' animation).
*   **frame\_count**: `6` - Number of frames in this animation.
*   **frame\_width**: `24` - Width of each individual frame.
*   **frame\_height**: `18` - Height of each individual frame.
*   **frame\_wait**: `0.07` - Delay between frames in seconds (faster than 'stand').
*   **frames\_per\_row**: `6` - Number of frames that fit horizontally on the sprite sheet.
*   **loop**: `0` - Indicates the animation does not loop (used for one-off actions like attacks).