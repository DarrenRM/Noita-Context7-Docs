---
title: Acid Shooter Sprite Animations
category: enemies_gfx
---

# Acid Shooter Sprite Animations

This document details the sprite animations for the Acid Shooter enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/acidshooter.png"
 offset_x="8"
 offset_y="12"
 default_animation="stand"
>
```

*   **`filename`**: Path to the sprite sheet.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: The animation to play when no other is specified.

## Animation Definitions

The `<RectAnimation>` tags define individual animations.

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

*   **`name`**: Identifier for the animation.
*   **`pos_x`**, **`pos_y`**: Starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: Total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: How many frames are in a single row of the sprite sheet.
*   **`loop`**: `1` for looping, `0` for one-time playback.

### Walk Animation

Defines the movement animation.

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

*   Shares most attributes with `stand`, indicating similar visual movement.

### Run Animation

A copy of the walk animation, suggesting no distinct visual difference for running.

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

A copy of the walk animation, indicating the same visual representation when burning.

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

Defines the animation for a close-range attack.

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
*   **`frame_wait="0.07"`**: Faster animation for attacks.
*   **`loop="0"`**: Plays only once.
*   **`<Event>`**: Triggers an action.
    *   **`frame="2"`**: The event occurs on the 3rd frame (0-indexed).
    *   **`name="bite"`**: The name of the event (likely an internal game trigger).
    *   **`probability="1"`**: The event is guaranteed to trigger.
    *   **`check_physics_material="0"`**: Does not check physics material for this event.

### Attack Ranged Animation

Defines the animation for a ranged attack (spitting).

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

*   **`pos_y="24"`**: Shares the same sprite sheet offset as the melee attack.
*   **`frame_wait="0.07"`**: Fast animation.
*   **`loop="0"`**: Plays only once.
*   **`<Event>`**:
    *   **`name="spit_slime"`**: The event name, indicating the projectile type.
    *   **`check_physics_material="1"`**: Checks physics material for this event, potentially influencing projectile behavior.