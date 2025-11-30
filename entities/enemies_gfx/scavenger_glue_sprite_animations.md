---
title: Scavenger Glue Sprite Animations
category: entities/enemies_gfx
---

# Scavenger Glue Sprite Animations

This document details the sprite animations for the "Scavenger Glue" enemy in Noita, as defined in its XML configuration file. It focuses on the key attributes of each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the base properties for the enemy's visual representation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/scavenger_glue.png` - The path to the sprite sheet image.
*   **offset\_x**: `7` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `17` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation state that plays by default.

## Animation States

The `<Sprite>` tag contains multiple `<RectAnimation>` elements, each defining a specific animation state.

### Stand Animation

*   **name**: `stand`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `8`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.12` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `1` (true, animation loops)

### Walk Animation

*   **name**: `walk`
*   **pos\_x**: `0`
*   **pos\_y**: `19`
*   **frame\_count**: `6`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.082` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `1` (true, animation loops)
*   **Events**:
    *   `step` (frame 2, probability 1, checks physics material)
    *   `step` (frame 5, probability 1, checks physics material)

### Run Animation (Copy of Walk)

*   **name**: `run`
*   **pos\_x**: `0`
*   **pos\_y**: `19`
*   **frame\_count**: `6`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.082` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `1` (true, animation loops)
*   **Events**:
    *   `step` (frame 2, probability 1, checks physics material)
    *   `step` (frame 5, probability 1, checks physics material)

### Burn Animation (Copy of Walk)

*   **name**: `burn`
*   **pos\_x**: `0`
*   **pos\_y**: `19`
*   **frame\_count**: `6`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.06` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `1` (true, animation loops)
*   **Events**:
    *   `step` (frame 2, probability 1, checks physics material)
    *   `step` (frame 5, probability 1, checks physics material)

### Attack Ranged Animation

*   **name**: `attack_ranged`
*   **pos\_x**: `0`
*   **pos\_y**: `38`
*   **frame\_count**: `10`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.07` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `0` (false, animation does not loop)

### Attack Animation

*   **name**: `attack`
*   **pos\_x**: `0`
*   **pos\_y**: `95`
*   **frame\_count**: `5`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.09` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `0` (false, animation does not loop)
*   **Events**:
    *   `attack_melee` (frame 3, probability 1, does not check physics material)
    *   `voc_attack` (frame 4, probability 1, does not check physics material)

### Fly Idle Animation

*   **name**: `fly_idle`
*   **pos\_x**: `0`
*   **pos\_y**: `57`
*   **frame\_count**: `8`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.12` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `1` (true, animation loops)

### Fly Move Animation

*   **name**: `fly_move`
*   **pos\_x**: `0`
*   **pos\_y**: `76`
*   **frame\_count**: `8`
*   **frame\_width**: `22`
*   **frame\_height**: `19`
*   **frame\_wait**: `0.09` (seconds per frame)
*   **frames\_per\_row**: `12`
*   **loop**: `1` (true, animation loops)

---
**Note**: The `jump_up` and `jump_fall` animations are commented out in the source file and are not active. The `run` and `burn` animations are direct copies of the `walk` animation, suggesting they might be placeholders or intended to share the same visual movement.