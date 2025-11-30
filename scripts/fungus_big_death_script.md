---
title: Fungus Big Death Script
category: scripts
---

---

# Fungus Big Death Script

This script defines the behavior for the "Fungus Big" entity when it dies or its collision trigger timer finishes. It primarily focuses on spawning an explosion effect.

## Key Functions

### `death(damage_type_bit_field, damage_message, entity_thats_responsible, drop_items)`

This function is called when the entity receives fatal damage.

*   **Purpose:** To trigger the death animation and effects.
*   **Action:** Spawns `data/entities/projectiles/fungus_big_explosion.xml` at the entity's current position.

### `collision_trigger_timer_finished()`

This function is called when a specific timer related to collision triggers expires.

*   **Purpose:** To trigger an effect after a certain collision-related condition is met.
*   **Action:** Spawns `data/entities/projectiles/fungus_big_explosion.xml` at the entity's current position.

## Core Logic

The script's core logic revolves around the `EntityLoad` function, which is used to instantiate other entity XML files at specific world coordinates. In both `death` and `collision_trigger_timer_finished`, this function is used to create a visual explosion effect, likely a particle effect or a small projectile that detonates.

## Dependencies

*   `data/scripts/lib/utilities.lua`: This is a common utility library for Noita scripting.
*   `data/entities/projectiles/fungus_big_explosion.xml`: This XML file defines the visual and behavioral aspects of the explosion effect.