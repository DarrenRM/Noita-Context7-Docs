---
title: Meteor Rain Projectile
category: entities/misc
---

# Meteor Rain Projectile

This entity defines the projectile used for the "Meteor Rain" effect in Noita. It's a simple projectile with a Lua script that handles its behavior.

## Key Components

### LuaComponent
This is the core of the projectile's functionality.

*   **`script_source_file`**: `data/scripts/projectiles/meteor_rain.lua` - Specifies the Lua script that controls the projectile's actions.
*   **`execute_every_n_frame`**: `30` - The script will execute its logic every 30 frames.

### LifetimeComponent
Determines how long the projectile exists.

*   **`lifetime`**: `600` - The projectile will exist for 600 frames before being removed.

## Inheritance

*   **`InheritTransformComponent`**: This component indicates that the projectile inherits transform properties (like position and rotation) from its parent or creator.

## Tags

*   **`player_projectile`**: This tag suggests that this projectile is typically spawned by the player.