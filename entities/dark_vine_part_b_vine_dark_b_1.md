---
title: Dark Vine Part B (vine_dark_b_1)
category: entities
---

# Dark Vine Part B (vine_dark_b_1)

This entity defines a single segment of a dark vine, specifically the "B" variant. It's a visual component used in Noita's verlet chain system for creating vine-like structures.

## Sprite Information

The sprite defines the visual appearance of this vine segment.

```xml
<Sprite
filename="data/entities/verlet_chains/vines/vine_parts/vine_dark_b.png"
offset_x="0"
offset_y="0"
default_animation="stand" >
```

*   **filename**: Specifies the texture file used for the sprite.
*   **offset\_x**, **offset\_y**: Define the sprite's pivot point.
*   **default\_animation**: Sets the initial animation to play.

### Animations

This section details the available animations for the sprite.

```xml
<!-- animation -->
	<RectAnimation
		name="stand"
		pos_x="0"
		pos_y="0"
		frame_count="1"
		frame_width="4"
		frame_height="3"
		frame_wait="1"
		frames_per_row="8"
		loop="1"   >
	</RectAnimation>
```

*   **name**: The identifier for the animation ("stand" in this case).
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Delay between frames in game ticks.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (1 for yes, 0 for no).