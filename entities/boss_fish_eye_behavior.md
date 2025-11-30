---
title: Boss Fish Eye Behavior
category: entities
---

# Boss Fish Eye Behavior

This document details the behavior of the Boss Fish's eye entity, focusing on its animation states, player interaction, and projectile firing.

## Core Functionality

The `eye.lua` script controls the visual state of the boss fish's eye and its offensive capabilities. It primarily manages:

*   **Animation Transitions:** Switching between "closed", "close", "open", and "opened" states.
*   **Player Detection:** Reacting to the player's proximity.
*   **Projectile Firing:** Launching projectiles when the eye is in its "opened" state for a sustained period.

## Key Components and Attributes

### SpriteComponent

This component is crucial for managing the visual appearance and animation of the eye.

*   **`rect_animation`**: Controls the current animation state. Possible values include:
    *   `"closed"`: The eye is fully closed.
    *   `"close"`: The eye is in the process of closing.
    *   `"open"`: The eye is in the process of opening.
    *   `"opened"`: The eye is fully open.
*   **`next_rect_animation`**: Sets the animation to transition to after the current one finishes.

### VariableStorageComponent

Used to store and manage the `phase_timer`, which tracks the duration of the eye's current animation state.

*   **`name`**: `"phase_timer"`
*   **`value_int`**: An integer representing the timer's current count.

### HitboxComponent

This component is enabled or disabled based on the eye's state, likely to control collision or interaction during different animation phases.

*   **Enabled**: When the eye is opening or opened.
*   **Disabled**: When the eye is closed or closing.

## Behavior Logic

### Initialization

1.  The script retrieves the entity's ID, root entity ID, and transform (position).
2.  It initializes a `timer` and retrieves the `VariableStorageComponent` to access the `phase_timer`.
3.  It also gets the `HitboxComponent` of the root entity.

### Player Proximity and Animation Control

*   The script continuously checks for the presence of a player within a 160-unit radius.
*   **If no player is detected:**
    *   If the eye is `"opened"`, it transitions to `"close"` and then `"closed"`. The `HitboxComponent` is disabled.
    *   If the eye is `"close"` and the `timer` exceeds 36 frames, it transitions to `"closed"`.
    *   If the eye is `"open"` and the `timer` exceeds 36 frames, it transitions to `"opened"`. The `HitboxComponent` is enabled.
*   **If a player is detected:**
    *   If the eye is `"closed"`, it transitions to `"open"`.
    *   If the eye is `"open"` and the `timer` exceeds 36 frames, it transitions to `"opened"`. The `HitboxComponent` is enabled.
    *   If the eye is `"close"` and the `timer` exceeds 36 frames, it transitions to `"closed"`.

### Projectile Firing

*   When the eye is in the `"opened"` state and the `timer` exceeds 360 frames, the boss fish fires a volley of projectiles.
*   Eight projectiles are fired in a circular pattern around the boss fish.
*   The projectiles are of type `orb_big.xml`.
*   The firing pattern is randomized slightly using `SetRandomSeed` and `Random`.

### Timer Management

*   The `phase_timer` is incremented each frame.
*   It is reset to 0 when transitions between certain animation states occur or when projectiles are fired.
*   The updated `timer` value is stored back into the `VariableStorageComponent`.