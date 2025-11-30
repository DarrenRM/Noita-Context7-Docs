---
title: Mine Animation Script
category: scripts
---

# Mine Animation Script

This script controls the animation states of a mine projectile in Noita, specifically handling its detonation triggered by collisions or damage.

## Key Functions

### `set_main_animation(current_name)`
- **Purpose:** Sets the main animation state for the entity.
- **Parameters:**
    - `current_name` (string): The name of the animation to set (e.g., "detonate").
- **Logic:**
    - Retrieves the entity's ID.
    - Iterates through all `SpriteComponent`s of the entity.
    - Updates the `rect_animation` property of each `SpriteComponent` to the provided `current_name`.

### `collision_trigger()`
- **Purpose:** Called when the mine collides with something.
- **Logic:**
    - Calls `set_main_animation("detonate")` to change the mine's animation to its detonation state.

### `damage_received(damage, desc, entity_who_caused, is_fatal)`
- **Purpose:** Called when the mine receives damage.
- **Parameters:**
    - `damage` (number): The amount of damage received.
    - `desc` (string): Description of the damage source.
    - `entity_who_caused` (entity ID): The entity that caused the damage.
    - `is_fatal` (boolean): Whether the damage was fatal.
- **Logic:**
    - Calls `set_main_animation("detonate")` to change the mine's animation to its detonation state.
    - Retrieves the entity's ID.
    - Edits the `CollisionTriggerComponent` to store the `timer_for_destruction` value in a local variable `mTimer`. This likely prepares for a timed detonation after receiving damage.