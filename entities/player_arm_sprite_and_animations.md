---
title: Player Arm Sprite and Animations
category: entities
---

---

# Player Arm Sprite and Animations

This document details the sprite and animation data for the player's arm in Noita, as defined in `player_arm.xml`. This file specifies the visual assets and their associated animations, crucial for rendering the player's arm in various states.

## Sprite Definition

The main `<Sprite>` tag defines the core visual properties of the player's arm.

### Key Attributes:

*   **`filename`**: The path to the primary sprite image file (`data/enemies_gfx/player_arm.png`).
*   **`hotspots_filename`**: The path to the image file defining collision or interaction points (`data/enemies_gfx/player_arm_hotspots.png`).
*   **`offset_x`**: Horizontal offset for the sprite's position.
*   **`offset_y`**: Vertical offset for the sprite's position.
*   **`default_animation`**: The name of the animation to play by default.

## Hotspots

Hotspots define specific points of interest within the sprite, often used for collision detection or interaction.

### Defined Hotspots:

*   **`hand`**:
    *   **`color`**: `00ff0000` (Represents a specific color channel, likely for internal use).

## Animations

The `<RectAnimation>` tags define different animation sequences for the player's arm. Each animation is a rectangular region within the sprite sheet.

### Key Attributes for Animations:

*   **`name`**: The identifier for the animation (e.g., "default", "down", "without_item").
*   **`pos_x`**: The X-coordinate of the animation's starting position within the sprite sheet.
*   **`pos_y`**: The Y-coordinate of the animation's starting position within the sprite sheet.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: Indicates if the animation should loop (`1` for true, `0` for false).

### Defined Animations:

| Name           | `pos_x` | `pos_y` | `frame_count` | `frame_width` | `frame_height` | `frame_wait` | `frames_per_row` | `loop` |
| :------------- | :------ | :------ | :------------ | :------------ | :------------- | :----------- | :--------------- | :----- |
| `default`      | 0       | 0       | 1             | 5             | 5              | 0.2          | 8                | 1      |
| `down`         | 0       | 0       | 1             | 5             | 5              | 0.2          | 8                | 1      |
| `without_item` | 0       | 10      | 1             | 5             | 5              | 0.2          | 8                | 1      |

**Note:** All listed animations have a `frame_count` of 1, indicating they are static frames. The `pos_y` attribute differentiates the "without\_item" animation from the others.