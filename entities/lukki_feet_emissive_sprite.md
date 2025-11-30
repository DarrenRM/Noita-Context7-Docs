---
title: Lukki Feet Emissive Sprite
category: entities
---

# Lukki Feet Emissive Sprite

This document describes the emissive sprite used for the Lukki's feet in Noita.

## Sprite Attributes

The `<Sprite>` element defines the visual representation of the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/lukki/lukki_feet/lukki_sprite_emissive.png` - The path to the sprite image file.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `10` - Vertical offset for the sprite.

## Animation: `stand`

The `<RectAnimation>` element defines the animation for the sprite.

### Key Attributes:

*   **name**: `stand` - The name of this animation state.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `20` - The width of each individual frame.
*   **frame\_height**: `20` - The height of each individual frame.
*   **frame\_wait**: `0.14` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).

```xml
<Sprite 
	filename="data/entities/animals/lukki/lukki_feet/lukki_sprite_emissive.png" 
	offset_x="10" 
	offset_y="10" >
	
  <RectAnimation 
	name="stand" 
	pos_x="0" 
	pos_y="0" 
	frame_count="1" 
	frame_width="20" 
	frame_height="20" 
	frame_wait="0.14" 
	frames_per_row="1" 
	loop="1"  >
  </RectAnimation>
  
</Sprite>
```