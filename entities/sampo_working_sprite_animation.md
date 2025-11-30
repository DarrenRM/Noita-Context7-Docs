---
title: Sampo Working Sprite Animation
category: entities
---

---

# Sampo Working Sprite Animation

This document describes the sprite animation for the "Sampo Working" entity in Noita, likely related to a boss centipede.

## Sprite Definition

The primary sprite definition for this entity is as follows:

```xml
<Sprite 
	filename="data/entities/animals/boss_centipede/sampo_working.png" 
	offset_x="12" 
	offset_y="12" 
	default_animation="default"
	>
	
	<RectAnimation
		name="default"
		pos_x="0"
		pos_y="0"
		frame_count="8"
		frame_width="24"
		frame_height="24"
		frame_wait="0.06"
		frames_per_row="8"
		loop="1"
		>
	</RectAnimation>
</Sprite>
```

### Key Attributes:

*   **`filename`**: `data/entities/animals/boss_centipede/sampo_working.png` - Specifies the image file used for the sprite.
*   **`offset_x`**: `12` - Horizontal offset of the sprite.
*   **`offset_y`**: `12` - Vertical offset of the sprite.
*   **`default_animation`**: `default` - The name of the animation to play by default.

## RectAnimation: "default"

This section details the parameters for the "default" rectangular animation.

### Key Attributes:

*   **`name`**: `default` - The identifier for this animation.
*   **`pos_x`**: `0` - The starting X position within the sprite sheet for the animation frames.
*   **`pos_y`**: `0` - The starting Y position within the sprite sheet for the animation frames.
*   **`frame_count`**: `8` - The total number of frames in this animation.
*   **`frame_width`**: `24` - The width of each individual animation frame.
*   **`frame_height`**: `24` - The height of each individual animation frame.
*   **`frame_wait`**: `0.06` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1` - Indicates that the animation should loop (1 for true, 0 for false).