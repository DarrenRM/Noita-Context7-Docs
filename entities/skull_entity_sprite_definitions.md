---
title: Skull Entity Sprite Definitions
category: entities
---

# Skull Entity Sprite Definitions

This document details the sprite definitions for the "Skull" entity in Noita, focusing on its visual animations.

## Sprite

The primary sprite for the skull entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_limbs/skull.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `24` - Horizontal offset of the sprite.
*   **offset\_y**: `24` - Vertical offset of the sprite.

## Animations

The `<Sprite>` tag contains definitions for different animations.

### `stand` Animation

This animation represents the skull in a standing or idle state.

*   **name**: `stand`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `1` - Number of frames in the animation.
*   **frame\_width**: `48` - Width of each frame.
*   **frame\_height**: `48` - Height of each frame.
*   **frame\_wait**: `0.09` - Time in seconds between frames.
*   **frames\_per\_row**: `6` - Number of frames per row in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no, 1 for yes).

### `invisible` Animation

This animation defines the visual state when the skull is invisible.

*   **name**: `invisible`
*   **pos\_x**: `0`
*   **pos\_y**: `48` - This offset likely points to a different section of the sprite sheet for the invisible state.
*   **frame\_count**: `1`
*   **frame\_width**: `48`
*   **frame\_height**: `48`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `6`
*   **loop**: `1` - This animation is set to loop, suggesting a continuous effect.

### `animate` Animation

This animation is labeled as "walk" and likely represents movement or a general active state.

*   **name**: `animate`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `6` - This animation uses multiple frames to depict motion.
*   **frame\_width**: `48`
*   **frame\_height**: `48`
*   **frame\_wait**: `0.13` - Slightly longer frame wait than the `stand` animation.
*   **frames\_per\_row**: `6`
*   **loop**: `0` - This animation does not loop.