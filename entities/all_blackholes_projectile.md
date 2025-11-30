---
title: All Blackholes Projectile
category: entities
---

# All Blackholes Projectile

This entity defines the properties for the "All Blackholes" projectile in Noita. It's a player-created projectile with specific behaviors and effects.

## Key Components

### LuaComponent
This component links the projectile to its associated Lua script, which handles its unique behavior.

*   **script_source_file**: `data/scripts/projectiles/all_blackholes.lua` - The primary script governing the projectile's actions.
*   **execute_every_n_frame**: `-1` - Indicates that the script logic is not executed on a fixed frame interval.
*   **execute_on_added**: `1` - The script logic is executed once when the projectile is first created.

### LifetimeComponent
Determines how long the projectile exists before being destroyed.

*   **lifetime**: `2` - The projectile will exist for 2 seconds.

### AudioComponent
Manages the sound effects associated with the projectile.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the projectile's sound events.
*   **event_root**: `player_projectiles/all_spell` - The root event name for player projectile sounds.
*   **set_latest_event_position**: `1` - Ensures the sound event plays at the projectile's current position.