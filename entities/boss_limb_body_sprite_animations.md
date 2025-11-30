---
title: Boss Limb Body Sprite Animations
category: entities
---

# Boss Limb Body Sprite Animations

This document details the sprite animations for the "boss_limbs/body.xml" entity, commonly used for boss body parts in Noita.

## Sprite Definition

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_limbs/body.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `24` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `24` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### Animation Details:

Each `<RectAnimation>` defines a sequence of frames for a specific action.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `name`           | The identifier for the animation (e.g., "stand", "open", "attack\_ranged"). |
| `pos_x`          | The starting X-coordinate of the animation frames within the sprite sheet.  |
| `pos_y`          | The starting Y-coordinate of the animation frames within the sprite sheet.  |
| `frame_count`    | The total number of frames in this animation.                               |
| `frame_width`    | The width of each individual frame in pixels.                               |
| `frame_height`   | The height of each individual frame in pixels.                              |
| `frame_wait`     | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row` | The number of frames that fit horizontally in the sprite sheet row.         |
| `loop`           | `1` for looping animations, `0` for one-time animations.                    |
| `next_animation` | (Optional) Specifies the animation to transition to after completion.       |

### Notable Animations:

*   **stand**: The default idle animation.
    *   `frame_count`: 12
    *   `frame_wait`: 0.12
*   **open**: An animation likely used to reveal something or transition to an "opened" state.
    *   `frame_count`: 6
    *   `frame_wait`: 0.09
    *   `next_animation`: "opened"
*   **opened**: A sustained "opened" state.
    *   `frame_count`: 5
    *   `frame_wait`: 0.12
    *   `loop`: 1
*   **close**: An animation to return to the "stand" state.
    *   `frame_count`: 5
    *   `frame_wait`: 0.09
    *   `next_animation`: "stand"
*   **attack\_ranged**: Animation for a ranged attack.
    *   `frame_count`: 7
    *   `frame_wait`: 0.09
*   **hurt**: Animation played when the entity takes damage.
    *   `frame_count`: 2
    *   `frame_wait`: 0.09
*   **charge**: Animation for charging an attack or ability.
    *   `frame_count`: 12
    *   `frame_wait`: 0.07
*   **death2**: A death animation.
    *   `frame_count`: 3
    *   `frame_wait`: 0.093
    *   `loop`: 1
*   **death1**: Another death animation.
    *   `frame_count`: 5
    *   `frame_wait`: 0.07
    *   `loop`: 0