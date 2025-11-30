---
title: Colour Spell - Invisible
category: entities
---

# Colour Spell - Invisible

This entity defines a projectile that applies an invisible effect.

## Key Components

### LuaComponent (x2)

These components attach Lua scripts to the entity.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua`
    *   This script handles the core logic for colour spells, including their effects.
*   **`execute_every_n_frame`**: `1`
    *   The script will execute every frame.
*   **`remove_after_executed`**: `1`
    *   The Lua component will be removed after its script has executed.
*   **`execute_on_added`**: `1`
    *   The script will execute immediately when the entity is added.

### VariableStorageComponent

This component stores a variable associated with the entity.

*   **`name`**: `colour_name`
    *   The name of the variable.
*   **`value_string`**: `invis`
    *   The string value assigned to `colour_name`, indicating this is an "invisible" spell.