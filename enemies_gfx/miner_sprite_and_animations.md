---
title: Miner Sprite and Animations
category: data/enemies_gfx/
---

# Miner Sprite and Animations

This document details the sprite and animation definitions for the Miner enemy in Noita, as defined in `miner.xml`.

## Sprite Definition

The main sprite for the Miner is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/miner.png` - The primary image file for the Miner's sprite.
*   **hotspots_filename**: `data/enemies_gfx/miner_hotspots.png` - The image file defining collision and interaction points.
*   **offset\_x**: `7` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default when the entity is idle.

### Hotspots:

*   **name**: `"hand"` - A defined interaction point, likely for melee attacks or item interaction.
    *   **color**: `"ff0000"` - Red color, often used for specific hotspot types.

## Animation Definitions

The Miner has various animations defined using `<RectAnimation>` tags, each describing a sequence of frames.

### Animation List:

| Animation Name   | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop | Notes                               |
| :--------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- | :---------------------------------- |
| `stand`          | 6           | 18          | 16           | 0.2        | 6              | Yes  | Idle animation.                     |
| `attack`         | 7           | 18          | 16           | 0.05       | 8              | No   | Melee attack animation.             |
| `attack_ranged`  | 7           | 18          | 16           | 0.05       | 8              | No   | Ranged attack animation.            |
| `walk`           | 6           | 18          | 16           | 0.15       | 6              | Yes  | Walking animation.                  |
| `run`            | 6           | 18          | 16           |0.15        | 8              | Yes  | Running animation.                  |
| `jump_up`        | 3           | 18          | 16           | 0.09       | 8              | No   | Jumping upwards animation.          |
| `knockback`      | 1           | 18          | 16           | 0.055      | 8              | Yes  | Knockback reaction.                 |
| `lower_head`     | 1           | 18          | 16           | 0.01       | 8              | No   | Head lowering animation.            |
| `eat`            | 6           | 18          | 16           | 0.068      | 8              | No   | Eating/consuming animation.         |
| `raise_head`     | 1           | 18          | 16           | 0.01       | 8              | No   | Head raising animation.             |
| `alert`          | 2           | 18          | 16           | 0.09       | 8              | No   | Alerted state animation.            |
| `burn`           | 6           | 18          | 16           | 0.1        | 8              | Yes  | Burning animation.                  |
| `jump_fall`      | 3           | 18          | 16           | 0.09       | 8              | No   | Falling after jump animation.       |
| `land`           | 2           | 18          | 16           | 0.08       | 8              | No   | Landing animation.                  |
| `swim_idle`      | 6           | 18          | 16           | 0.085      | 8              | Yes  | Swimming idle animation.            |
| `swim_move`      | 6           | 18          | 16           | 0.08       | 8              | Yes  | Swimming movement animation.        |
| `jump_prepare`   | 2           | 18          | 16           | 0.08       | 8              | No   | Preparing to jump animation.        |

### Key Animation Attributes:

*   **name**: The identifier for the animation (e.g., `stand`, `attack`).
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **pos\_x**, **pos\_y**: The starting coordinates of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation plays once, while `1` (or absence) means it loops.
*   **shrink\_by\_one\_pixel**: A value indicating if frames should be shrunk by one pixel, potentially for animation smoothing.

### Animation Events:

Animations can trigger specific game events at certain frames.

#### `attack` Animation Events:

*   **frame**: `4`
    *   **name**: `"attack_melee"` - Triggers a melee attack.
    *   **name**: `"voc_attack"` - Triggers a vocalized attack.

#### `attack_ranged` Animation Events:

*   **frame**: `4`
    *   **name**: `"throw"` - Triggers a ranged projectile throw.

#### `walk` Animation Events:

*   **frame**: `2`
    *   **name**: `"step"` - Triggers a footstep sound/effect.
*   **frame**: `5`
    *   **name**: `"step"` - Triggers another footstep sound/effect.

#### `run` Animation Events:

*   **frame**: `2`
    *   **name**: `"step"` - Triggers a footstep sound/effect.
*   **frame**: `5`
    *   **name**: `"step"` - Triggers another footstep sound/effect.

#### `jump_up` Animation Events:

*   **frame**: `0`
    *   **name**: `"jump"` - Triggers the jump action.

#### `eat` Animation Events:

*   **frame**: `4`
    *   **name**: `"attack_stomp"` - Triggers a stomp attack.
*   **frame**: `0`
    *   **name**: `"voc_stomp"` - Triggers a vocalized stomp.

#### `burn` Animation Events:

*   **frame**: `2`
    *   **name**: `"step"` - Triggers a footstep sound/effect.
*   **frame**: `5`
    *   **name**: `"step"` - Triggers another footstep sound/effect.

#### `swim_idle` Animation Events:

*   **frame**: `2`
    *   **name**: `"paddle"` - Triggers a swimming paddle sound/effect.
*   **frame**: `5`
    *   **name**: `"paddle"` - Triggers another swimming paddle sound/effect.

#### `swim_move` Animation Events:

*   **frame**: `2`
    *   **name**: `"paddle"` - Triggers a swimming paddle sound/effect.
*   **frame**: `5`
    *   **name**: `"paddle"` - Triggers another swimming paddle sound/effect.

#### `jump_prepare` Animation Events:

*   **frame**: `0`
    *   **name**: `"voc_jump"` - Triggers a vocalization for jumping.
*   **frame**: `2`
    *   **name**: `"jump_start"` - Triggers the start of the jump animation.

### Event Attributes:

*   **check\_physics\_material**: `0` or `1`. Determines if the event should check for specific physics materials.
*   **frame**: The specific frame number within the animation where the event occurs.
*   **max\_distance**: Maximum distance for the event to trigger (often related to AI perception).
*   **name**: The name of the event to trigger (e.g., `attack_melee`, `step`).
*   **on\_finished**: `0` or `1`. Indicates if the event should trigger when the animation finishes.
*   **probability**: The chance (0 to 1) that the event will occur.