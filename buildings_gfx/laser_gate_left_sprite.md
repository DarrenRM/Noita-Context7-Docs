---
title: Laser Gate Left Sprite
category: data/buildings_gfx
---

# Laser Gate Left Sprite

This document describes the sprite data for the `lasergate_left` building in Noita, focusing on its visual representation and animation.

## Sprite Definition

The primary `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/buildings_gfx/lasergate_left.png` - Specifies the texture file used for the sprite.
*   **offset_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset_y**: `4` - Vertical offset of the sprite's origin.
*   **default_animation**: `fireball` - The name of the animation that plays by default.

## Animations

The `<Sprite>` element contains one or more animation definitions.

### `fireball` Animation

This animation defines the visual sequence for the laser gate's activation.

#### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `8` - The width of each individual frame.
*   **frame_height**: `8` - The height of each individual frame.
*   **frame_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).

```xml
<Sprite 
	filename="data/buildings_gfx/lasergate_left.png" 
	offset_x="8" 
	offset_y="4" 
 default_animation="fireball" >

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
  loop="1"   >
 </RectAnimation>
</Sprite>
```