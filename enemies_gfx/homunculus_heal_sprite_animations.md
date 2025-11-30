---
title: Homunculus Heal Sprite Animations
category: data/enemies_gfx/
---

# Homunculus Heal Sprite Animations

This document details the sprite animations for the Homunculus Heal enemy in Noita, as defined in the `homunculus_heal.xml` file. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/homunculus_heal.png` - The path to the sprite sheet.
*   **default\_animation**: `stand` - The animation played when no other specific animation is triggered.
*   **offset\_x**: `6.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `10` - Vertical offset for the sprite's origin.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Animation List:

| Animation Name | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop | Pos X | Pos Y | Shrink By One Pixel |
| :------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- | :---- | :---- | :------------------ |
| `stand`        | 6           | 16          | 16           | 0.1        | 6              | N/A  | 0     | 1     | N/A                 |
| `walk`         | 6           | 16          | 16           | 0.085      | 6              | N/A  | 0     | 18    | N/A                 |
| `run`          | 6           | 16          | 16           | 0.085      | 6              | N/A  | 0     | 18    | N/A                 |
| `burn`         | 6           | 16          | 16           | 0.085      | 6              | N/A  | 0     | 18    | N/A                 |
| `fly_idle`     | 4           | 17          | 18           | 0.12       | 15             | N/A  | 0     | 35    | 1                   |
| `fly_move`     | 4           | 17          | 18           | 0.12       | 15             | N/A  | 0     | 35    | 1                   |
| `attack_ranged`| 6           | 16          | 17           | 0.04       | 6              | 0    | 0     | 53    | N/A                 |
| `attack`       | 6           | 16          | 17           | 0.04       | 6              | 0    | 0     | 53    | N/A                 |

### Key Attributes for RectAnimation:

*   **name**: The identifier for the animation (e.g., `stand`, `walk`, `attack`).
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **pos\_x**, **pos\_y**: The starting coordinates of the animation's frames within the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (e.g., for attacks). Default is assumed to loop.
*   **shrink\_by\_one\_pixel**: `1` indicates frames are shrunk by one pixel, often for flying animations.

## Animation Events

Events can be triggered at specific frames within an animation.

### `walk`, `run`, `burn` Animations:

These animations share similar event structures.

*   **Event Name**: `step`
    *   **frame**: `0` and `3` - The event triggers on these frames.
    *   **check\_physics\_material**: `1` - Checks for physics materials under the entity.
    *   **max\_distance**: `500` - Maximum distance for the physics check.
    *   **probability**: `1` - The event is guaranteed to trigger if conditions are met.
    *   **on\_finished**: `0` - The event does not affect animation completion.

### `attack_ranged` Animation:

*   **Event Name**: `shoot_magic`
    *   **frame**: `3` - The event triggers on the 4th frame (index 3).
    *   **check\_physics\_material**: `0` - Physics material check is disabled for this event.
    *   **max\_distance**: `500` - Maximum distance for the physics check (though disabled).
    *   **probability**: `1` - The event is guaranteed to trigger.
    *   **on\_finished**: `0` - The event does not affect animation completion.

### `attack` Animation:

*   **Event Name**: `shoot_melee`
    *   **frame**: `3` - The event triggers on the 4th frame (index 3).
    *   **check\_physics\_material**: `0` - Physics material check is disabled for this event.
    *   **max\_distance**: `500` - Maximum distance for the physics check (though disabled).
    *   **probability**: `1` - The event is guaranteed to trigger.
    *   **on\_finished**: `0` - The event does not affect animation completion.