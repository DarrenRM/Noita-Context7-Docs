---
title: Acid Shooter (Weak) Sprite Animations
category: enemies_gfx
---

# Acid Shooter (Weak) Sprite Animations

This document details the sprite animations for the "acidshooter_weak" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/acidshooter_weak.png"
 offset_x="8"
 offset_y="12"
 default_animation="stand"
>
```

*   **`filename`**: Path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: The animation to play when no other is specified.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Stand Animation

The default idle animation.

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
 loop="1"
>
</RectAnimation>
```

*   **`name`**: Identifier for the animation (e.g., "stand").
*   **`pos_x`**, **`pos_y`**: Top-left corner of the animation frames within the sprite sheet.
*   **`frame_count`**: Total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Time in seconds between frames.
*   **`frames_per_row`**: How many frames are laid out horizontally in the sprite sheet.
*   **`loop`**: `1` for looping, `0` for non-looping.

### Walk Animation

Similar to "stand", likely used for basic movement.

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
 loop="1"
>
</RectAnimation>
```

### Run Animation

A copy of the "walk" animation, suggesting no distinct visual difference for running in this sprite.

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
 loop="1"
>
</RectAnimation>
```

### Burn Animation

Also a copy of "walk", indicating the same visual representation when burning.

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
 loop="1"
>
</RectAnimation>
```

### Attack Animation (Melee)

Represents a close-range attack.

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
 loop="0"
>
 <Event frame="2" name="bite" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **`pos_y="24"`**: This animation uses frames starting from a different vertical offset in the sprite sheet.
*   **`frame_wait="0.07"`**: Faster animation for attack.
*   **`loop="0"`**: This animation plays only once.
*   **`<Event>`**: Triggers an action at a specific frame.
    *   `frame="2"`: The event occurs on the 3rd frame (0-indexed).
    *   `name="bite"`: The name of the event, likely triggering a melee attack sound or effect.
    *   `probability="1"`: Always triggers.
    *   `check_physics_material="0"`: Does not check physics material for this event.

### Attack Ranged Animation

Represents a ranged attack, likely spitting slime.

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
 loop="0"
>
 <Event frame="2" name="spit_slime" probability="1" check_physics_material="1"/>
</RectAnimation>
```

*   **`pos_y="24"`**: Shares the same vertical sprite sheet offset as the melee attack.
*   **`frame_wait="0.07"`**: Fast animation.
*   **`loop="0"`**: Plays once.
*   **`<Event>`**:
    *   `name="spit_slime"`: Triggers a ranged projectile (slime).
    *   `check_physics_material="1"`: This event might check the physics material of the target or environment.