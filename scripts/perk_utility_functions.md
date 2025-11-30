---
title: Perk Utility Functions
category: scripts/
---

# Perk Utility Functions

This document outlines utility functions used within Noita's perk system, primarily for managing perk stacking, tracking perk pickups, and applying status effects. These functions are crucial for modders looking to implement custom perks or modify existing ones.

## Core Perk Management

### `set_perk_entity_pickup_count(entity_who_picked, perk_entity_name, count)`

This function is designed for perks that can be stacked. It ensures that duplicate perk entities are not created and manages a count associated with a specific perk entity.

*   **`entity_who_picked`**: The entity that picked up the perk.
*   **`perk_entity_name`**: The name of the perk entity to track.
*   **`count`**: The desired pickup count for the perk.

This function searches for a child entity matching `perk_entity_name` and updates its `perk_pickup_count` variable. If the variable doesn't exist, it's created.

### `perk_pickup_event(style)`

Tracks the total number of times a perk of a specific `style` has been picked up.

*   **`style`**: A string representing the perk category (e.g., "RATTINESS", "FUNGAL").

This function increments a global variable named `[STYLE]_PERK_TOTAL_COUNT`.

### `reset_perk_pickup_event(style)`

Resets the pickup count for a specific perk `style` back to zero.

*   **`style`**: A string representing the perk category.

This function sets the global variable `[STYLE]_PERK_TOTAL_COUNT` to "0".

## Status Effect Application

These functions apply specific status effects to the player, often triggered by reaching certain thresholds of a perk's level.

### `add_rattiness_level(entity_who_picked)`

Increases the player's "rattiness" level. Upon reaching level 3, it grants a tail, persistent "player\_status\_ratty" flag, and increases movement speed.

*   **`entity_who_picked`**: The player entity.

**Key Effects at Level 3:**
*   Spawns a `verlet_tail.xml` entity.
*   Adds the `player_status_ratty` persistent flag.
*   Increases `run_velocity`, `velocity_min_x`, and `velocity_max_x` by 15%.

### `add_funginess_level(entity_who_picked)`

Increases the player's "fungal" level. Upon reaching level 3, it enables player hats, disables a shadow component, grants the "player\_status\_funky" flag, and reduces explosion resistance.

*   **`entity_who_picked`**: The player entity.

**Key Effects at Level 3:**
*   Enables components tagged `player_hat`.
*   Disables components tagged `player_hat2_shadow`.
*   Adds the `player_status_funky` persistent flag.
*   Reduces explosion damage multiplier by 10% (multiplies by 0.9).

### `add_ghostness_level(entity_who_picked)`

Increases the player's "ghostness" level. Upon reaching level 3, it spawns two ghost entities, grants the "player\_status\_ghostly" flag, and increases fly recharge speed.

*   **`entity_who_picked`**: The player entity.

**Key Effects at Level 3:**
*   Spawns `ghostly_ghost.xml` and `tiny_ghost_extra.xml` entities.
*   Adds the `player_status_ghostly` persistent flag.
*   Increases `fly_recharge_spd` by 15%.

### `add_lukkiness_level(entity_who_picked)`

Increases the player's "lukkiness" level. Upon reaching level 3, it enables a "lukki\_enable" component, grants the "player\_status\_lukky" flag, makes a "lukki\_disable" sprite invisible, and increases movement speed.

*   **`entity_who_picked`**: The player entity.

**Key Effects at Level 3:**
*   Enables components tagged `lukki_enable`.
*   Adds the `player_status_lukky` persistent flag.
*   Sets alpha of sprite component "lukki\_disable" to 0.0.
*   Increases `run_velocity`, `velocity_min_x`, and `velocity_max_x` by 10%.

### `add_halo_level(entity_who_picked, amount, set_to_this_value)`

Manages the player's "halo" level, affecting fire and holy resistance. This function can increase or decrease the level, or set it to a specific value.

*   **`entity_who_picked`**: The player entity.
*   **`amount`**: The amount to change the halo level by (e.g., 1 for increase, -1 for decrease).
*   **`set_to_this_value`**: (Optional) A specific value to set the halo level to.

**Key Effects:**
*   **Level 3+**: Spawns `player_halo_light.xml`, grants `player_status_halo`, increases fire and holy resistance by 10% (multiplies by 0.9).
*   **Level -3-**: Spawns `player_halo_dark.xml`, grants `player_status_halo`, increases fire and holy resistance by 10% (multiplies by 0.9).
*   **Level 0**: Removes halo decoration and fire/holy resistance bonuses.
*   **Losing Halo**: Removes halo decoration and reverses resistance bonuses.