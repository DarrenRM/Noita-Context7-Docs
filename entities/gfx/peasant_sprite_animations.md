---
title: Peasant Sprite Animations
category: entities/gfx
---

# Peasant Sprite Animations

This document details the sprite animations for the "Peasant" entity in Noita, as defined in `peasant.xml`. It focuses on key attributes for AI-assisted modding, such as animation names, frame counts, and timings.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/peasant.png` - The texture file for the peasant sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `6.5` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played by default when the entity is idle.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation.

### Animation Attributes:

*   **name**: The identifier for the animation (e.g., "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **pos\_x**: The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; otherwise, it loops.
*   **has\_offset**: `1` indicates that `offset_x` and `offset_y` are specific to this animation.
*   **shrink\_by\_one\_pixel**: `1` indicates the sprite is shrunk by one pixel, often for smoother transitions or smaller hitboxes.

### Notable Animations:

| Animation Name   | Frame Count | Frame Height | Frame Width | Frame Wait | Notes                               |
| :--------------- | :---------- | :----------- | :---------- | :--------- | :---------------------------------- |
| `walk`           | 8           | 19           | 12          | 0.082      | Includes "step" events.             |
| `stand`          | 6           | 19           | 12          | 0.2        | Default idle animation.             |
| `jump_up`        | 3           | 19           | 12          | 0.082      | Includes "jump" event.              |
| `jump_fall`      | 2           | 19           | 12          | 0.082      |                                     |
| `land`           | 4           | 19           | 12          | 0.082      | Includes "land" event.              |
| `sleep`          | 2           | 19           | 17          | 1.5        | Slow animation.                     |
| `attack`         | 4           | 20           | 15          | 0.09       | `shrink_by_one_pixel="1"`.          |
| `attack_ranged`  | 5           | 20           | 19          | 0.12       | `has_offset="1"`, `shrink_by_one_pixel="1"`. |
| `run`            | 8           | 20           | 13          | 0.07       | `shrink_by_one_pixel="1"`.          |
| `dig_hor`        | 6           | 19           | 17          | 0.095      | Horizontal digging animation.       |
| `dig_down`       | 6           | 20           | 18          | 0.095      | Vertical digging animation.         |
| `dig_up`         | 6           | 20           | 16          | 0.095      | Vertical digging animation.         |
| `mine`           | 5           | 20           | 18          | 0.1        | `has_offset="1"`, `shrink_by_one_pixel="1"`. |

### Animation Events

Some animations include `<Event>` tags, which trigger specific game actions at certain frames.

*   **name**: The name of the event (e.g., "step", "jump", "land").
*   **frame**: The frame number at which the event occurs.
*   **check\_physics\_material**: `1` indicates the event checks the physics material of the ground.
*   **probability**: The chance of the event occurring (usually `1` for guaranteed events).
*   **max\_distance**: Maximum distance for the event to trigger.
*   **on\_finished**: `0` means the event does not stop the animation.

**Example Event (from `walk` animation):**

```xml
<Event 
  check_physics_material="1" 
  frame="2" 
  max_distance="500" 
  name="step" 
  on_finished="0" 
  probability="1" >
</Event>
```
This event triggers a "step" sound/effect on frame 2 of the "walk" animation.