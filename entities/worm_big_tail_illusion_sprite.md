---
title: Worm Big Tail Illusion Sprite
category: entities
---

# Worm Big Tail Illusion Sprite

This documentation describes the sprite definition for the "worm_big_tail_illusion" enemy in Noita. It details the visual assets and animations used for this entity.

## Sprite Definition

The primary sprite definition is enclosed within the `<Sprite>` tag.

### Key Attributes

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `filename`  | Path to the sprite image file.                  |
| `offset_x`  | Horizontal offset for the sprite.               |
| `offset_y`  | Vertical offset for the sprite.                 |
| `default_animation` | The animation to play by default.           |

```xml
<Sprite 
	filename="data/enemies_gfx/worm_big_tail_illusion.png" 
	offset_x="14" 
	offset_y="12" 
  default_animation="stand">
  
  <!-- Animations defined below -->
  
</Sprite>
```

## Animations

The sprite utilizes `RectAnimation` tags to define different animation sequences.

### `stand` Animation

This animation represents the default standing state of the worm's tail illusion.

#### Key Attributes

| Attribute        | Description                                     |
| :--------------- | :---------------------------------------------- |
| `name`           | The name of the animation.                      |
| `pos_x`          | Starting X position of the animation frames.    |
| `pos_y`          | Starting Y position of the animation frames.    |
| `frame_count`    | Total number of frames in the animation.        |
| `frame_width`    | Width of each individual frame.                 |
| `frame_height`   | Height of each individual frame.                |
| `frame_wait`     | Time in seconds between frames.                 |
| `frames_per_row` | Number of frames arranged horizontally in the sprite sheet. |
| `loop`           | Whether the animation should loop (1 for yes, 0 for no). |

```xml
	<RectAnimation 
		name="stand" 
		pos_x="0" 
		pos_y="0" 
		frame_count="4" 
		frame_width="28" 
		frame_height="25" 
		frame_wait="0.082" 
		frames_per_row="4" 
		loop="1"  >
	</RectAnimation>
```

### `eat` Animation

This animation defines the visual sequence for when the worm's tail illusion is eating.

#### Key Attributes

| Attribute        | Description                                     |
| :--------------- | :---------------------------------------------- |
| `name`           | The name of the animation.                      |
| `pos_x`          | Starting X position of the animation frames.    |
| `pos_y`          | Starting Y position of the animation frames.    |
| `frame_count`    | Total number of frames in the animation.        |
| `frame_width`    | Width of each individual frame.                 |
| `frame_height`   | Height of each individual frame.                |
| `frame_wait`     | Time in seconds between frames.                 |
| `frames_per_row` | Number of frames arranged horizontally in the sprite sheet. |
| `loop`           | Whether the animation should loop (1 for yes, 0 for no). |

```xml
	<RectAnimation 
		name="eat" 
		pos_x="0" 
		pos_y="0" 
		frame_count="4" 
		frame_width="28" 
		frame_height="25" 
		frame_wait="0.082" 
		frames_per_row="4" 
		loop="1"  >
	</RectAnimation>
```