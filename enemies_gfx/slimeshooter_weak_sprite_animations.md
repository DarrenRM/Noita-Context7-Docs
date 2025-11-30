---
title: Slimeshooter Weak Sprite Animations
category: enemies_gfx
---

# Slimeshooter Weak Sprite Animations

This document details the sprite animations for the "slimeshooter_weak" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/slimeshooter_weak.png"
 offset_x="8"
 offset_y="16"
 default_animation="stand" >
```

*   **`filename`**: Path to the sprite sheet.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its entity origin.
*   **`default_animation`**: The animation to play when no other animation is specified.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Stand Animation

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "stand" - The identifier for this animation.
*   **`pos_x`**, **`pos_y`**: The top-left corner of the animation frames within the sprite sheet.
*   **`frame_count`**: Number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Time in seconds between frames.
*   **`frames_per_row`**: How many frames are laid out horizontally in the sprite sheet.
*   **`loop`**: `1` for looping, `0` for non-looping.

### Walk Animation

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   Identical to `stand` in this configuration, suggesting a static "walk" pose or that movement is handled by other means.

### Run Animation

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   Copied from `walk`. Similar to `walk`, this implies the visual representation of running might be the same as walking or handled externally.

### Burn Animation

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   Copied from `walk`. This animation is used when the enemy is burning.

### Attack Animation

```xml
<RectAnimation
 name="attack"
 pos_x="0"
 pos_y="24"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.07"
 frames_per_row="6"
 loop="0" >
 <Event frame="0" name="bite" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **`pos_y="24"`**: This animation uses frames from a different row in the sprite sheet.
*   **`frame_wait="0.07"`**: Faster frame rate for attack.
*   **`loop="0"`**: This animation plays once.
*   **`<Event>`**:
    *   `frame="0"`: Triggered on the first frame.
    *   `name="bite"`: The event name, likely triggering a melee attack action.

### Attack Ranged Animation

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="24"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.07"
 frames_per_row="6"
 loop="0" >
 <Event frame="2" name="shoot_slime" probability="1" check_physics_material="0"/>
 <Event frame="0" name="voc_shoot"/>
</RectAnimation>
```

*   **`pos_y="24"`**: Shares the same sprite sheet row as `attack`.
*   **`frame_wait="0.07"`**: Faster frame rate.
*   **`loop="0"`**: Plays once.
*   **`<Event>`**:
    *   `frame="2"`: Triggered on the third frame.
    *   `name="shoot_slime"`: Likely triggers the projectile firing action.
    *   `frame="0"`: Triggered on the first frame.
    *   `name="voc_shoot"`: Likely triggers a sound effect for shooting.

### Fly Idle Animation

```xml
<RectAnimation
 name="fly_idle"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   Uses the same sprite sheet row as `stand` and `walk`.

### Fly Move Animation

```xml
<RectAnimation
 name="fly_move"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   Uses the same sprite sheet row as `stand` and `walk`.