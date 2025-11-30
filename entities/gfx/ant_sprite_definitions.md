---
title: Ant Sprite Definitions
category: entities/gfx
---

# Ant Sprite Definitions

This document details the sprite definitions for the Ant enemy in Noita, focusing on its visual animations and associated events.

## Sprite Attributes

The main `<Sprite>` tag defines the overall visual properties of the Ant.

| Attribute      | Value | Description                                                                 |
|----------------|-------|-----------------------------------------------------------------------------|
| `filename`     | `data/enemies_gfx/ant.png` | Path to the sprite sheet containing all animations.                         |
| `name`         | `""`  | This attribute is empty, typically used for unique entity identification.   |
| `default_animation` | `stand` | The animation to play by default when the entity is idle.                   |
| `offset_x`     | `8`   | Horizontal offset for the sprite's origin.                                  |
| `offset_y`     | `18`  | Vertical offset for the sprite's origin.                                    |
| `scale_x`      | `1`   | Horizontal scaling factor for the sprite.                                   |
| `scale_y`      | `1`   | Vertical scaling factor for the sprite.                                     |

## Animations

The Ant has several distinct animations, each defined by a `<RectAnimation>` tag. These animations are arranged in a sprite sheet, and their positions and frame data are specified within these tags.

### `stand` Animation

*   **Description:** The idle animation for the Ant.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 6.
*   **Frame Wait:** 0.12 seconds per frame.
*   **Looping:** Enabled (`loop="1"`).
*   **Sprite Sheet Position:** Top section of the sprite sheet.

### `walk` Animation

*   **Description:** The animation for when the Ant is walking.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 6.
*   **Frame Wait:** 0.12 seconds per frame.
*   **Looping:** Enabled (`loop="1"`).
*   **Sprite Sheet Position:** Second section of the sprite sheet.
*   **Events:**
    *   `step` event triggered on frame 1 and frame 4.

### `run` Animation

*   **Description:** A faster movement animation for the Ant.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 6.
*   **Frame Wait:** 0.1 seconds per frame.
*   **Looping:** Enabled (`loop="1"`).
*   **Sprite Sheet Position:** Third section of the sprite sheet.
*   **Events:**
    *   `step` event triggered on frame 1 and frame 4.

### `burn` Animation

*   **Description:** Animation played when the Ant is on fire.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 6.
*   **Frame Wait:** 0.085 seconds per frame.
*   **Looping:** Enabled (`loop="1"`).
*   **Sprite Sheet Position:** Fourth section of the sprite sheet.
*   **Events:**
    *   `step` event triggered on frame 1 and frame 4.

### `jump_up` Animation

*   **Description:** Animation for the Ant jumping upwards.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 3.
*   **Frame Wait:** 0.1 seconds per frame.
*   **Looping:** Disabled (`loop="0"`).
*   **Sprite Sheet Position:** Fifth section of the sprite sheet.
*   **Events:**
    *   `jump` event triggered on frame 0.

### `jump_fall` Animation

*   **Description:** Animation for the Ant falling after a jump.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 2.
*   **Frame Wait:** 0.1 seconds per frame.
*   **Looping:** Disabled (`loop="0"`).
*   **Sprite Sheet Position:** Sixth section of the sprite sheet.

### `land` Animation

*   **Description:** Animation played when the Ant lands.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 3.
*   **Frame Wait:** 0.1 seconds per frame.
*   **Looping:** Disabled (`loop="0"`).
*   **Sprite Sheet Position:** Seventh section of the sprite sheet.
*   **Shrink by one pixel:** Enabled (`shrink_by_one_pixel="1"`), which might slightly alter the sprite's bounding box on this frame.

### `attack` Animation

*   **Description:** Animation for the Ant's melee attack.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 6.
*   **Frame Wait:** 0.08 seconds per frame.
*   **Looping:** Disabled (`loop="0"`).
*   **Sprite Sheet Position:** Eighth section of the sprite sheet.
*   **Events:**
    *   `attack_melee` event triggered on frame 3.

### `attack_ranged` Animation

*   **Description:** Animation for the Ant's ranged attack (spitting).
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 5.
*   **Frame Wait:** 0.09 seconds per frame.
*   **Looping:** Disabled (`loop="0"`).
*   **Sprite Sheet Position:** Ninth section of the sprite sheet.
*   **Events:**
    *   `attack_spit_large` event triggered on frame 2.

### `hurt` Animation

*   **Description:** Animation played when the Ant takes damage.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 3.
*   **Frame Wait:** 0.105 seconds per frame.
*   **Looping:** Disabled (`loop="0"`).
*   **Sprite Sheet Position:** Tenth section of the sprite sheet.

### `alert` Animation

*   **Description:** Animation played when the Ant becomes alerted or notices the player.
*   **Frame Dimensions:** 24x24 pixels.
*   **Frames per Row:** 6.
*   **Frame Count:** 5.
*   **Frame Wait:** 0.04 seconds per frame.
*   **Looping:** Disabled (`loop="0"`).
*   **Sprite Sheet Position:** Eleventh section of the sprite sheet.
*   **Events:**
    *   `alert` event triggered on frame 1 and frame 3 with a probability of 0.6.

## Animation Events

Events within animations are used to trigger specific game actions or effects at certain frames.

| Event Name       | Trigger Frame | Description