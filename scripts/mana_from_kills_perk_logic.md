---
title: Mana From Kills Perk Logic
category: scripts
---

# Mana From Kills Perk Logic

This script implements the "Mana From Kills" perk logic in Noita. When an entity with the "homing_target" tag is killed, this perk grants mana to the player.

## Core Functionality

The script identifies entities within a radius that are tagged as "homing_target". For each such entity, it checks if it has already been processed by this perk. If not, it applies the "mana_from_kills" tag and adds components to handle mana regeneration upon the target's death.

## Key Components and Attributes

### `EntityGetInRadiusWithTag`

*   **Purpose**: Detects potential targets for the perk.
*   **Radius**: `240` units.
*   **Tag**: `"homing_target"`.

### `EntityHasTag`

*   **Purpose**: Checks if an entity has specific tags.
*   **Tags Checked**:
    *   `"mana_from_kills"`: Prevents re-processing of a target.
    *   `"polymorphed"`: Excludes polymorphed entities from triggering the perk.

### `VariableStorageComponent`

*   **Purpose**: Stores custom variables associated with an entity.
*   **Key Variable**:
    *   `name`: `"mana_from_kills"`
    *   `value_int`: Stores the `entity_id` of the perk's source (the player or entity that triggered the perk).

### `LuaComponent`

*   **Purpose**: Executes Lua scripts on an entity.
*   **Key Attributes**:
    *   `script_death`: `"data/scripts/perks/mana_from_kills_death.lua"` - This script is executed when the target entity dies, triggering mana regeneration.
    *   `execute_every_n_frame`: `"-1"` - Indicates that the script is not intended for continuous frame-by-frame execution but rather for event-driven triggers (like death).

## Logic Flow

1.  **Get Entity ID and Position**: Retrieves the ID and coordinates of the entity executing this script.
2.  **Scan for Targets**: Searches for entities with the `"homing_target"` tag within a `240` unit radius.
3.  **Iterate Through Targets**: For each found target:
    *   **Check if Processed**: Verifies if the target already has the `"mana_from_kills"` tag.
    *   **Check for Variable Storage**: If not processed, it looks for a `VariableStorageComponent` named `"mana_from_kills"`.
    *   **Apply Perk Logic**: If the target is not processed, not polymorphed, and the variable storage check passes (or is not found, implying it's a new target), the following actions occur:
        *   The target entity is tagged with `"mana_from_kills"`.
        *   A `VariableStorageComponent` is added to store the source `entity_id` and the name `"mana_from_kills"`.
        *   A `LuaComponent` is added, linking the `script_death` to `mana_from_kills_death.lua` to handle mana regeneration upon the target's demise.