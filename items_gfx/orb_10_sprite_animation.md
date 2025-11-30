---
title: Orb 10 Sprite Animation
category: items_gfx
---

```

# Orb 10 Sprite Animation

This document describes the sprite and animation data for Orb 10, a graphical asset used in Noita.

## Sprite Definition

The primary sprite definition for Orb 10 is as follows:

```xml
<Sprite 
	filename="data/items_gfx/orbs/orb_10.png" 
	offset_x="20" 
	offset_y="48"
	default_animation="default"
	>
	
	<!-- Animation details are nested within -->
</Sprite>
```

### Key Sprite Attributes:

*   **filename**: Specifies the path to the sprite image file (`data/items_gfx/orbs/orb_10.png`).
*   **offset\_x**: Horizontal offset for the sprite's origin.
*   **offset\_y**: Vertical offset for the sprite's origin.
*   **default\_animation**: The name of the animation to play by default.

## Default Animation: "default"

The "default" animation defines how the sprite cycles through its frames.

```xml
	<RectAnimation
		name="default"
		pos_x="0"
		pos_y="0"
		frame_count="7"
		frame_width="40"
		frame_height="50"
		frame_wait="0.12"
		frames_per_row="7"
		loop="1"
		>
  </RectAnimation>
```

### Key Animation Attributes:

*   **name**: The identifier for this animation ("default").
*   **pos\_x**: Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation (7).
*   **frame\_width**: The width of each individual frame (40 pixels).
*   **frame\_height**: The height of each individual frame (50 pixels).
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing (0.12 seconds).
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet (7).
*   **loop**: Indicates if the animation should loop (1 for true, 0 for false).