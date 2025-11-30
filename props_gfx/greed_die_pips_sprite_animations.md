---
title: Greed Die Pips Sprite Animations
category: props_gfx
---

# Greed Die Pips Sprite Animations

This document describes the sprite animations for the "greed_die_pips" asset, used for visual effects related to greed dice.

## Sprite Definition

The main sprite definition points to the texture file and defines the default animation.

```xml
<Sprite
 filename="data/props_gfx/greed_die_pips.png"
 offset_x="8"
 offset_y="8" 
 default_animation="default">
```

*   **filename**: Path to the sprite texture.
*   **offset\_x**, **offset\_y**: Offset applied to the sprite's position.
*   **default\_animation**: The animation to play by default.

## Animations

The `greed_die_pips.png` texture contains multiple animations defined by `RectAnimation` elements. Each animation represents a different visual state or action.

### `default` Animation

This is the base animation, likely for a static or idle state.

```xml
<RectAnimation
 name="default"
 pos_x="0"
 pos_y="0"
 frame_count="1"
 frame_width="16"
 frame_height="16"
 frame_wait="0.1"
 frames_per_row="8"
 loop="1">
</RectAnimation>
```

*   **name**: "default"
*   **pos\_x**, **pos\_y**: Starting position of the animation frames within the texture.
*   **frame\_count**: Number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Time in seconds between frames.
*   **frames\_per\_row**: How many frames are arranged horizontally in the texture.
*   **loop**: Whether the animation should loop (1 for yes, 0 for no).

### `roll` Animation

This animation likely depicts the rolling of the greed die.

```xml
<RectAnimation
 name="roll"
 pos_x="0"
 pos_y="0"
 frame_count="8"
 frame_width="16"
 frame_height="16"
 frame_wait="0.04"
 frames_per_row="8"
 loop="1">
</RectAnimation>
```

*   **name**: "roll"
*   **frame\_count**: 8 frames.
*   **frame\_wait**: Shorter wait time (0.04s) for a faster, rolling effect.

### `rolled_X` Animations (X = 1 to 6)

These animations represent the different outcomes of a greed die roll, from 1 to 6. Each animation uses a single frame from the sprite sheet.

| Animation Name | `pos_x` | `frame_count` | `frame_wait` | Description                               |
| :------------- | :------ | :------------ | :----------- | :---------------------------------------- |
| `rolled_1`     | 0       | 1             | 0.1          | Represents a roll of 1.                   |
| `rolled_2`     | 16      | 1             | 0.1          | Represents a roll of 2.                   |
| `rolled_3`     | 32      | 1             | 0.1          | Represents a roll of 3.                   |
| `rolled_4`     | 48      | 1             | 0.1          | Represents a roll of 4.                   |
| `rolled_5`     | 64      | 1             | 0.1          | Represents a roll of 5.                   |
| `rolled_6`     | 80      | 1             | 0.1          | Represents a roll of 6.                   |

### `rolled_bad` and `rolled_good` Animations

These animations represent special outcomes, likely a "bad" or "good" result from a greed die roll.

```xml
<RectAnimation
 name="rolled_bad"
 pos_x="96"
 pos_y="0"
 frame_count="1"
 frame_width="16"
 frame_height="16"
 frame_wait="0.1"
 frames_per_row="8"
 loop="1">
</RectAnimation>

<RectAnimation
 name="rolled_good"
 pos_x="112"
 pos_y="0"
 frame_count="1"
 frame_width="16"
 frame_height="16"
 frame_wait="0.1"
 frames_per_row="8"
 loop="1">
</RectAnimation>
```

*   **`rolled_bad`**: Uses the frame at `pos_x="96"`.
*   **`rolled_good`**: Uses the frame at `pos_x="112"`.