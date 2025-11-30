---
title: Necrobot GFX Definitions
category: entities
---

---

# Necrobot GFX Definitions

This document details the graphical sprite and animation definitions for the Necrobot enemy in Noita.

## Sprite Definition

The main sprite for the Necrobot is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/necrobot.png` - Path to the primary sprite sheet.
*   **hotspots_filename**: `data/enemies_gfx/necrobot_hotspots.png` - Path to the sprite sheet defining collision/interaction points.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `22` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

### Hotspots:

Hotspots define specific points on the sprite for interactions or collision.

| Name  | Color   |
| :---- | :------ |
| hand  | `ff0000` |

## Animation Definitions

The Necrobot utilizes several `RectAnimation` definitions to represent different actions. Each animation is defined by a rectangular region within the sprite sheet.

### Animation Table:

| Name          | Frame Count | Frame Width | Frame Height | Frame Wait | Loop | Notes                               |
| :------------ | :---------- | :---------- | :----------- | :--------- | :--- | :---------------------------------- |
| `stand`       | 6           | 20          | 30           | 0.2        | 1    | Idle animation.                     |
| `walk`        | 4           | 20          | 30           | 0.082      | 1    | Walking animation.                  |
| `run`         | 4           | 20          | 30           | 0.082      | 1    | Copied from `walk`.                 |
| `burn`        | 4           | 20          | 30           | 0.06       | 1    | Burning animation.                  |
| `jump_up`     | 1           | 20          | 30           | 0.082      | 0    | Jump initiation.                    |
| `jump_fall`   | 1           | 20          | 30           | 0.082      | 0    | Falling after jump.                 |
| `attack_ranged` | 10          | 20          | 30           | 0.09       | 0    | Ranged attack animation.            |
| `fly_idle`    | 4           | 20          | 30           | 0.12       | 1    | Hovering/idle flying animation.     |
| `fly_move`    | 4           | 20          | 30           | 0.09       | 1    | Flying movement animation.          |
| `attack`      | 10          | 20          | 30           | 0.09       | 0    | Melee attack animation.             |

### Animation Details:

*   **`pos_x` / `pos_y`**: These define the starting coordinates of the animation frames within the sprite sheet. Each animation is offset vertically to create distinct sequences.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width` / `frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are present horizontally in the sprite sheet for this animation's section.
*   **`loop`**: `1` for looping animations (e.g., `stand`, `walk`), `0` for one-off animations (e.g., `attack`, `jump_up`).

### Animation Events:

Some animations include `<Event>` tags, which trigger specific game actions at certain frames.

*   **`burn` animation**:
    *   `frame="2"`: `step` event.
    *   `frame="5"`: `step` event.
*   **`jump_up` animation**:
    *   `frame="0"`: `jump` event.
*   **`attack_ranged` animation**:
    *   `frame="5"`: `shoot_bullet` event.
*   **`attack` animation**:
    *   `frame="5"`: `hit` event.

**Note**: `check_physics_material` attribute on events can influence how the event interacts with the game world.