---
title: Crystal Enemy Sprite Animations
category: entities_gfx
---

# Crystal Enemy Sprite Animations

This document details the sprite animations for the Crystal enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/crystal.png` - Path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `16` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The following `<RectAnimation>` tags define the different animations available for the Crystal enemy.

### `stand` Animation

This animation represents the enemy's idle or standing state.

#### Key Attributes:

*   **name**: `"stand"`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in the animation.
*   **frame\_width**: `16` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.1` - Delay between frames in seconds.
*   **frames\_per\_row**: `8` - Number of frames in a single row of the sprite sheet.
*   **loop**: `1` - Indicates the animation loops (1 for true, 0 for false).

### `attack_ranged` Animation

This animation is used for the enemy's ranged attack.

#### Key Attributes:

*   **name**: `"attack_ranged"`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `20` - Starting Y position on the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in the animation.
*   **frame\_width**: `16` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.02` - Delay between frames in seconds (faster than `stand`).
*   **frames\_per\_row**: `8` - Number of frames in a single row of the sprite sheet.
*   **loop**: `0` - Indicates the animation does not loop.

### `attack` Animation

This animation is used for the enemy's melee or general attack.

#### Key Attributes:

*   **name**: `"attack"`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `20` - Starting Y position on the sprite sheet.
*   **frame\_count**: `8` - Total number of frames in the animation.
*   **frame\_width**: `16` - Width of each individual frame.
*   **frame\_height**: `20` - Height of each individual frame.
*   **frame\_wait**: `0.05` - Delay between frames in seconds.
*   **frames\_per\_row**: `8` - Number of frames in a single row of the sprite sheet.
*   **loop**: `0` - Indicates the animation does not loop.