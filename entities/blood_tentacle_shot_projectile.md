---
title: Blood Tentacle Shot Projectile
category: entities
---

# Blood Tentacle Shot Projectile

This entity defines the projectile fired by the Blood Tentacle. It primarily relies on a Lua script to handle its behavior.

## Key Components

### LuaComponent
This is the core component responsible for the projectile's logic.

*   **`script_source_file`**: `data/scripts/projectiles/bloodtentacle.lua`
    *   Specifies the Lua script that governs the projectile's behavior, including its movement, damage, and any special effects.
*   **`execute_on_added`**: `1`
    *   Indicates that the Lua script should be executed immediately when the projectile is spawned.
*   **`remove_after_executed`**: `1`
    *   Ensures that the projectile entity is removed from the game world once its associated Lua script has finished executing.

## Inheritance

### InheritTransformComponent
This component suggests that the projectile inherits transformation properties (like position, rotation, and scale) from its parent or the entity that spawned it. This is standard for projectiles to ensure they start at the correct location and orientation.