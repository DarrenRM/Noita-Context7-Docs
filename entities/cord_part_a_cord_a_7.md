---
title: Cord Part A (cord_a_7)
category: entities
---

# Cord Part A (cord_a_7)

This document describes the `cord_a_7.xml` entity, which defines a segment of a cord in Noita. This entity is part of theverlet chain system, used for creating flexible, chain-like structures.

## Sprite Information

The `Sprite` element defines the visual representation of the cord part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/cords/cord_parts/cord_a.png` - The texture file used for this sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

### Animation: `stand`

This `RectAnimation` defines the static appearance of the cord part.

#### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos\_x**: `28` - The X-coordinate of the top-left corner of the sprite frame within the texture.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the sprite frame within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of a single animation frame.
*   **frame\_height**: `3` - The height of a single animation frame.
*   **frame\_wait**: `1` - The duration each frame is displayed before advancing (in game ticks).
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).

```xml
<Sprite
filename="data/entities/verlet_chains/cords/cord_parts/cord_a.png"
offset_x="0"
offset_y="0"
default_animation="stand" >

<!-- animation -->
	<RectAnimation
		name="stand"
		pos_x="28"
		pos_y="0"
		frame_count="1"
		frame_width="4"
		frame_height="3"
		frame_wait="1"
		frames_per_row="8"
		loop="1"   >
	</RectAnimation>
</Sprite>
```