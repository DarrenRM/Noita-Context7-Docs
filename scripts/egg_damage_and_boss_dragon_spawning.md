---
title: Egg Damage and Boss Dragon Spawning
category: scripts
---

# Egg Damage and Boss Dragon Spawning

This script defines the behavior for an "egg" entity, specifically how it handles damage and triggers the spawning of a boss dragon.

## Key Functions

### `spawn_boss_dragon()`

This function is responsible for initiating the boss dragon spawn sequence.

*   **Global State Management:**
    *   Checks a global variable `boss_dragon_spawned` to prevent multiple spawns.
    *   Sets `boss_dragon_spawned` to "1" upon successful initiation.
    *   Stores the spawn position (`boss_dragon_spawned_pos_x`, `boss_dragon_spawned_pos_y`) in global variables.
*   **Visual Feedback:**
    *   Triggers an "open" animation on the entity.
*   **Damage Script Disabling:**
    *   Iterates through `LuaComponent`s attached to the entity.
    *   Clears the `script_damage_received` property of these components, effectively disabling further damage processing for the egg itself.
*   **Delayed Entity Loading:**
    *   Uses `SetTimeOut` to schedule the `impl_spawn_boss_dragon` function to run after a short delay (0.54 seconds). This is a workaround for issues encountered with direct `EntityLoad` calls.

### `impl_spawn_boss_dragon()`

This function is called by `SetTimeOut` to actually load the boss dragon entity.

*   **Position Retrieval:**
    *   Retrieves the stored spawn position from global variables.
*   **Entity Loading:**
    *   Loads the `data/entities/animals/boss_dragon.xml` entity at the retrieved position, slightly offset vertically.

### `damage_received( damage, desc, entity_who, is_fatal )`

This is the primary damage handling function for the egg entity.

*   **Fatal Damage Check:**
    *   If `is_fatal` is true (meaning the damage would normally kill the entity), it proceeds to spawn the boss dragon.
*   **Randomized Spawning:**
    *   If the damage is not fatal, it has a 60% chance (`Random(0,100) < 60`) to trigger the boss dragon spawn.

## Key Attributes/Elements

*   **Global Variables:** Used extensively for managing spawn state and position (`boss_dragon_spawned`, `boss_dragon_spawned_pos_x`, `boss_dragon_spawned_pos_y`).
*   **`LuaComponent`:** The script relies on `LuaComponent`s to manage its behavior, particularly for disabling damage scripts.
*   **`SetTimeOut`:** Crucial for asynchronous entity loading, overcoming potential script execution order issues.
*   **`EntityLoad`:** The function used to instantiate the boss dragon entity.
*   **`play_animation`:** Used for visual cues during the spawning process.
*   **`GlobalsGetValue` / `GlobalsSetValue`:** Standard functions for interacting with global game state.
*   **`ComponentSetValue`:** Used to modify component properties.