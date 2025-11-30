---
title: Fungus Death Behavior
category: scripts
---

---

# Fungus Death Behavior

This script defines the behavior for a "fungus" entity when it dies or its collision trigger timer expires. It primarily focuses on spawning a specific explosion effect.

## Key Functions

### `death(damage_type_bit_field, damage_message, entity_thats_responsible, drop_items)`

This function is called when the fungus entity is destroyed.

*   **Purpose:** To handle the entity's death.
*   **Action:** Spawns a `fungus_explosion.xml` entity at the fungus's current position.

### `collision_trigger_timer_finished()`

This function is called when a timer associated with the fungus's collision trigger finishes.

*   **Purpose:** To trigger an effect after a certain collision-related condition.
*   **Action:** Spawns a `fungus_explosion.xml` entity at the fungus's current position.

## Core Logic

Both `death` and `collision_trigger_timer_finished` share the same core logic:

1.  **Get Entity ID:** Retrieves the unique identifier for the current entity.
2.  **Get Transform:** Obtains the entity's current position (`pos_x`, `pos_y`).
3.  **Spawn Explosion:** Uses `EntityLoad` to instantiate the `data/entities/projectiles/fungus_explosion.xml` entity at the calculated position. This is the primary visual and functional outcome of the fungus's demise or timer expiration.

## Key Attributes/Elements

*   **`EntityLoad("data/entities/projectiles/fungus_explosion.xml", pos_x, pos_y)`:** This is the most critical line, responsible for spawning the explosion effect. The specific behavior of this explosion is defined within the `fungus_explosion.xml` file.
*   **`GetUpdatedEntityID()`:** Standard function to get the ID of the entity the script is attached to.
*   **`EntityGetTransform(entity_id)`:** Standard function to get the position of an entity.

## Summary

This script is a simple death handler for a fungus entity. Its main purpose is to create a visual explosion effect when the fungus dies or its collision timer runs out, by loading a predefined explosion entity.