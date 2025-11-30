---
title: Necromancer Super Sprite Animations
category: enemies_gfx
---

# Necromancer Super Sprite Animations

This document details the sprite animations for the "Necromancer Super" enemy in Noita, as defined in the `necromancer_super.xml` file. It focuses on the key attributes of each animation, useful for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Necromancer Super.

*   **filename**: `data/enemies_gfx/necromancer_super.png` - The primary image file for the sprite.
*   **offset_x**: `16` - Horizontal offset for the sprite's origin.
*   **offset_y**: `42` - Vertical offset for the sprite's origin.
*   **default_animation**: `"stand"` - The animation to play by default.

## Animations

This section lists the defined animations, their properties, and any associated events.

### `stand`

The idle animation for the Necromancer Super.

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.1`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `120`

### `walk`

The walking animation.

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.085`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `0`

### `run`

The running animation.

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.085`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `0`

### `burn`

The animation for when the Necromancer Super is burning.

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.085`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `0`

### `fly_idle`

The idle animation while flying.

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.12`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `120`

### `fly_move`

The movement animation while flying.

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.12`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `0`

### `attack_ranged`

The animation for a standard ranged attack. This animation is not looped (`loop="0"`).

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.08`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `60`

#### Events for `attack_ranged`

*   **`shoot_magic`**:
    *   **frame**: `6` - The frame on which the event triggers.
    *   **name**: `"shoot_magic"` - The name of the event, likely triggering a projectile.
    *   **probability**: `1` - The event will always trigger when the specified frame is reached.
    *   **on_finished**: `0` - The event does not depend on the animation finishing.
    *   **check_physics_material**: `0` - Physics material is not checked for this event.
    *   **max_distance**: `500` - Maximum distance for the projectile effect.

### `attack_ranged_fast`

A faster ranged attack animation. This animation is not looped (`loop="0"`).

*   **frame_count**: `4`
*   **frame_height**: `59`
*   **frame_wait**: `0.09`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `180`

### `attack`

A standard melee or close-range attack animation. This animation is not looped (`loop="0"`).

*   **frame_count**: `8`
*   **frame_height**: `60`
*   **frame_wait**: `0.08`
*   **frame_width**: `42`
*   **frames_per_row**: `8`
*   **pos_x**: `0`
*   **pos_y**: `60`

#### Events for `attack`

*   **`shoot_magic`**:
    *   **frame**: `6` - The frame on which the event triggers.
    *   **name**: `"shoot_magic"` - The name of the event, likely triggering a projectile.
    *   **probability**: `1` - The event will always trigger when the specified frame is reached.
    *   **on_finished**: `0` - The event does not depend on the animation finishing.
    *   **check_physics_material**: `0` - Physics material is not checked for this event.
    *   **max_distance**: `500` - Maximum distance for the projectile effect.