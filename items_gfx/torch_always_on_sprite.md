---
title: Torch Always On Sprite
category: items_gfx
---

# Torch Always On Sprite

This document describes the sprite data for the "torch_always_on" item in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite definition for this item is as follows:

```xml
<Sprite 
	filename="data/items_gfx/torch_always_on.png" 
	offset_x="6" 
	offset_y="3" 
	default_animation="default"
	>
</Sprite>
```

### Key Attributes:

*   **filename**: Specifies the image file used for the sprite (`data/items_gfx/torch_always_on.png`).
*   **offset_x**: Horizontal offset for the sprite's position.
*   **offset_y**: Vertical offset for the sprite's position.
*   **default_animation**: The name of the default animation to play.

## Animation: `default`

The `default` animation defines how the sprite is rendered over time.

```xml
  <RectAnimation 
	name="default" 
	pos_x="1" 
	pos_y="1" 
	offset_x="3" 
	offset_y="3" 
	has_offset="1"
	frame_count="1" 
	frame_width="12" 
	frame_height="6" 
	frame_wait="0.2" 
	frames_per_row="10" 
	loop="0"  >
  </RectAnimation>
```

### Key Attributes:

*   **name**: The identifier for this animation (`default`).
*   **pos_x**, **pos_y**: Starting position within the sprite sheet for the animation frames.
*   **offset_x**, **offset_y**: Offset applied to each frame of the animation.
*   **has_offset**: Indicates if the `offset_x` and `offset_y` attributes are active.
*   **frame_count**: The total number of frames in this animation (1 in this case, indicating a static sprite).
*   **frame_width**, **frame_height**: Dimensions of each individual frame.
*   **frame_wait**: Duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (`0` means no loop).