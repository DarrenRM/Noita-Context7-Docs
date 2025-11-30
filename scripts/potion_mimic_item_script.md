---
title: Potion Mimic Item Script
category: scripts
---

# Potion Mimic Item Script

This script defines the behavior for a "Potion Mimic" item in Noita. When interacted with (picked up, collided with, or its physics body is modified), it transforms into a Mimic Potion entity and plays a sound effect.

## Key Functions

### `spawn_leggy( entity_item )`

This is the core function responsible for the transformation.

*   **Purpose:** Spawns a polymorph explosion particle effect, plays a sound, spawns a `mimic_potion.xml` entity, and destroys the original item.
*   **Parameters:**
    *   `entity_item`: The entity ID of the Potion Mimic item.
*   **Actions:**
    *   Retrieves the position (`x`, `y`) of the `entity_item`.
    *   Loads `data/entities/particles/polymorph_explosion.xml` at the item's position.
    *   Plays the sound `game_effect/polymorph/create` from `data/audio/Desktop/misc.bank`.
    *   Loads `data/entities/animals/mimic_potion.xml` at the item's position.
    *   Destroys the `entity_item`.

### `item_pickup( entity_item, entity_who_picked, name )`

Triggered when a player picks up the item.

*   **Purpose:** Initiates the transformation process.
*   **Parameters:**
    *   `entity_item`: The entity ID of the Potion Mimic item.
    *   `entity_who_picked`: The entity ID of the entity that picked up the item.
    *   `name`: The name of the item.
*   **Actions:** Calls `spawn_leggy()` with the `entity_item`.

### `physics_body_modified( is_destroyed )`

Triggered when the item's physics body is modified (e.g., destroyed by an explosion).

*   **Purpose:** Initiates the transformation process upon physics interaction.
*   **Parameters:**
    *   `is_destroyed`: A boolean indicating if the physics body was destroyed.
*   **Actions:**
    *   Gets the updated entity ID using `GetUpdatedEntityID()`.
    *   Calls `spawn_leggy()` with the updated entity ID.

### `collision_trigger( colliding_entity_id )`

Triggered when the item collides with another entity.

*   **Purpose:** Initiates the transformation process upon collision.
*   **Parameters:**
    *   `colliding_entity_id`: The entity ID of the entity that the Potion Mimic collided with.
*   **Actions:**
    *   Gets the updated entity ID using `GetUpdatedEntityID()`.
    *   Calls `spawn_leggy()` with the updated entity ID.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions.

## Summary

The Potion Mimic script is a simple but effective item that acts as a trap or surprise. Its core logic relies on the `spawn_leggy` function, which is called by various game events to transform the item into a hostile Mimic Potion.