---
title: Spitter Green Projectile Sprite
category: projectiles_gfx
---

# Spitter Green Projectile Sprite

This documentation describes the sprite definition for the "spitter_green" projectile in Noita.

## Sprite Definition

The primary element is `<Sprite>`, which defines the visual asset for the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/spitter_green.png` - Specifies the path to the image file containing the projectile's frames.
*   **offset_x**: `6` - The horizontal offset of the sprite from its origin.
*   **offset_y**: `6` - The vertical offset of the sprite from its origin.
*   **default_animation**: `fireball` - The name of the animation to be played by default.

```xml
<Sprite
 filename="data/projectiles_gfx/spitter_green.png"
 offset_x="6"
 offset_y="6"
 default_animation="fireball" >
</Sprite>
```

## Animation Definition

The `<RectAnimation>` element defines how the sprite frames are arranged and animated.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation, referenced by `default_animation` in the `<Sprite>` tag.
*   **pos_x**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos_y**: `0` - The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame_count**: `7` - The total number of frames in the animation.
*   **frame_width**: `12` - The width of each individual animation frame.
*   **frame_height**: `12` - The height of each individual animation frame.
*   **frame_wait**: `0.07` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `7` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop. `0` means it does not loop (plays once).

```xml
<!-- animation -->
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="7"
 frame_width="12"
 frame_height="12"
 frame_wait="0.07"
 frames_per_row="7"
 loop="0"
 >
</RectAnimation>
```