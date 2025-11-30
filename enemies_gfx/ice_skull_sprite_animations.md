---
title: Ice Skull Sprite Animations
category: data/enemies_gfx
---

# Ice Skull Sprite Animations

This document details the sprite animations for the "Ice Skull" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/iceskull.png"
 offset_x="8"
 offset_y="13"
 default_animation="stand" >
```

*   **`filename`**: Path to the sprite sheet.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its entity.
*   **`default_animation`**: The animation to play when no other is specified.

## Animations

The following `<RectAnimation>` tags define the different states and actions of the Ice Skull.

### Stand Animation

The default idle animation.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="16"
 frame_height="16"
 frame_wait="0.13"
 frames_per_row="5"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "stand"
*   **`frame_count`**: 5 frames.
*   **`frame_width`**, **`frame_height`**: Each frame is 16x16 pixels.
*   **`frame_wait`**: 0.13 seconds per frame.
*   **`frames_per_row`**: 5 frames are laid out horizontally.
*   **`loop`**: 1 (true), meaning the animation will repeat.

### Walk Animation

The animation for when the enemy is moving.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="16"
 frame_height="16"
 frame_wait="0.11"
 frames_per_row="5"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "walk"
*   **`frame_wait`**: 0.11 seconds per frame (faster than stand).

### Run Animation

A faster movement animation.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="16"
 frame_height="16"
 frame_wait="0.09"
 frames_per_row="5"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "run"
*   **`frame_wait`**: 0.09 seconds per frame (even faster).

### Burn Animation

Animation for when the enemy is on fire.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="16"
 frame_height="16"
 frame_wait="0.09"
 frames_per_row="5"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "burn"
*   **`frame_wait`**: 0.09 seconds per frame.

### Attack Animations

These animations trigger specific actions during combat.

#### Attack (Bite)

```xml
<RectAnimation
 name="attack"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="16"
 frame_height="16"
 frame_wait="0.08"
 frames_per_row="6"
 loop="0" >
 <Event frame="1" name="attack_bite" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **`name`**: "attack"
*   **`frame_wait`**: 0.08 seconds per frame.
*   **`loop`**: 0 (false), this is a single-play animation.
*   **`Event`**: At frame 1, triggers the "attack\_bite" action.

#### Attack Ranged (Shoot)

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="16"
 frame_height="16"
 frame_wait="0.08"
 frames_per_row="6"
 loop="0" >
 <Event frame="2" name="attack_shoot" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **`name`**: "attack\_ranged"
*   **`frame_wait`**: 0.08 seconds per frame.
*   **`loop`**: 0 (false).
*   **`Event`**: At frame 2, triggers the "attack\_shoot" action.

#### Attack Dash

```xml
<RectAnimation
 name="attack_dash"
 pos_x="0"
 pos_y="0"
 frame_count="5"
 frame_width="16"
 frame_height="16"
 frame_wait="0.07"
 frames_per_row="6"
 loop="0" >
 <Event frame="0" name="attack_dash" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **`name`**: "attack\_dash"
*   **`frame_wait`**: 0.07 seconds per frame (fastest attack).
*   **`loop`**: 0 (false).
*   **`Event`**: At frame 0, triggers the "attack\_dash" action.