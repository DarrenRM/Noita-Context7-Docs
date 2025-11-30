---
title: Assassin Sprite Animations
category: data/enemies_gfx
---

# Assassin Sprite Animations

This document details the sprite animations for the Assassin enemy in Noita, as defined in its `assassin.xml` file. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/assassin.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite.
*   **offset\_y**: `8` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of each individual frame.
*   **frame\_height**: Height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the top-left corner of the animation frames on the sprite sheet.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates frames are shrunk by one pixel, often for visual adjustments.

### Key Animations:

| Animation Name | Frame Count | Frame Wait | Frames Per Row | Loop | Notes                               |
| :------------- | :---------- | :--------- | :------------- | :--- | :---------------------------------- |
| `stand`        | 6           | 0.1        | 6              | Yes  | Idle animation.                     |
| `walk`         | 6           | 0.085      | 6              | Yes  | Movement animation.                 |
| `run`          | 6           | 0.085      | 6              | Yes  | Faster movement animation.          |
| `burn`         | 6           | 0.085      | 6              | Yes  | Animation when burning.             |
| `jump_up`      | 2           | 0.1        | 6              | No   | Ascending jump animation.           |
| `jump_fall`    | 2           | 0.1        | 6              | No   | Descending jump animation.          |
| `land`         | 3           | 0.1        | 6              | No   | Landing animation.                  |
| `attack`       | 5           | 0.08       | 6              | No   | Melee attack animation.             |
| `hurt`         | 2           | 0.12       | 6              | No   | Taking damage animation.            |
| `attack_dash`  | 15          | 0.055      | 15             | No   | Dash attack animation.              |
| `fly_idle`     | 4           | 0.09       | 15             | Yes  | Idle animation while flying.        |
| `fly_move`     | 4           | 0.09       | 15             | Yes  | Movement animation while flying.    |

## Animation Events

`<Event>` tags within `<RectAnimation>` define specific actions or triggers at certain frames.

### Common Attributes:

*   **name**: The name of the event (e.g., "step", "attack\_melee", "dash").
*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **probability**: Likelihood of the event triggering (usually 1).
*   **on\_finished**: `0` means the event does not stop the animation.
*   **check\_physics\_material**: `1` means the event checks the material of the ground/surface.
*   **max\_distance**: Maximum distance for certain events (e.g., step sounds).

### Notable Events:

*   **`step`**: Triggered during `walk`, `run`, and `burn` animations. Likely plays footstep sounds.
*   **`attack_melee`**: Triggered during the `attack` animation.
*   **`land`**: Triggered during the `land` animation.
*   **`attack_dash`**: Triggered during the `jump_up` animation, initiating a dash.
*   **`dash`**: Triggered during the `attack_dash` animation, representing the actual dash action.