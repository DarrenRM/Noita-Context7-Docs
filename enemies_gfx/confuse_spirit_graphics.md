---
title: Confuse Spirit Graphics
category: data/enemies_gfx
---

# Confuse Spirit Graphics

This document details the graphical assets for the Confuse Spirit enemy in Noita, focusing on its sprite sheet and animations.

## Sprite Definition

The main sprite definition for the Confuse Spirit.

```xml
<Sprite
 filename="data/enemies_gfx/confusespirit.png"
 offset_x="9"
 offset_y="9"
 default_animation="stand"
>
```

### Key Attributes:

*   **filename**: Specifies the path to the sprite sheet image.
*   **offset\_x**, **offset\_y**: Defines the sprite's pivot point relative to its center.
*   **default\_animation**: Sets the animation to play when the sprite is first loaded.

## Animations

The Confuse Spirit utilizes several `RectAnimation` elements to define its visual states. All animations share the same frame dimensions and timing, suggesting they are variations of the same core animation sequence.

### Stand Animation

The default idle animation.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="18"
 frame_height="18"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1"
>
</RectAnimation>
```

### Walk Animation

The animation for when the Confuse Spirit is walking.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="18"
 frame_height="18"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1"
>
</RectAnimation>
```

### Run Animation

A copy of the walk animation, likely intended for faster movement.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="18"
 frame_height="18"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1"
>
</RectAnimation>
```

### Burn Animation

A copy of the walk animation, used when the Confuse Spirit is on fire.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="18"
 frame_height="18"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1"
>
</RectAnimation>
```

### Animation Attributes:

*   **name**: The identifier for the animation state.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should repeat (`1` for true, `0` for false).