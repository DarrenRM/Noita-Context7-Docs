---
title: Basebot Hidden Sprite Animations
category: enemies_gfx
---

# Basebot Hidden Sprite Animations

This document details the sprite animations for the "Basebot Hidden" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Basebot Hidden.

```xml
<Sprite
 filename="data/enemies_gfx/basebot_hidden.png"
 offset_x="9"
 offset_y="15"
 default_animation="stand" >
```

### Key Attributes:

*   **filename**: Path to the sprite image file.
*   **offset\_x**, **offset\_y**: Adjustments to the sprite's position relative to its origin.
*   **default\_animation**: The animation that plays when no other animation is specified.

## Animations

This section breaks down the different animations defined for the Basebot Hidden.

### `stand` Animation

The default idle animation for the Basebot Hidden.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="20"
 frame_height="20"
 frame_wait="0.12"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

### `walk` Animation

The animation for when the Basebot Hidden is walking.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="20"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.09"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

### `run` Animation

A placeholder animation, currently identical to `walk`.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="20"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.09"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

### `burn` Animation

A placeholder animation, currently identical to `walk`.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="20"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.09"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

### `attack` Animation

The animation for the Basebot Hidden's attack.

```xml
<RectAnimation
 name="attack"
 pos_x="0"
 pos_y="40"
 frame_count="5"
 frame_width="20"
 frame_height="20"
 frame_wait="0.05"
 frames_per_row="8"
 loop="0" >
 <Event frame="3" name="shoot_bullet" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **Event**: Triggers an action at a specific frame.
    *   **frame**: The frame number when the event occurs.
    *   **name**: The name of the event (e.g., `shoot_bullet`).
    *   **probability**: Likelihood of the event occurring.
    *   **check\_physics\_material**: Whether physics material should be checked for the event.

### `attack_ranged` Animation

Similar to `attack`, likely for ranged attacks.

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="40"
 frame_count="5"
 frame_width="20"
 frame_height="20"
 frame_wait="0.05"
 frames_per_row="8"
 loop="0" >
 <Event frame="3" name="shoot_bullet" probability="1" check_physics_material="0"/>
</RectAnimation>
```

### `fly_idle` Animation

The idle animation when the Basebot Hidden is flying.

```xml
<RectAnimation
 name="fly_idle"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="20"
 frame_height="20"
 frame_wait="0.085"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

### `fly_move` Animation

The animation for when the Basebot Hidden is flying and moving.

```xml
<RectAnimation
 name="fly_move"
 pos_x="0"
 pos_y="20"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.07"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

## Animation Attributes Summary

| Attribute         | Description                                                                 |
| :---------------- | :-------------------------------------------------------------------------- |
| `name`            | The identifier for the animation.                                           |
| `pos_x`, `pos_y`  | The starting coordinates of the animation frames within the sprite sheet.   |
| `frame_count`     | The total number of frames in the animation.                                |
| `frame_width`     | The width of each individual frame.                                         |
| `frame_height`    | The height of each individual frame.                                        |
| `frame_wait`      | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row`  | The number of frames that fit horizontally in a single row of the sprite sheet. |
| `loop`            | Whether the animation should repeat (`1` for true, `0` for false).          |
| `Event`           | Defines actions to be triggered at specific frames within an animation.     |