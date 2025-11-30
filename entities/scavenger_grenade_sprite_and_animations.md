---
title: Scavenger Grenade Sprite and Animations
category: entities
---

# Scavenger Grenade Sprite and Animations

This document details the sprite and animation definitions for the Scavenger Grenade enemy in Noita.

## Sprite Definition

The main sprite for the Scavenger Grenade is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/scavenger_grenade.png` - The primary image file for the sprite.
*   **hotspots_filename**: `data/enemies_gfx/scavenger_grenade_hotspots.png` - The image file containing defined hotspots.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Hotspots:

Hotspots define specific points on the sprite, often used for interaction or collision detection.

*   **hand**: `color="00ff0000"` - Likely indicates a point related to the entity's hand.
*   **eye**: `color="000000ff"` - Likely indicates a point related to the entity's eye.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation sequence.

### Animation Details:

Each `<RectAnimation>` defines a sequence of frames from a sprite sheet.

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**, **pos\_y**: The starting coordinates on the sprite sheet for this animation.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for non-looping.

### Key Animations:

| Animation Name    | Description        | Frame Count | Frame Wait | Loop | Key Events                                                              |
| :---------------- | :----------------- | :---------- | :--------- | :--- | :---------------------------------------------------------------------- |
| **stand**         | Idle standing pose | 6           | 0.2        | 1    | None                                                                    |
| **walk**          | Walking animation  | 6           | 0.082      | 1    | `step` on frames 2 and 5 (checks physics material)                      |
| **run**           | Running animation  | 6           | 0.082      | 1    | `step` on frames 2 and 5 (checks physics material) - *Identical to walk* |
| **burn**          | Burning animation  | 6           | 0.06       | 1    | `step` on frames 2 and 5 (checks physics material) - *Similar to walk*  |
| **jump\_up**      | Jumping upwards    | 3           | 0.082      | 0    | `jump` on frame 0 (checks physics material)                             |
| **jump\_fall**    | Falling after jump | 2           | 0.082      | 0    | None                                                                    |
| **attack\_ranged**| Ranged attack      | 5           | 0.09       | 0    | `shoot_bullet` on frame 1 (does not check physics material)             |
| **fly\_idle**     | Hovering animation | 4           | 0.12       | 1    | None                                                                    |
| **fly\_move**     | Flying animation   | 4           | 0.09       | 1    | None                                                                    |
| **attack**        | Melee attack       | 4           | 0.09       | 0    | `hit` on frame 1 (does not check physics material)                      |
| **jump\_prepare** | Preparing to jump  | 3           | 0.1        | 0    | `jump_start` on frame 3                                                 |
| **throw**         | Throwing animation | 4           | 0.09       | 0    | `throw_release` on frame 1                                              |
| **reload**        | Reloading animation| 6           | 0.05       | 0    | None                                                                    |

### Animation Events:

Animations can trigger events at specific frames.

*   **step**: Triggered during movement animations, potentially for footstep sounds or effects. `check_physics_material="1"` suggests it might react differently based on the surface.
*   **jump**: Triggered at the start of a jump. `check_physics_material="1"` implies it might be influenced by the ground.
*   **shoot\_bullet**: Triggered during ranged attacks, initiating projectile firing. `check_physics_material="0"` means it's not dependent on the ground material.
*   **hit**: Triggered during melee attacks, indicating a successful hit. `check_physics_material="0"` means it's not dependent on the ground material.
*   **jump\_start**: Triggered when the jump action begins.
*   **throw\_release**: Triggered when an item is thrown.