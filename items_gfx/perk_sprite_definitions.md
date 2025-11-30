---
title: Perk Sprite Definitions
category: items_gfx
---

# Perk Sprite Definitions

This document details the sprite definitions for perks in Noita, as found in `data/items_gfx/perk.xml`. These definitions are crucial for how perk icons are rendered in the game.

## Sprite Element

The primary element is `<Sprite>`, which defines the image file and its positioning.

### Key Attributes:

*   `filename`: The path to the sprite image file (e.g., `data/items_gfx/perk.png`).
*   `offset_x`: Horizontal offset for the sprite's origin.
*   `offset_y`: Vertical offset for the sprite's origin.

## RectAnimation Element

Nested within `<Sprite>`, the `<RectAnimation>` element defines how frames within the sprite sheet are used.

### Key Attributes:

*   `name`: The name of the animation (e.g., "default").
*   `pos_x`: Starting X position of the animation frame within the sprite sheet.
*   `pos_y`: Starting Y position of the animation frame within the sprite sheet.
*   `frame_count`: The total number of frames in the animation.
*   `frame_width`: The width of each individual frame.
*   `frame_height`: The height of each individual frame.
*   `frame_wait`: The duration (in seconds) each frame is displayed.
*   `frames_per_row`: The number of frames arranged horizontally in the sprite sheet.
*   `loop`: Whether the animation should loop (0 for no, 1 for yes).

---

**Example Snippet:**

```xml
<Sprite 
	filename="data/items_gfx/perk.png" 
	offset_x="8" 
	offset_y="8" 
	>
	
  <RectAnimation 
	name="default" 
	pos_x="0" 
	pos_y="0" 
	frame_count="1" 
	frame_width="16" 
	frame_height="16" 
	frame_wait="0.2" 
	frames_per_row="10" 
	loop="0"  >
  </RectAnimation>
  
</Sprite>
```