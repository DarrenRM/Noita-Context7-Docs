---
title: Boss Centipede Long Limb A (Green)
category: entities
---

# Boss Centipede Long Limb A (Green)

This document describes the `limb_long_a_green.xml` entity, which represents a segment of the boss centipede's body.

## Sprite

The sprite definition for this limb segment.

```xml
<Sprite 
	filename="data/entities/animals/boss_centipede/limbs/limb_long_A_green.png" 
	offset_x="0" 
	offset_y="8" 
	>
```

### Sprite Attributes

*   **filename**: Specifies the texture file for the limb segment.
*   **offset\_x**: Horizontal offset of the sprite.
*   **offset\_y**: Vertical offset of the sprite.

### RectAnimation

Defines the animation for the sprite.

```xml
  <RectAnimation 
	name="stand" 
	pos_x="0" 
	pos_y="0" 
	frame_count="8" 
	frame_width="80" 
	frame_height="16" 
	frame_wait="0.17" 
	frames_per_row="8" 
	loop="1"  >
  </RectAnimation>
```

#### RectAnimation Attributes

*   **name**: The name of the animation state ("stand" in this case).
*   **pos\_x**, **pos\_y**: Starting position of the animation frames within the sprite sheet.
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual animation frame.
*   **frame\_wait**: Time in seconds to wait between frames.
*   **frames\_per\_row**: Number of frames arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (1 for true, 0 for false).