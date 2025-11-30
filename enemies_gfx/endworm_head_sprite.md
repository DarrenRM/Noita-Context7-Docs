---
title: Endworm Head Sprite
category: enemies_gfx
---

# Endworm Head Sprite

This document details the sprite definition for the Endworm's head in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The primary sprite for the endworm head is defined by the `<Sprite>` tag.

### Key Attributes

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite image file.                  |
| `offset_x`    | Horizontal offset for sprite positioning.       |
| `offset_y`    | Vertical offset for sprite positioning.         |
| `default_animation` | The animation to play by default.           |

```xml
<Sprite 
	filename="data/enemies_gfx/endworm_head.png" 
	offset_x="16" 
	offset_y="16"
  default_animation="stand" >
  
  <!-- Animations defined below -->
  
</Sprite>
```

## Animations

The sprite supports multiple animations, defined using `<RectAnimation>` tags.

### `stand` Animation

This animation represents the default standing state of the endworm head.

| Attribute        | Description                                     |
|------------------|-------------------------------------------------|
| `name`           | The name of the animation.                      |
| `pos_x`          | Starting X position within the sprite sheet.    |
| `pos_y`          | Starting Y position within the sprite sheet.    |
| `frame_count`    | Total number of frames in the animation.        |
| `frame_width`    | Width of each individual frame.                 |
| `frame_height`   | Height of each individual frame.                |
| `frame_wait`     | Time in seconds to wait between frames.         |
| `frames_per_row` | Number of frames in a single row of the sheet.  |
| `loop`           | Whether the animation should loop (1 for yes).  |

```xml
	<RectAnimation 
		name="stand" 
		pos_x="0" 
		pos_y="0" 
		frame_count="1" 
		frame_width="32" 
		frame_height="32" 
		frame_wait="0.082" 
		frames_per_row="1" 
		loop="1"  >
	</RectAnimation>
```

### `eat` Animation

This animation likely represents the endworm head performing an eating action.

| Attribute        | Description                                     |
|------------------|-------------------------------------------------|
| `name`           | The name of the animation.                      |
| `pos_x`          | Starting X position within the sprite sheet.    |
| `pos_y`          | Starting Y position within the sprite sheet.    |
| `frame_count`    | Total number of frames in the animation.        |
| `frame_width`    | Width of each individual frame.                 |
| `frame_height`   | Height of each individual frame.                |
| `frame_wait`     | Time in seconds to wait between frames.         |
| `frames_per_row` | Number of frames in a single row of the sheet.  |
| `loop`           | Whether the animation should loop (1 for yes).  |

```xml
	<RectAnimation 
		name="eat" 
		pos_x="0" 
		pos_y="0" 
		frame_count="1" 
		frame_width="32" 
		frame_height="32" 
		frame_wait="0.082" 
		frames_per_row="1" 
		loop="1"  >
	</RectAnimation>
```