---
title: Player Mine Sprite
category: projectiles_gfx
---

# Player Mine Sprite

This document describes the sprite and animations for the player's mine projectile in Noita.

## Sprite Definition

The main sprite for the player mine is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/mine_player.png` - Specifies the texture file used for the sprite.
*   **offset_x**: `6.5` - Horizontal offset for the sprite's origin.
*   **offset_y**: `11` - Vertical offset for the sprite's origin.
*   **default_animation**: `stand` - The animation that plays by default when the projectile is active.

## Animations

The player mine has two primary animations: `stand` and `detonate`.

### `stand` Animation

This animation represents the mine in its idle or active state before detonation.

*   **name**: `stand`
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `13` - Width of each frame in pixels.
*   **frame\_height**: `14` - Height of each frame in pixels.
*   **frame\_wait**: `0.16` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop.

### `detonate` Animation

This animation plays when the mine is about to detonate.

*   **name**: `detonate`
*   **frame\_count**: `8` - Number of frames in this animation.
*   **frame\_width**: `13` - Width of each frame in pixels.
*   **frame\_height**: `14` - Height of each frame in pixels.
*   **frame\_wait**: `0.09` - Time in seconds to wait between frames.
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates that the animation should loop.

#### Events within `detonate` Animation:

The `detonate` animation includes specific events triggered at certain frames.

*   **frame="0"**: Triggers a `beep` event.
*   **frame="2"**: Triggers a `beep` event.
*   **frame="3"**: Triggers a `beep` event.
*   **frame="4"**: Triggers a `beep` event.

Each `beep` event has a `probability="1"`, meaning it will always occur when that frame is reached. `check_physics_material="0"` indicates that the event does not depend on the physics material of the projectile.