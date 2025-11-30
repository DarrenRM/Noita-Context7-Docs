---
title: Small Orb Sprite
category: guides
---

<Sprite 
	filename="data/items_gfx/orbs/orb_small.png" 
	offset_x="8" 
	offset_y="8"
	default_animation="default"
	>
	
	<RectAnimation
		name="default"
		pos_x="0"
		pos_y="0"
		frame_count="6"
		frame_width="16"
		frame_height="16"
		frame_wait="0.12"
		frames_per_row="6"
		loop="1"
		>
  </RectAnimation>
</Sprite>
```

---
title: Small Orb Sprite
category: items_gfx
---

# Small Orb Sprite

This document describes the sprite definition for the small orb item in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the item.

### Key Attributes:

*   **filename**: `data/items_gfx/orbs/orb_small.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"default"` - The name of the default animation to play.

## RectAnimation Definition

The `<RectAnimation>` element defines a specific animation using a rectangular grid of frames.

### Key Attributes:

*   **name**: `"default"` - The name of this animation.
*   **pos\_x**: `"0"` - The starting X position of the animation frames within the texture.
*   **pos\_y**: `"0"` - The starting Y position of the animation frames within the texture.
*   **frame\_count**: `"6"` - The total number of frames in the animation.
*   **frame\_width**: `"16"` - The width of each individual frame in pixels.
*   **frame\_height**: `"16"` - The height of each individual frame in pixels.
*   **frame\_wait**: `"0.12"` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `"6"` - The number of frames arranged horizontally in the texture.
*   **loop**: `"1"` - Indicates whether the animation should loop (1 for true, 0 for false).