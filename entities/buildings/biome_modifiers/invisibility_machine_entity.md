---
title: Invisibility Machine Entity
category: entities/buildings/biome_modifiers
---

# Invisibility Machine Entity

This entity represents an invisibility machine, a biome modifier that attaches a shield to nearby enemies.

## Key Components

### LifetimeComponent
*   **lifetime**: The duration in frames the invisibility machine will exist.

### LuaComponent
*   **script_source_file**: Specifies the Lua script responsible for the entity's behavior.
    *   `data/scripts/animals/invisibility_machine.lua`
*   **execute_every_n_frame**: Determines how frequently the Lua script is executed.
    *   `21`