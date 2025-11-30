---
title: Basebot Sentry Sprite Animations
category: entities_gfx
---

# Basebot Sentry Sprite Animations

This document details the sprite animations for the Basebot Sentry enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Basebot Sentry.

```xml
<Sprite
 filename="data/enemies_gfx/basebot_sentry.png"
 offset_x="9"
 offset_y="15"
 default_animation="stand" >
</Sprite>
```

### Key Attributes:

*   **filename**: Path to the sprite texture file.
*   **offset\_x**, **offset\_y**: Adjusts the sprite's position relative to its entity's origin.
*   **default\_animation**: The animation to play when no other animation is specified.

## Animation Definitions

This section breaks down the different animations used by the Basebot Sentry.

### `stand` Animation

The default idle animation for the Sentry.

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

The animation for when the Sentry is moving.

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

This animation is a direct copy of the `walk` animation.

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

This animation is also a direct copy of the `walk` animation.

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

The animation played when the Sentry performs a melee or close-range attack.

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

#### Key Attributes:

*   **loop**: Set to `0` indicating it's a one-time animation.
*   **Event**: Triggers an action on a specific frame.
    *   **frame**: The frame number (0-indexed) at which the event occurs.
    *   **name**: The name of the event to trigger (e.g., `shoot_bullet`).
    *   **probability**: The chance of the event occurring.
    *   **check\_physics\_material**: Whether to check physics materials for the event.

### `attack_ranged` Animation

Similar to the `attack` animation, likely for ranged attacks.

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

The idle animation when the Sentry is airborne.

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

The animation for when the Sentry is flying and moving.

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

## Common `RectAnimation` Attributes

These attributes are common across most `RectAnimation` definitions and are crucial for understanding sprite behavior:

| Attribute        | Description                                                                                                |
| :--------------- | :--------------------------------------------------------------------------------------------------------- |
| **name**         | The identifier for this animation (e.g., "stand", "walk", "attack").                                       |
| **pos\_x**, **pos\_y** | The top-left corner coordinates of the animation's frame grid within the sprite sheet.                   |
| **frame\_count** | The total number of frames in this animation.                                                              |
| **frame\_width** | The width of each individual frame in pixels.                                                              |
| **frame\_height**| The height of each individual frame in pixels.                                                             |
| **frame\_wait**  | The duration (in seconds) each frame is displayed before advancing to the next.                              |
| **frames\_per\_row**| The number of frames that fit horizontally in a single row of the sprite sheet.                            |
| **loop**         | Determines if the animation repeats (`1` for loop, `0` for no loop).                                       |