---
title: Forcefield Generator Light Sprite
category: guides
---

<Sprite
	filename="data/props_gfx/forcefield_generator_light.png"
	offset_x="0"
	offset_y="4" 
	default_animation="on">

	<RectAnimation
		name="on"
		pos_x="0"
		pos_y="0"
		frame_count="2"
		frame_width="16"
		frame_height="16"
		frame_wait="0.42"
		frames_per_row="2"
		loop="1"   >
	</RectAnimation>

</Sprite>
```

---
title: Forcefield Generator Light Sprite
category: props_gfx
---

# Forcefield Generator Light Sprite

This document describes the sprite definition for the forcefield generator's light effect in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual appearance and animation of the forcefield generator light.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/props_gfx/forcefield_generator_light.png`
*   **`offset_x`**: Horizontal offset for the sprite's position.
    *   `0`
*   **`offset_y`**: Vertical offset for the sprite's position.
    *   `4`
*   **`default_animation`**: The name of the animation to play by default.
    *   `on`

## Animation: "on"

The `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `on`
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet.
    *   `0`, `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `2`
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
    *   `16`, `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.42`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `2`
*   **`loop`**: Determines if the animation should repeat.
    *   `1` (meaning it loops)