---
title: Hook Projectile Sprite
category: data/projectiles_gfx/
---

# Hook Projectile Sprite

This document describes the sprite and animation data for the "hook" projectile in Noita.

## Sprite Attributes

The `<Sprite>` tag defines the visual representation of the projectile.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `filename`  | Path to the sprite image file.                  |
| `offset_x`  | Horizontal offset for the sprite.               |
| `offset_y`  | Vertical offset for the sprite.                 |
| `default_animation` | The name of the animation to play by default. |

```xml
<Sprite
 filename="data/projectiles_gfx/hook.png"
 offset_x="2"
 offset_y="4.5"
 default_animation="fireball" >
</Sprite>
```

## Animation Data

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### `fireball` Animation

This animation is named "fireball" and is used as the default for the hook projectile.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `name`          | The name of this animation.                     |
| `pos_x`         | Starting X position within the sprite sheet.    |
| `pos_y`         | Starting Y position within the sprite sheet.    |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. |
| `loop`          | Whether the animation should loop (1 for yes, 0 for no). |

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="1"
 frame_width="11"
 frame_height="9"
 frame_wait="0.2"
 frames_per_row="1"
 loop="1" >
</RectAnimation>
```