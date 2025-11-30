---
title: Wraith Sprite Animations
category: data/enemies_gfx
---

# Wraith Sprite Animations

This document details the sprite animations for the Wraith enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The core sprite definition for the Wraith.

```xml
<Sprite
 filename="data/enemies_gfx/wraith.png"
 offset_x="12"
 offset_y="12"
 default_animation="stand" >
```

### Key Attributes:

*   **filename**: The path to the sprite sheet image.
*   **offset\_x**, **offset\_y**: Adjustments to the sprite's position relative to its origin.
*   **default\_animation**: The animation that plays when the entity is first spawned or idle.

## Animation Definitions

The Wraith utilizes several `RectAnimation` elements to define its visual states.

### `stand` Animation

The default idle animation for the Wraith.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="24"
 frame_height="28"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

### `walk` Animation

The animation for when the Wraith is moving.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="24"
 frame_height="28"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

### `run` Animation

The animation for when the Wraith is running. This is currently a copy of the `walk` animation.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="24"
 frame_height="28"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

### `burn` Animation

The animation for when the Wraith is burning. This is currently a copy of the `walk` animation.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="24"
 frame_height="28"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

### `fly_idle` Animation

The idle animation when the Wraith is flying.

```xml
<RectAnimation
 name="fly_idle"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="24"
 frame_height="28"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

### `fly_move` Animation

The movement animation when the Wraith is flying.

```xml
<RectAnimation
 name="fly_move"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="24"
 frame_height="28"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

### Key `RectAnimation` Attributes:

*   **name**: The identifier for the animation state (e.g., "stand", "walk").
*   **pos\_x**, **pos\_y**: The starting coordinates of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **loop**: Whether the animation should repeat (`1` for true, `0` for false).

**Note:** For modding purposes, observe that `run` and `burn` animations are currently identical to `walk`. Modifying these could introduce distinct visual behaviors for these states. The `fly_idle` and `fly_move` animations also share the same frame data, suggesting potential for visual differentiation.