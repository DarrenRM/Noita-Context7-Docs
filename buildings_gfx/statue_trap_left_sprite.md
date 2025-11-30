---
title: Statue Trap Left Sprite
category: data/buildings_gfx
---

# Statue Trap Left Sprite

This documentation describes the sprite definition for the `statue_trap_left` building graphic in Noita.

## Sprite Definition

The primary sprite for this building is defined by the `<Sprite>` tag.

### Key Attributes

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite image file.                  |
| `offset_x`    | Horizontal offset of the sprite.                |
| `offset_y`    | Vertical offset of the sprite.                  |
| `default_animation` | The name of the default animation to play. |

```xml
<Sprite
 filename="data/buildings_gfx/statue_trap_left.png"
 offset_x="10"
 offset_y="19"
 default_animation="default" >
```

## Animation Definition

The sprite utilizes a single animation named "default".

### Key Attributes

| Attribute        | Description                                       |
|------------------|---------------------------------------------------|
| `name`           | The name of the animation.                        |
| `pos_x`          | Starting X position of the animation frame.       |
| `pos_y`          | Starting Y position of the animation frame.       |
| `frame_count`    | Total number of frames in the animation.          |
| `frame_width`    | Width of each individual animation frame.         |
| `frame_height`   | Height of each individual animation frame.        |
| `frame_wait`     | Time in seconds to wait between frames.           |
| `frames_per_row` | Number of frames arranged horizontally in the sprite sheet. |
| `loop`           | Whether the animation should loop (1 for yes, 0 for no). |

```xml
 <!-- animation -->
 <RectAnimation
  name="default"
  pos_x="0"
  pos_y="0"
  frame_count="1"
  frame_width="20"
  frame_height="20"
  frame_wait="0.12"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>
```