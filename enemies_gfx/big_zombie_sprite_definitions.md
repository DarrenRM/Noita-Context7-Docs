---
title: Big Zombie Sprite Definitions
category: enemies_gfx
---

# Big Zombie Sprite Definitions

This document details the sprite definitions for the "Big Zombie" enemy in Noita, focusing on its visual animations and associated events.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and default animation for the enemy.

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `filename`    | `data/enemies_gfx/bigzombie.png`    | Path to the sprite sheet image file.                                        |
| `offset_x`    | `8`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | `20`                                | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `stand`                             | The animation to play by default when the enemy is idle.                    |

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation sequence.

### Stand Animation

*   **Name:** `stand`
*   **Frames:** 6
*   **Frame Size:** 24x24 pixels
*   **Frame Wait:** 0.2 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="1"`
*   **Description:** The idle animation for the Big Zombie.

### Walk Animation

*   **Name:** `walk`
*   **Frames:** 6
*   **Frame Size:** 24x24 pixels
*   **Frame Wait:** 0.1 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="26"`
*   **Events:**
    *   `step` event triggered on frame 0 and frame 3. This likely corresponds to footstep sounds or effects.

### Run Animation

*   **Name:** `run`
*   **Frames:** 6
*   **Frame Size:** 24x24 pixels
*   **Frame Wait:** 0.082 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="26"`
*   **Events:**
    *   `step` event triggered on frame 0 and frame 3.

### Burn Animation

*   **Name:** `burn`
*   **Frames:** 6
*   **Frame Size:** 24x24 pixels
*   **Frame Wait:** 0.06 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="26"`
*   **Events:**
    *   `step` event triggered on frame 0 and frame 3.

### Jump Up Animation

*   **Name:** `jump_up`
*   **Frames:** 3
*   **Frame Size:** 24x24 pixels
*   **Frame Wait:** 0.082 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="51"`
*   **Loop:** `0` (not looping)
*   **Events:**
    *   `jump` event triggered on frame 0.

### Jump Fall Animation

*   **Name:** `jump_fall`
*   **Frames:** 3
*   **Frame Size:** 24x24 pixels
*   **Frame Wait:** 0.082 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="76"`
*   **Loop:** `0` (not looping)

### Land Animation

*   **Name:** `land`
*   **Frames:** 4
*   **Frame Size:** 25x25 pixels
*   **Frame Wait:** 0.09 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="101"`
*   **Loop:** `0` (not looping)
*   **Shrink by One Pixel:** `1`
*   **Events:**
    *   `land` event triggered on frame 0.

### Attack Animation

*   **Name:** `attack`
*   **Frames:** 7
*   **Frame Size:** 25x25 pixels
*   **Frame Wait:** 0.09 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="126"`
*   **Loop:** `0` (not looping)
*   **Shrink by One Pixel:** `1`
*   **Events:**
    *   `slash` event triggered on frame 4.

### Attack Ranged Animation

*   **Name:** `attack_ranged`
*   **Frames:** 7
*   **Frame Size:** 25x25 pixels
*   **Frame Wait:** 0.1 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="126"`
*   **Loop:** `0` (not looping)
*   **Shrink by One Pixel:** `1`
*   **Events:**
    *   `shoot_fire` event triggered on frame 4.

### Jump Prepare Animation

*   **Name:** `jump_prepare`
*   **Frames:** 3
*   **Frame Size:** 24x24 pixels
*   **Frame Wait:** 0.09 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="151"`
*   **Loop:** `0` (not looping)
*   **Events:**
    *   `jump_start` event triggered on frame 3.

## Key Animation Events

The `<Event>` tags within `<RectAnimation>` define specific actions or triggers that occur at certain frames of an animation.

| Event Name    | Animation Triggered On | Description