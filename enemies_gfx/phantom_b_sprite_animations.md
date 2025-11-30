---
title: Phantom B Sprite Animations
category: data/enemies_gfx
---

# Phantom B Sprite Animations

This document details the sprite animations for the "Phantom B" enemy in Noita, as defined in its XML configuration file. It focuses on the key attributes of each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offsets.

### Key Attributes:

*   **filename**: `data/enemies_gfx/phantom_b.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `19` - Vertical offset of the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation States

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation state for the enemy.

### Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **shrink\_by\_one\_pixel**: A boolean (1 or 0) indicating if frames should be shrunk by one pixel.
*   **loop**: A boolean (1 or 0) indicating if the animation should loop.

### Defined Animations:

| Name           | Frame Count | Frame Height | Frame Width | Frames Per Row | Frame Wait | Pos X | Pos Y | Loop | Shrink |
| :------------- | :---------- | :----------- | :---------- | :------------- | :--------- | :---- | :---- | :--- | :----- |
| stand          | 6           | 23           | 17          | 8              | 0.12       | 0     | 1     | 1    | 1      |
| walk           | 4           | 23           | 17          | 8              | 0.1        | 0     | 24    | 1    | 1      |
| run            | 4           | 23           | 17          | 8              | 0.1        | 0     | 24    | 1    | 1      |
| burn           | 4           | 23           | 17          | 8              | 0.1        | 0     | 24    | 1    | 1      |
| fly\_idle      | 4           | 23           | 17          | 8              | 0.09       | 0     | 47    | 1    | 1      |
| fly\_move      | 4           | 23           | 17          | 8              | 0.09       | 0     | 47    | 1    | 1      |
| attack\_ranged | 7           | 23           | 17          | 8              | 0.09       | 0     | 70    | 0    | 1      |
| attack         | 5           | 23           | 25          | 8              | 0.09       | 0     | 93    | 0    | 1      |

---

### Special Animation Events

Some animations can trigger events at specific frames.

#### `attack_ranged` Animation Events:

*   **Event Name**: `shoot_magic`
    *   **Trigger Frame**: `4`
    *   **Conditions**:
        *   `probability="1"` (Always triggers)
        *   `on_finished="0"` (Does not wait for animation to finish)
        *   `max_distance="500"`
        *   `check_physics_material="0"`

This event is associated with the ranged attack animation and likely triggers the projectile firing mechanism.