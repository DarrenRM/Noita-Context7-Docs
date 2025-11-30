---
title: Petrify Hit Effect
category: entities
---

# Petrify Hit Effect

This entity defines the visual and functional effect of a projectile hitting an entity and causing petrification. It primarily relies on a Lua script to handle the actual petrification logic.

## Lua Component

The core functionality is driven by a `LuaComponent`.

### Key Attributes

*   **`script_source_file`**: Specifies the Lua script responsible for the petrification effect.
    *   Value: `data/scripts/projectiles/petrify.lua`
*   **`execute_on_added`**: Determines if the script should execute immediately when the entity is added.
    *   Value: `0` (Script does not execute on addition)
*   **`remove_after_executed`**: Indicates if the entity should be removed after the script has finished its execution.
    *   Value: `1` (Entity is removed after script execution)
*   **`execute_every_n_frame`**: Controls how often the script's `update` function is called.
    *   Value: `1` (Script's `update` function is called every frame)