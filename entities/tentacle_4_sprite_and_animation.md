---
title: Tentacle 4 Sprite and Animation
category: entities
---

# Tentacle 4 Sprite and Animation

This document describes the sprite and animation data for `tentacle_4.xml`, a tentacle entity found in the parallel dimension.

## Sprite

The primary sprite for this tentacle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/parallel/tentacles/tentacle.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

## Animation: "stand"

The `"stand"` animation defines the visual frames and timing for the tentacle's idle state.

### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `12` - X-coordinate within the sprite sheet for the animation's starting frame.
*   **pos\_y**: `0` - Y-coordinate within the sprite sheet for the animation's starting frame.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `11` - The height of each individual frame.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.

```xml
<Sprite
filename="data/entities/animals/parallel/tentacles/tentacle.png"
offset_x="0"
offset_y="0"
default_animation="stand" >

<!-- animation -->
	<RectAnimation
		name="stand"
		pos_x="12"
		pos_y="0"
		frame_count="1"
		frame_width="4"
		frame_height="11"
		frame_wait="1"
		frames_per_row="8"
		loop="1"   >
	</RectAnimation>
</Sprite>
```