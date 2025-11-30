---
title: Wither End Status Effect
category: scripts
---

# Wither End Status Effect

This script defines the behavior of the "Wither End" status effect in Noita. When applied, it modifies the target's damage resistances based on data stored within a `VariableStorageComponent`.

## Core Functionality

The primary purpose of this script is to dynamically adjust the damage multipliers of an entity, typically the player, based on specific "wither data" provided.

### Key Attributes & Elements

*   **`entity_id`**: The unique identifier for the entity this script is attached to.
*   **`player_id`**: The parent entity of `entity_id`, usually the player.
*   **`DamageModelComponent`**: A component on the target entity that stores damage-related properties, including `damage_multipliers`.
*   **`VariableStorageComponent`**: A component used to store arbitrary data. This script looks for a variable named `"wither_data"`.
*   **`wither_data`**: A string value within the `VariableStorageComponent` that contains space-separated damage resistance values.
*   **`resists`**: A predefined table of damage types (e.g., "drill", "fire", "projectile") that the `wither_data` string corresponds to.
*   **`damage_multipliers`**: The specific property within `DamageModelComponent` that is modified. The script iterates through `resists` and applies the corresponding value from `wither_data`.
*   **`effect_resistance` Tag**: This script also enables components tagged with `"effect_resistance"` on child entities of the player.

## Data Structure

The `wither_data` string is expected to be a sequence of numerical values, separated by spaces. Each value corresponds to a specific damage resistance type listed in the `resists` table.

### Example `wither_data` format:

```
0.5 1.0 0.8 1.2 0.9 1.0 0.7 1.1 0.6
```

This would correspond to the `resists` table in order:

*   `drill`: 0.5
*   `electricity`: 1.0
*   `explosion`: 0.8
*   `fire`: 1.2
*   `ice`: 0.9
*   `melee`: 1.0
*   `projectile`: 0.7
*   `radioactive`: 1.1
*   `slice`: 0.6

If a value is missing in the `wither_data` string for a given resistance, it defaults to `1.0`.

## Script Logic Flow

1.  **Get Entity IDs**: Retrieves the current entity ID and its parent (player) ID.
2.  **Check Player Validity**: Ensures the player ID is valid and not the same as the current entity.
3.  **Access Components**: Gets the `DamageModelComponent` of the player and any `VariableStorageComponent` on the current entity.
4.  **Parse `wither_data`**:
    *   Iterates through `VariableStorageComponent`s to find the one with the name `"wither_data"`.
    *   Extracts the `value_string` from this component.
    *   Parses the string into a table of individual resistance values.
5.  **Apply Damage Multipliers**:
    *   Iterates through the predefined `resists` table.
    *   For each resistance, it retrieves the corresponding value from the parsed `wither_data`.
    *   Sets the `damage_multipliers` for that resistance on the player's `DamageModelComponent`.
6.  **Enable Effect Resistances**:
    *   Retrieves all child entities of the player.
    *   If a child entity has the tag `"effect_resistance"`, its components with that tag are enabled.