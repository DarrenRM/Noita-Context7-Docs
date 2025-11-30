---
title: Coward Enemy Sprite Animations
category: enemies_gfx
---

---

# Coward Enemy Sprite Animations

This document details the sprite animations for the "Coward" enemy in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/coward.png"
 offset_x="8"
 offset_y="16"
 default_animation="stand" >
```

*   **`filename`**: Path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: The animation that plays when the enemy is first spawned or idle.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### `stand` Animation

The default idle animation.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="16"
 frame_height="22"
 frame_wait="0.2"
 frames_per_row="12"
 loop="1" >
</RectAnimation>
```

*   **`name`**: Identifier for the animation.
*   **`pos_x`**, **`pos_y`**: Starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: Total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: How many frames are present horizontally on the sprite sheet.
*   **`loop`**: `1` for looping, `0` for non-looping.

### `walk` Animation

The animation for when the enemy is moving.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="22"
 frame_count="6"
 frame_width="16"
 frame_height="22"
 frame_wait="0.082"
 frames_per_row="12"
 loop="1" >
 <Event frame="2" name="step" probability="1" check_physics_material="1"/>
 <Event frame="5" name="step" probability="1" check_physics_material="1"/>
</RectAnimation>
```

*   **`pos_y`**: This animation starts on the second row of frames (y=22).
*   **`frame_wait`**: Faster frame rate than `stand`.
*   **`Event`**: Triggers an action at a specific frame.
    *   `name="step"`: Likely plays a footstep sound.
    *   `check_physics_material="1"`: The event only triggers if the enemy is standing on a valid physics material.

### `run` Animation

A duplicate of the `walk` animation, suggesting it's not visually distinct.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="22"
 frame_count="6"
 frame_width="16"
 frame_height="22"
 frame_wait="0.082"
 frames_per_row="12"
 loop="1" >
 <Event frame="2" name="step" probability="1" check_physics_material="1"/>
 <Event frame="5" name="step" probability="1" check_physics_material="1"/>
</RectAnimation>
```

### `burn` Animation

A duplicate of the `walk` animation with a slightly faster `frame_wait`.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="22"
 frame_count="6"
 frame_width="16"
 frame_height="22"
 frame_wait="0.06"
 frames_per_row="12"
 loop="1" >
 <Event frame="2" name="step" probability="1" check_physics_material="1"/>
 <Event frame="5" name="step" probability="1" check_physics_material="1"/>
</RectAnimation>
```

*   **`frame_wait`**: Slightly faster than `walk`, potentially indicating a more urgent movement when burning.

### `attack_ranged` Animation

The animation for performing a ranged attack.

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="88"
 frame_count="4"
 frame_width="16"
 frame_height="22"
 frame_wait="0.07"
 frames_per_row="12"
 loop="0" >
 <Event frame="1" name="shoot" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **`pos_y`**: This animation starts on the fifth row of frames (y=88).
*   **`frame_count`**: Shorter animation sequence.
*   **`loop="0"`**: This animation plays only once.
*   **`Event frame="1" name="shoot"`**: Triggers the "shoot" action on the second frame. `check_physics_material="0"` means this event can trigger regardless of the ground material.

### `fly_idle` Animation

The idle animation when the enemy is hovering.

```xml
<RectAnimation
 name="fly_idle"
 pos_x="0"
 pos_y="44"
 frame_count="4"
 frame_width="16"
 frame_height="22"
 frame_wait="0.12"
 frames_per_row="12"
 loop="1" >
</RectAnimation>
```

*   **`pos_y`**: This animation starts on the third row of frames (y=44).
*   **`frame_wait`**: Slower frame rate, giving a more relaxed idle appearance.

### `fly_move` Animation

The animation for when the enemy is flying.

```xml
<RectAnimation
 name="fly_move"
 pos_x="0"
 pos_y="66"
 frame_count="4"
 frame_width="16"
 frame_height="22"
 frame_wait="0.09"
 frames_per_row="12"
 loop="1" >
</RectAnimation>
```

*   **`pos_y`**: This animation starts on the fourth row of frames (y=66).
*   **`frame_wait`**: Faster than `fly_idle`, indicating movement.