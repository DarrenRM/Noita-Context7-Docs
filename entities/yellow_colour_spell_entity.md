---
title: Yellow Colour Spell Entity
category: entities
---

# Yellow Colour Spell Entity

This entity defines the properties for a "yellow" colour spell in Noita, primarily managed through Lua scripts.

## Key Components

### LuaComponent
This component is responsible for executing Lua scripts associated with the spell.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua`
    *   This indicates that the core logic for this spell's behaviour is handled by the `colour_spell.lua` script.
*   **`execute_every_n_frame`**: `1`
    *   The script will execute every frame.
*   **`execute_on_added`**: `1`
    *   The script will execute once when the entity is added to the game.
*   **`remove_after_executed`**: `1`
    *   The Lua component will be removed after its script has executed.

### VariableStorageComponent
This component stores specific variables associated with the entity.

*   **`name`**: `colour_name`
    *   The name of the variable being stored.
*   **`value_string`**: `yellow`
    *   The string value assigned to the `colour_name` variable, identifying this entity as the "yellow" colour spell.