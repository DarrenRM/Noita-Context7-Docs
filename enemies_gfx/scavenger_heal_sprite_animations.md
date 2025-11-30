---
title: Scavenger Heal Sprite Animations
category: enemies_gfx
---

# Scavenger Heal Sprite Animations

This document details the sprite animations for the "Scavenger Heal" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/enemies_gfx/scavenger_heal.png` - The path to the sprite sheet.
*   **offset\_x**: `7` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Common Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **pos\_x**: The starting X coordinate of the animation frames on the sprite sheet.
*   **pos\_y**: The starting Y coordinate of the animation frames on the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are present horizontally on the sprite sheet.
*   **loop**: `1` for looping animations, `0` for one-time animations.

### Key Animations:

#### 1. Stand Animation

*   **name**: `stand`
*   **pos\_y**: `0`
*   **frame\_count**: `6`
*   **frame\_wait**: `0.2`
*   **loop**: `1`

#### 2. Walk Animation

*   **name**: `walk`
*   **pos\_y**: `21`
*   **frame\_count**: `6`
*   **frame\_wait**: `0.082`
*   **loop**: `1`
*   **Events**:
    *   `frame="2"`: `name="step"`, `probability="1"`, `check_physics_material="1"`
    *   `frame="5"`: `name="step"`, `probability="1"`, `check_physics_material="1"`

#### 3. Run Animation (Copy of Walk)

*   **name**: `run`
*   **pos\_y**: `21`
*   **frame\_count**: `6`
*   **frame\_wait**: `0.082`
*   **loop**: `1`
*   **Events**: Similar to `walk`.

#### 4. Burn Animation (Copy of Walk)

*   **name**: `burn`
*   **pos\_y**: `21`
*   **frame\_count**: `6`
*   **frame\_wait**: `0.06` (Slightly faster than walk/run)
*   **loop**: `1`
*   **Events**: Similar to `walk`.

#### 5. Jump Up Animation

*   **name**: `jump_up`
*   **pos\_y**: `42`
*   **frame\_count**: `3`
*   **frame\_wait**: `0.082`
*   **loop**: `0`
*   **Events**:
    *   `frame="0"`: `name="jump"`, `probability="1"`, `check_physics_material="1"`

#### 6. Jump Falling Animation

*   **name**: `jump_fall`
*   **pos\_y**: `63`
*   **frame\_count**: `2`
*   **frame\_wait**: `0.082`
*   **loop**: `0`

#### 7. Attack Ranged Animation

*   **name**: `attack_ranged`
*   **pos\_y**: `84`
*   **frame\_count**: `3`
*   **frame\_wait**: `0.07`
*   **loop**: `0`
*   **Events**:
    *   `frame="1"`: `name="shoot_heal"`, `probability="1"`, `check_physics_material="0"`

#### 8. Hovering Animation

*   **name**: `fly_idle`
*   **pos\_y**: `105`
*   **frame\_count**: `4`
*   **frame\_wait**: `0.12`
*   **loop**: `1`

#### 9. Flying Animation

*   **name**: `fly_move`
*   **pos\_y**: `126`
*   **frame\_count**: `4`
*   **frame\_wait**: `0.09`
*   **loop**: `1`

## Animation Events

Events within animations can trigger specific game actions.

### Key Event Attributes:

*   **frame**: The frame number at which the event occurs.
*   **name**: The name of the event (e.g., "step", "jump", "shoot\_heal").
*   **probability**: The likelihood of the event occurring (usually `1` for defined events).
*   **check\_physics\_material**: `1` if the event should consider the physics material of the ground, `0` otherwise.

This structure provides a clear overview of the visual components and their associated behaviors for the Scavenger Heal enemy, useful for understanding and modifying its animations.