---
title: Background Cleaner Sprite
category: projectiles_gfx
---

# Background Cleaner Sprite

This documentation describes the sprite used for the "background cleaner" projectile in Noita. It defines the visual appearance and animation of this projectile.

## Sprite Definition

The main sprite definition for the background cleaner.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/background_cleaner.png` - The path to the image file containing the sprite frames.
*   **offset_x**: `4` - Horizontal offset for the sprite's origin.
*   **offset_y**: `4` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation to play by default.

```xml
<Sprite
 filename="data/projectiles_gfx/background_cleaner.png"
 offset_x="4"
 offset_y="4"
 default_animation="fireball" >
</Sprite>
```

## Animation Definition

Defines the "fireball" animation used by the background cleaner sprite.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `8` - The width of each individual animation frame.
*   **frame_height**: `8` - The height of each individual animation frame.
*   **frame_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

```xml
<!-- animation -->
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="8"
 frame_height="8"
 frame_wait="0.05"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```