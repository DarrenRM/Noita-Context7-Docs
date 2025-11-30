---
title: Ice Fireball Sprite Animations
category: projectiles_gfx
---

# Ice Fireball Sprite Animations

This document details the sprite animations for the alternative ice fireball projectile in Noita.

## Sprite Definition

The primary `<Sprite>` element defines the base image and its offsets.

### Key Attributes:

*   `default_animation`: Specifies the animation to play by default ("spawn").
*   `filename`: The path to the sprite sheet (`data/projectiles_gfx/fireball_alt_ice.png`).
*   `offset_x`: Horizontal offset of the sprite (16 pixels).
*   `offset_y`: Vertical offset of the sprite (12 pixels).

## Animations

The sprite sheet contains multiple `RectAnimation` elements, defining different animation sequences.

### `fireball` Animation

This animation represents the main visual of the fireball in flight.

#### Key Attributes:

*   `name`: "fireball"
*   `frame_count`: 4 frames.
*   `frame_width`: 33 pixels.
*   `frame_height`: 25 pixels.
*   `frames_per_row`: 4 frames per row in the sprite sheet.
*   `frame_wait`: 0.035 seconds between frames.
*   `pos_x`: Starting X position in the sprite sheet (0).
*   `pos_y`: Starting Y position in the sprite sheet (1).
*   `shrink_by_one_pixel`: 1 (indicates a slight shrinking effect).

### `spawn` Animation

This animation plays when the projectile is initially created.

#### Key Attributes:

*   `name`: "spawn"
*   `frame_count`: 4 frames.
*   `frame_width`: 32 pixels.
*   `frame_height`: 24 pixels.
*   `frames_per_row`: 4 frames per row.
*   `frame_wait`: 0.08 seconds between frames.
*   `loop`: 0 (this animation does not loop).
*   `next_animation`: "fireball" (transitions to the "fireball" animation after completion).
*   `pos_x`: Starting X position in the sprite sheet (0).
*   `pos_y`: Starting Y position in the sprite sheet (26).