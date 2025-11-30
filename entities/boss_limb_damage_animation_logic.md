---
title: Boss Limb Damage Animation Logic
category: entities
---

# Boss Limb Damage Animation Logic

This script defines functions for handling damage reception and animating a sprite component, specifically for boss limbs.

## Core Functions

### `set_main_animation(current_name, next_name)`

This function is responsible for setting the sprite's current and next animations. It checks if the sprite is in an "opened" or "open" state before triggering the animation to prevent unintended visual glitches.

*   **`current_name`**: The name of the current animation frame.
*   **`next_name`**: The name of the next animation frame to transition to.

### `animate_sprite(sprite, current_name, next_name)`

A helper function to directly set the `rect_animation` and `next_rect_animation` properties of a `SpriteComponent`.

*   **`sprite`**: The `SpriteComponent` to animate.
*   **`current_name`**: The name of the current animation frame.
*   **`next_name`**: The name of the next animation frame.

## Event Handlers

### `damage_received(damage, desc, entity_who, is_fatal)`

This function is called when the entity receives damage. It triggers a sprite animation sequence, transitioning from a "hurt" state to an "opened" state.

*   **`damage`**: The amount of damage received.
*   **`desc`**: A description of the damage.
*   **`entity_who`**: The entity that dealt the damage.
*   **`is_fatal`**: A boolean indicating if the damage is fatal.