---
title: Plague Rats Perk Logic
category: scripts
---

# Plague Rats Perk Logic

This script handles the logic for the "Plague Rats" perk in Noita. When activated, it seeks out nearby entities with the "homing_target" tag and applies a "plague_rats" variable to them, provided they don't already have it and are not polymorphed. This marks them for potential future effects handled by `plague_rats_death.lua`.

## Key Functionality

*   **Target Acquisition:** Identifies entities within a 160-unit radius that possess the "homing_target" tag.
*   **Plague Status Check:** Verifies if a target entity already has the "plague_rats" variable stored.
*   **Polymorph Check:** Ensures the target entity is not currently polymorphed.
*   **Plague Application:** If the target is eligible, it adds a `VariableStorageComponent` with the name "plague_rats" and a `LuaComponent` that links to a death script (`plague_rats_death.lua`).

## Core Components and Attributes

### `EntityGetInRadiusWithTag`

*   **Purpose:** Finds entities within a specified radius and with a specific tag.
*   **Key Attributes:**
    *   `x`, `y`: Coordinates of the entity executing the script.
    *   `radius`: The search radius (160 units in this case).
    *   `tag`: The tag to search for ("homing_target").

### `VariableStorageComponent`

*   **Purpose:** Stores custom variables on an entity.
*   **Key Attributes:**
    *   `name`: The name of the variable being stored (e.g., "plague_rats").

### `LuaComponent`

*   **Purpose:** Attaches Lua scripts to entities for custom behavior.
*   **Key Attributes:**
    *   `script_death`: The script to execute when the entity dies (e.g., "data/scripts/perks/plague_rats_death.lua").
    *   `execute_every_n_frame`: Controls script execution frequency. "-1" indicates it's primarily for death-triggered events.

### `EntityAddComponent`

*   **Purpose:** Adds a specified component to an entity.
*   **Usage:** Used to add `VariableStorageComponent` and `LuaComponent` to eligible targets.

### `EntityHasTag`

*   **Purpose:** Checks if an entity possesses a specific tag.
*   **Usage:** Used to check for the "polymorphed" tag.