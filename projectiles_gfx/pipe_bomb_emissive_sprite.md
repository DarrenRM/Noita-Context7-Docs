---
title: Pipe Bomb Emissive Sprite
category: projectiles_gfx
---

---

# Pipe Bomb Emissive Sprite

This document describes the sprite data for the emissive texture of the pipe bomb projectile in Noita.

## Sprite Definition

The main `<Sprite>` element defines the base texture and its default animation.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/pipe_bomb_emissive.png` - The path to the sprite texture file.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite.
*   **offset\_y**: `4.5` - Vertical offset for the sprite.
*   **default\_animation**: `fireball` - The animation to play by default.

## Animations

The sprite can have multiple animations defined, allowing for different visual states.

### `fireball` Animation

This animation likely represents the active, in-flight state of the pipe bomb.

#### Key Attributes:

*   **name**: `fireball`
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `6` - The total number of frames in this animation.
*   **frame\_width**: `9` - The width of each individual frame.
*   **frame\_height**: `9` - The height of each individual frame.
*   **frame\_wait**: `1000` - The delay between frames in milliseconds (1 second).
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop.

### `on_ground` Animation

This animation likely represents the state when the pipe bomb is on the ground.

#### Key Attributes:

*   **name**: `on_ground`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `1` - This animation consists of a single frame.
*   **frame\_width**: `9`
*   **frame\_height**: `9`
*   **frame\_wait**: `0.02` - A very short delay, suggesting a quick transition or static display.
*   **frames\_per\_row**: `6`
*   **loop**: `0` - Indicates that the animation should not loop.