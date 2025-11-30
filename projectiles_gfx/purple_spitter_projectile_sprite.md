---
title: Purple Spitter Projectile Sprite
category: projectiles_gfx
---

---

# Purple Spitter Projectile Sprite

This documentation describes the sprite and animation data for the "purple spitter" projectile in Noita.

## Sprite Definition

The primary sprite definition for the projectile.

```xml
<Sprite
 filename="data/projectiles_gfx/spitter_purple.png"
 offset_x="6"
 offset_y="6"
 default_animation="fireball" >
</Sprite>
```

### Key Attributes:

*   **filename**: The path to the sprite image file.
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.
*   **default\_animation**: The name of the animation to play by default.

## Animation: `fireball`

Defines the animation sequence for the projectile.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="7"
 frame_width="12"
 frame_height="12"
 frame_wait="0.09"
 frames_per_row="7"
 loop="0"
>
</RectAnimation>
```

### Key Attributes:

*   **name**: The identifier for this animation.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (0 for no, 1 for yes).