---
title: Game Helper Functions
category: scripts
---

# Game Helper Functions

This document outlines key helper functions found in `game_helpers.lua`, designed to assist in AI-assisted modding of Noita. These functions provide common game logic operations that can be easily integrated into custom mods.

## Core Functionality

### `play_animation( entity_id, animation_name )`

This function applies a specified animation to an entity's sprite component.

*   **`entity_id`**: The unique identifier of the entity to animate.
*   **`animation_name`**: The name of the animation to play (e.g., "idle", "walk").

### `heal_entity( entity_id, heal_amount )`

Restores health to a given entity and triggers a visual healing effect.

*   **`entity_id`**: The unique identifier of the entity to heal.
*   **`heal_amount`**: The amount of health to restore.

**Key Actions:**
*   Finds `DamageModelComponent` for the entity.
*   Calculates and applies the new health, capping at `max_hp`.
*   Spawns a `heal_effect.xml` particle entity at the entity's location.

### `load_gold_entity( entity_filename, x, y, remove_timer )`

Loads a gold entity (likely for pickups) and optionally sets a lifetime for it.

*   **`entity_filename`**: The path to the gold entity's XML file.
*   **`x`**: The X-coordinate for spawning.
*   **`y`**: The Y-coordinate for spawning.
*   **`remove_timer`**: A boolean. If `true`, any `LifetimeComponent` on the loaded entity will be removed, preventing it from despawning automatically.

### `give_perk_to_enemy( perk_data, entity_who_picked, entity_item )`

Grants a perk to an enemy entity, applying its effects and UI representation.

*   **`perk_data`**: A table containing information about the perk. Expected keys include:
    *   `id`: The unique identifier of the perk.
    *   `game_effect`: Path to a game effect XML to apply.
    *   `func_enemy`: A function to call specifically for enemy perk application.
    *   `func`: A general function to call for perk application.
    *   `ui_icon`: Path to the UI icon for the perk.
*   **`entity_who_picked`**: The entity receiving the perk (the enemy).
*   **`entity_item`**: The entity that triggered the perk pickup (often 0 if not a physical item).

**Key Actions:**
*   Applies `game_effect` if specified, setting its duration to infinite (`frames = -1`).
*   Executes custom perk logic via `perk_data.func_enemy` or `perk_data.func`.
*   Spawns a visual perk icon (`enemy_icon.xml`) attached to the entity.

### `give_random_perk_to_enemy( entity_id )`

Selects and grants a random perk that is usable by enemies to a specified entity.

*   **`entity_id`**: The unique identifier of the enemy entity to receive the perk.

**Key Actions:**
*   Checks if the entity is a boss type (worm, dragon, ghost, lukki) and skips if it is.
*   Filters `perk_list` to find perks marked with `usable_by_enemies = true`.
*   Randomly selects one of the valid perks.
*   Calls `give_perk_to_enemy` to apply the chosen perk.