---
title: Destruction Projectile
category: entities/projectiles/deck
---

# Destruction Projectile

This entity defines a player-owned projectile with destructive capabilities.

## Key Components

### LuaComponent
This component handles the projectile's behavior through a Lua script.

*   **script\_source\_file**: `data/scripts/projectiles/destruction.lua` - Specifies the script file that controls the projectile's logic.
*   **execute\_every\_n\_frame**: `1` - The script will execute every frame, allowing for real-time updates and complex behaviors.

### AudioComponent
This component manages the sound effects associated with the projectile.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **event\_root**: `player_projectiles/destruction` - The root event name for sounds related to this projectile.
*   **set\_latest\_event\_position**: `1` - Ensures the sound plays at the projectile's current position.

## Inheritance

*   **InheritTransformComponent**: This indicates the projectile inherits transform properties, likely position, rotation, and scale, from its parent or creator.