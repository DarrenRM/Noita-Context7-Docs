---
title: AI-Assisted Modding: Loading Entities with Perks
category: scripts
---

# AI-Assisted Modding: Loading Entities with Perks

This documentation outlines how to load entities in Noita and equip them with perks, specifically for AI-assisted modding. It focuses on the core logic for assigning perks to entities.

## Core Functions

### `give_perk_to_enemy(perk_data, entity_who_picked, entity_item)`

This function is responsible for applying a given perk to an entity.

**Key Attributes of `perk_data`:**

*   `id`: The unique identifier for the perk.
*   `game_effect`: The name of the game effect component to apply.
*   `func`: A custom function to execute when the perk is applied.
*   `ui_icon`: The file path to the perk's UI icon.

**Key Parameters:**

*   `perk_data`: A table containing information about the perk to be applied.
*   `entity_who_picked`: The entity that will receive the perk.
*   `entity_item`: The entity that represents the perk item (often `nil` in this context).

### `entity_load_give_perks(entity, x, y)`

This function loads a specified entity at given coordinates and then assigns it a random perk that is usable by enemies.

**Key Parameters:**

*   `entity`: The file path to the entity's XML definition (e.g., `"data/entities/animals/shotgunner.xml"`).
*   `x`: The X-coordinate for loading the entity.
*   `y`: The Y-coordinate for loading the entity.

**Internal Logic:**

1.  Loads the specified entity.
2.  Disables `CameraBoundComponent` if present to prevent the entity from being immediately unloaded.
3.  Filters `perk_list` to identify perks marked as `usable_by_enemies`.
4.  Selects a random perk from the valid list.
5.  Calls `give_perk_to_enemy` to apply the chosen perk.

## Example Usage (Debug Function)

### `SPAWN_SHOTGUNNER()`

This function is provided for debugging purposes. When called (e.g., via the debug UI), it spawns a "shotgunner" entity at the current camera position and equips it with a random enemy-usable perk.

**How to Use:**

1.  Ensure you have Noita's debug console enabled.
2.  Load this script.
3.  In the debug UI, find and execute the `SPAWN_SHOTGUNNER()` function.

## `perk_list` Structure (Relevant Fields)

The `perk_list` table (defined in `data/scripts/perks/perk_list.lua`) contains data for all available perks. For the purpose of this script, the following fields are most relevant:

| Field             | Type    | Description                                                              |
| :---------------- | :------ | :----------------------------------------------------------------------- |
| `id`              | string  | Unique identifier for the perk.                                          |
| `usable_by_enemies` | boolean | If `true`, this perk can be assigned to enemies by this script.          |
| `game_effect`     | string  | The name of the `GameEffect` component to apply to the entity.           |
| `func`            | function| A custom function to execute when the perk is applied.                 |
| `ui_icon`         | string  | File path to the perk's icon used in the UI.                             |

**Note:** This is a simplified view. Refer to `data/scripts/perks/perk_list.lua` for the complete structure of perk data.