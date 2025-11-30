---
title: Shine Particle Effect (shine_03)
category: guides
---

<Sprite
	filename="data/particles/shine_03.png"
	offset_x="4.5"
	offset_y="4.5"
	default_animation="explosion"
 >

	<!-- explosion -->
	<RectAnimation
		name="explosion"
		pos_x="0"
		pos_y="0"
		frame_count="16"
		frame_width="9"
		frame_height="9"
		frame_wait="0.03"
		frames_per_row="16"
		loop="0"   >
	</RectAnimation>
</Sprite>
```

---
title: Shine Particle Effect (shine_03)
category: particles
---

# Shine Particle Effect (shine_03)

This document describes the `shine_03.xml` particle effect, which is used to create a small, shimmering light effect in Noita.

## Sprite Definition

The core of the particle is defined by the `<Sprite>` element.

### Key Attributes

*   **`filename`**: Specifies the image file used for the particle's texture.
    *   `data/particles/shine_03.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `4.5`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `4.5`
*   **`default_animation`**: The name of the animation to play by default when the particle is spawned.
    *   `explosion`

## Animations

The particle can have multiple animations. In this case, only one is defined: `explosion`.

### `explosion` Animation

This animation defines how the sprite changes over time.

#### Key Attributes

*   **`name`**: The identifier for this animation.
    *   `explosion`
*   **`pos_x`**: Starting X position within the sprite sheet for the animation frames.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet for the animation frames.
    *   `0`
*   **`frame_count`**: The total number of frames in this animation.
    *   `16`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `9`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `9`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing to the next.
    *   `0.03`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `16`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping (plays once).
    *   `0`