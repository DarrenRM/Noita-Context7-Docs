---
title: Boss Centipede Tail Segment (Green)
category: entities
---

# Boss Centipede Tail Segment (Green)

This documentation describes the `tail_2_green.xml` entity, representing a green tail segment of the boss centipede in Noita.

## Sprite

The sprite definition for this entity.

```xml
<Sprite
filename="data/entities/animals/boss_centipede/tail/tail_big_green.png"
offset_x="0"
offset_y="0"
default_animation="stand" >
```

### Animations

Defines the visual animations for the sprite.

```xml
	<RectAnimation
		name="stand"
		pos_x="0"
		pos_y="0"
		frame_count="1"
		frame_width="42"
		frame_height="41"
		frame_wait="1"
		frames_per_row="8"
		loop="1"   >
	</RectAnimation>
```

*   **`filename`**: Path to the sprite texture.
*   **`default_animation`**: The animation to play by default.
*   **`RectAnimation`**:
    *   **`name`**: The name of the animation (e.g., "stand").
    *   **`frame_count`**: Total number of frames in the animation.
    *   **`frame_width`**: Width of each animation frame.
    *   **`frame_height`**: Height of each animation frame.
    *   **`frame_wait`**: Time in frames to wait before advancing to the next frame.
    *   **`frames_per_row`**: Number of frames arranged horizontally in the sprite sheet.
    *   **`loop`**: Whether the animation should loop (1 for true, 0 for false).