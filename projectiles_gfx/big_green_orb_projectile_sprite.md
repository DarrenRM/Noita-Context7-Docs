---
title: Big Green Orb Projectile Sprite
category: projectiles_gfx
---

# Big Green Orb Projectile Sprite

This document describes the sprite and animation data for the "Big Green Orb" projectile in Noita.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/orb_green_big.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - The vertical offset of the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation that plays by default.

## Animation: `fireball`

The `<RectAnimation>` tag defines the animation sequence for the projectile.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X-coordinate within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - The starting Y-coordinate within the sprite sheet for the animation frames.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).

```xml
<Sprite
 filename="data/projectiles_gfx/orb_green_big.png"
 offset_x="8"
 offset_y="8"
 default_animation="fireball" >

 <!-- animation -->
 <RectAnimation
  name="fireball"
  pos_x="0"
  pos_y="0"
  frame_count="4"
  frame_width="16"
  frame_height="16"
  frame_wait="0.05"
  frames_per_row="4"
  loop="1"   >
 </RectAnimation>
</Sprite>
```