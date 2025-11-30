---
title: Zombie Emissive Sprite Animations
category: data/enemies_gfx
---

# Zombie Emissive Sprite Animations

This document details the sprite animations for the "zombie_emissive" entity in Noita, focusing on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/zombie_emissive.png` - The texture file used for the sprite.
*   **offset\_x**: `8.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame block within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame block within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop; omitted or `1` (default) means it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates frames are one pixel smaller than the base `frame_width`/`frame_height`, often used for smoother transitions.

### Animation Breakdown:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Loop | Shrink | Notes                               |
| :--------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :--- | :----- | :---------------------------------- |
| `stand`          | 6           | 18          | 19           | 8              | 0.2        | 0     | 1     | Yes  | No     | Default idle animation.             |
| `walk`           | 6           | 19          | 20           | 8              | 0.082      | 0     | 21    | Yes  | Yes    | Walking animation.                  |
| `run`            | 6           | 19          | 20           | 8              | 0.075      | 0     | 41    | Yes  | Yes    | Running animation.                  |
| `burn`           | 6           | 19          | 20           | 8              | 0.075      | 0     | 41    | Yes  | Yes    | Burning animation (shares frames with run). |
| `jump_up`        | 3           | 19          | 20           | 8              | 0.082      | 0     | 61    | No   | Yes    | Ascending part of a jump.           |
| `jump_fall`      | 2           | 19          | 20           | 8              | 0.082      | 0     | 81    | No   | Yes    | Descending part of a jump.          |
| `land`           | 3           | 19          | 20           | 8              | 0.082      | 0     | 101   | No   | Yes    | Landing animation.                  |
| `attack`         | 4           | 19          | 20           | 8              | 0.075      | 0     | 121   | No   | Yes    | Attack animation.                   |
| `hurt`           | 4           | 19          | 20           | 8              | 0.07       | 0     | 141   | No   | Yes    | Taking damage animation.            |
| `knockback`      | 1           | 18          | 19           | 8              | 0.07       | 0     | 161   | Yes  | No     | Knockback reaction.                 |
| `lower_head`     | 3           | 18          | 19           | 8              | 0.12       | 0     | 181   | No   | No     | Animation for lowering the head.    |
| `eat`            | 4           | 18          | 19           | 8              | 0.18       | 0     | 201   | Yes  | No     | Eating animation.                   |
| `raise_head`     | 3           | 18          | 19           | 8              | 0.12       | 0     | 221   | No   | No     | Animation for raising the head.     |
| `alert`          | 4           | 18          | 19           | 8              | 0.06       | 0     | 241   | No   | No     | Alert/awareness animation.          |
| `swim_idle`      | 6           | 19          | 20           | 8              | 0.11       | 0     | 261   | Yes  | Yes    | Idle animation while swimming.      |
| `swim_move`      | 6           | 19          | 20           | 8              | 0.09       | 0     | 261   | Yes  | Yes    | Movement animation while swimming.  |
| `jump_prepare`   | 3           | 18          | 19           | 8              | 0.05       | 0     | 281   | No   | No     | Animation for preparing to jump.    |

## Animation Events

Some animations can trigger events at specific frames.

### `jump_prepare` Animation Events:

*   **Event Name**: `jump_start`
    *   **Trigger Frame**: `3` (the last frame of the `jump_prepare` animation)
    *   **Conditions**: `check_physics_material="0"`, `max_distance="500"`, `probability="1"`
    *   **Action**: `on_finished="0"` (indicates the event is tied to the animation finishing)

This event is likely used to initiate the actual jump physics or state change after the preparation animation completes.