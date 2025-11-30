---
title: Mass Polymorph Projectile
category: entities
---

# Mass Polymorph Projectile

This entity defines the "Mass Polymorph" projectile used in Noita. It's a player-fired projectile that triggers a polymorph effect.

## Key Components

### LuaComponent
This component links the projectile to its behavior script.

*   **script_source_file**: `data/scripts/projectiles/mass_polymorph.lua` - Specifies the Lua script that governs the projectile's logic.
*   **execute_every_n_frame**: `1` - The script will execute every frame.

### AudioComponent
This component handles the sound effects associated with the projectile.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **event_root**: `player_projectiles/destruction` - The root event for player projectile destruction sounds.
*   **set_latest_event_position**: `1` - Ensures the sound plays at the projectile's current position.

### InheritTransformComponent
This is an empty component, likely used to inherit transform properties from its parent or a base entity.