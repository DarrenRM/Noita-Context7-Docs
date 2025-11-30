---
title: Verlet Chain Segment 2 Sprite
category: entities
---

# Verlet Chain Segment 2 Sprite

This document describes the sprite data for the second segment of the Verlet chain used by the boss centipede in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation for this entity segment.

### Key Attributes

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/verlet_piece_2.png` - Specifies the texture file for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation: `stand`

This section details the `stand` animation for the sprite.

### Key Attributes

*   **name**: `"stand"` - The name of the animation.
*   **pos\_x**: `0` - X-coordinate for the animation frame.
*   **pos\_y**: `0` - Y-coordinate for the animation frame.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `7` - The width of each animation frame in pixels.
*   **frame\_height**: `7` - The height of each animation frame in pixels.
*   **frame\_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

```xml
<Sprite
filename="data/entities/animals/boss_centipede/verlet_chains/verlet_piece_2.png"
offset_x="0"
offset_y="0"
default_animation="stand" >

<!-- animation -->
	<RectAnimation
		name="stand"
		pos_x="0"
		pos_y="0"
		frame_count="1"
		frame_width="7"
		frame_height="7"
		frame_wait="1"
		frames_per_row="8"
		loop="1"   >
	</RectAnimation>
</Sprite>
```