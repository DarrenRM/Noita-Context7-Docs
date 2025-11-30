---
title: Boss Wizard Body Sprite and Animations
category: entities
---

# Boss Wizard Body Sprite and Animations

This document details the sprite and animation definitions for the Boss Wizard's body entity in Noita. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The `<Sprite>` tag defines the visual representation and animation data for the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_wizard/wizard_body.png` - Path to the sprite texture.
*   **hotspots\_filename**: `data/entities/animals/boss_wizard/wizard_hotspots.png` - Path to the sprite texture containing hotspot definitions.
*   **offset\_x**: `40` - Horizontal offset for the sprite.
*   **offset\_y**: `56` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Hotspots:

Hotspots define specific points on the sprite used for gameplay mechanics.

*   **hand**: Green hotspot (`00ff00`), likely used for melee attacks or interactions.
*   **shoot\_pos**: Red hotspot (`ff0000`), indicates the origin point for ranged attacks.

## Animations

The `<RectAnimation>` tags define individual animations, specifying frame data and timing.

### Common Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of a single frame.
*   **frame\_height**: Height of a single frame.
*   **frames\_per\_row**: Number of frames in each row of the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**, **pos\_y**: Offset within the sprite sheet for this animation's frames.
*   **loop**: `0` indicates the animation does not loop.

### Defined Animations:

| Animation Name | Frame Count | Frame Wait (s) | Loop | Notes                               |
| :------------- | :---------- | :------------- | :--- | :---------------------------------- |
| `stand`        | 6           | 0.14           | Yes  | Idle animation.                     |
| `walk`         | 6           | 0.12           | Yes  | Walking animation.                  |
| `run`          | 6           | 0.1            | Yes  | Running animation.                  |
| `burn`         | 6           | 0.09           | Yes  | Burning animation.                  |
| `fly_idle`     | 6           | 0.11           | Yes  | Flying idle animation.              |
| `fly_move`     | 6           | 0.09           | Yes  | Flying movement animation.          |
| `attack`       | 6           | 0.06           | No   | Melee attack animation.             |
| `attack_ranged`| 18          | 0.05           | No   | Primary ranged attack animation.    |
| `attack_ranged2`| 11          | 0.06           | No   | Secondary ranged attack animation.  |

### Animation Events:

Events are triggered at specific frames within an animation.

*   **attack**:
    *   Frame `7`: Triggers `attack_melee` event.
*   **attack\_ranged**:
    *   Frame `11`: Triggers `attack_shoot` event.
*   **attack\_ranged2**:
    *   Frame `7`: Triggers `attack_shoot` event.

**Event Attributes:**

*   **frame**: The frame number at which the event occurs.
*   **name**: The name of the event to trigger (e.g., `attack_melee`, `attack_shoot`).
*   **max\_distance**: Maximum distance for the event to be considered (e.g., for ranged attacks).
*   **on\_finished**: `0` indicates the event does not wait for animation completion.
*   **probability**: `1` means the event will always trigger if conditions are met.