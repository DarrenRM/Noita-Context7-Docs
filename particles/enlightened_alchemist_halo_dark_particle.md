---
title: Enlightened Alchemist Halo Dark Particle
category: guides
---

<Sprite
	filename="data/particles/enlightened_alchemist_halo_dark.png"
	offset_x="21"
	offset_y="44"
	default_animation="stand"
	>
	
	<RectAnimation
		name="stand"
		pos_x="0"
		pos_y="0"
		frame_count="1"
		frame_width="42"
		frame_height="38"
		frame_wait="0.04"
		frames_per_row="1"
		loop="1"
		>
	</RectAnimation>
</Sprite>
```

---
title: Enlightened Alchemist Halo Dark Particle
category: particles
---

# Enlightened Alchemist Halo Dark Particle

This documentation describes the `enlightened_alchemist_halo_dark.xml` particle file, which defines the visual appearance and animation of a dark halo effect, likely associated with the "Enlightened Alchemist" entity in Noita.

## Sprite

The primary visual component of the particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/enlightened_alchemist_halo_dark.png`
    *   Specifies the image file used for the particle's texture.
*   **`offset_x`**: `21`
    *   Horizontal offset of the sprite's origin.
*   **`offset_y`**: `44`
    *   Vertical offset of the sprite's origin.
*   **`default_animation`**: `stand`
    *   The name of the animation to play by default.

## RectAnimation

This tag defines a rectangular animation sequence for the sprite.

### Key Attributes:

*   **`name`**: `stand`
    *   The identifier for this specific animation.
*   **`pos_x`**: `0`
    *   The starting X position within the sprite sheet for this animation.
*   **`pos_y`**: `0`
    *   The starting Y position within the sprite sheet for this animation.
*   **`frame_count`**: `1`
    *   The total number of frames in this animation.
*   **`frame_width`**: `42`
    *   The width of each individual frame.
*   **`frame_height`**: `38`
    *   The height of each individual frame.
*   **`frame_wait`**: `0.04`
    *   The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `1`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1`
    *   Indicates whether the animation should loop (1 for true, 0 for false).