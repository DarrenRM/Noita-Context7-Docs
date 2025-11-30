---
title: Caster Cast Projectile
category: entities
---

---

# Caster Cast Projectile

This entity defines the behavior of a projectile cast by a "caster" entity. It primarily relies on a Lua script to handle its logic.

## Key Components

### LuaComponent

This component is crucial for defining the projectile's behavior.

*   **`script_source_file`**: Specifies the path to the Lua script that controls the projectile's actions.
    *   Value: `data/scripts/projectiles/caster_cast.lua`
*   **`execute_on_added`**: Determines if the script should run immediately when the entity is added to the game world.
    *   Value: `1` (True - script executes on spawn)
*   **`remove_after_executed`**: Indicates whether the entity should be removed from the game world after the script has finished executing.
    *   Value: `1` (True - projectile is removed after its script logic is complete)

## Lua Script (`data/scripts/projectiles/caster_cast.lua`)

The associated Lua script (`caster_cast.lua`) is responsible for the actual projectile mechanics, such as its movement, damage, effects, and interactions with the environment. The specifics of this script are not detailed in this XML, but it's the core of the projectile's functionality.