---
title: Boss Fish Eye Sprite
category: entities
---

# Boss Fish Eye Sprite

This document describes the sprite data for the Boss Fish's eye entity in Noita. It details the visual appearance, animations, and their properties.

## Sprite Definition

The primary `<Sprite>` tag defines the visual asset and its base properties.

```xml
<Sprite
filename="data/entities/animals/boss_fish/eye.png"
offset_x="25"
offset_y="36" 
default_animation="closed"
>
```

### Key Attributes:

*   **filename**: The path to the sprite image file.
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.
*   **default\_animation**: The animation to play by default when the entity is spawned.

## Animations

The `<Sprite>` tag contains several `<RectAnimation>` elements, each defining a distinct animation for the eye.

### `closed` Animation

This animation represents the closed state of the eye.

```xml
<RectAnimation
 name="closed"
 pos_x="0"
 pos_y="144"
 frame_count="1"
 frame_width="50"
 frame_height="72"
 frame_wait="0.09"
 frames_per_row="5"
 loop="1"
>
</RectAnimation>
```

### `opened` Animation

This animation represents the fully opened state of the eye.

```xml
<RectAnimation
 name="opened"
 pos_x="0"
 pos_y="0"
 frame_count="1"
 frame_width="50"
 frame_height="72"
 frame_wait="0.09"
 frames_per_row="5"
 loop="1"
>
</RectAnimation>
```

### `open` Animation

This animation depicts the process of the eye opening.

```xml
<RectAnimation
 name="open"
 pos_x="0"
 pos_y="72"
 frame_count="5"
 frame_width="50"
 frame_height="72"
 frame_wait="0.12"
 frames_per_row="5"
 next_animation="opened"
 loop="0"
>
</RectAnimation>
```

### `close` Animation

This animation depicts the process of the eye closing.

```xml
<RectAnimation
 name="close"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="50"
 frame_height="72"
 frame_wait="0.12"
 frames_per_row="5"
 next_animation="closed"
 loop="0"
>
</RectAnimation>
```

### Animation Attributes:

*   **name**: The identifier for the animation.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.
*   **next\_animation**: The animation to transition to after this one completes (for non-looping animations).