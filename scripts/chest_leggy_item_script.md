---
title: Chest Leggy Item Script
category: scripts
---

# Chest Leggy Item Script

This script defines the behavior for the "Chest Leggy" item in Noita. When this item is interacted with (picked up or its physics body is modified), it triggers a special effect and spawns a "Chest Leggy" entity.

## Core Functionality

The script primarily uses the `spawn_leggy` function to handle the item's activation.

### `spawn_leggy( entity_item )`

This function is responsible for the visual and auditory effects, as well as spawning the actual "Chest Leggy" entity.

*   **Parameters:**
    *   `entity_item`: The entity ID of the "Chest Leggy" item itself.

*   **Key Actions:**
    1.  **Get Position:** Retrieves the `x` and `y` coordinates of the item.
    2.  **Spawn Polymorph Explosion:** Loads and spawns a `polymorph_explosion.xml` particle effect at the item's location.
    3.  **Play Sound:** Plays a specific sound effect (`game_effect/polymorph/create`) associated with the polymorph effect.
    4.  **Spawn Chest Leggy Entity:** Loads and spawns the actual `chest_leggy.xml` entity at the item's location.
    5.  **Kill Item:** Removes the original "Chest Leggy" item entity from the game.

## Event Handlers

The script hooks into several game events to trigger the `spawn_leggy` function.

### `item_pickup( entity_item, entity_who_picked, name )`

This function is called when a player picks up the "Chest Leggy" item. It directly calls `spawn_leggy` to activate the item's effect.

### `physics_body_modified( is_destroyed )`

This function is triggered when the physics body of the "Chest Leggy" item is modified (e.g., if it's hit by something). It retrieves the updated entity ID and calls `spawn_leggy`.

### `collision_trigger( colliding_entity_id )`

This function is called when the "Chest Leggy" item collides with another entity. It retrieves the updated entity ID and calls `spawn_leggy`.