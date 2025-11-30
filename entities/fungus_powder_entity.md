---
title: Fungus Powder Entity
category: entities
---

# Fungus Powder Entity

This entity represents the "Fungus Powder" item in Noita. It is primarily defined by its associated Lua script, which handles its behavior and effects.

## Key Components

### LuaComponent
This is the core component that defines the entity's dynamic behavior.

*   **`script_source_file`**: `data/scripts/animals/fungus_powder.lua`
    *   This attribute specifies the path to the Lua script responsible for the entity's logic.
*   **`execute_on_added`**: `1`
    *   Indicates that the associated Lua script should be executed immediately when this entity is added to the game world.

## Behavior (via Lua Script)

The `data/scripts/animals/fungus_powder.lua` script dictates the specific actions and effects of Fungus Powder. While the XML only points to the script, the script itself would contain logic for:

*   How the powder is spawned or dropped.
*   Its visual appearance.
*   Any interactions it has with the player, enemies, or the environment.
*   Potential effects like damage, status ailments, or environmental changes.