---
title: Wasp Swarm Projectile Sprite
category: projectiles_gfx
---

---

# Wasp Swarm Projectile Sprite

This document describes the sprite and animation data for the "swarm_wasp" projectile in Noita, intended for AI-assisted modding.

## Sprite Data

The primary sprite for the wasp swarm projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/swarm_wasp.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `4.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"fly"` - The name of the animation that plays by default.

```xml
<Sprite
 filename="data/projectiles_gfx/swarm_wasp.png"
 offset_x="4.5"
 offset_y="4.5"
 default_animation="fly" >
 <!-- ... animation data ... -->
</Sprite>
```

## Animation Data

The projectile utilizes a rectangular animation for its visual movement.

### Animation: `fly`

This animation defines the frames and timing for the wasp's flight.

#### Key Attributes:

*   **name**: `"fly"` - The identifier for this animation.
*   **pos\_x**: `"0"` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `"0"` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `"4"` - The total number of frames in the animation.
*   **frame\_width**: `"9"` - The width of each individual animation frame.
*   **frame\_height**: `"9"` - The height of each individual animation frame.
*   **frame\_wait**: `"0.04"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously (1 for true, 0 for false).

```xml
 <RectAnimation
  name="fly"
  pos_x="0"
  pos_y="0"
  frame_count="4"
  frame_width="9"
  frame_height="9"
  frame_wait="0.04"
  frames_per_row="4"
  loop="1" >
 </RectAnimation>
```