---
title: All Deathcrosses Projectile
category: entities
---

---

# All Deathcrosses Projectile

This entity defines the behavior and properties of the "All Deathcrosses" projectile in Noita.

## Core Components

### LuaComponent
This component links the projectile to its associated Lua script, which handles its dynamic behavior.

*   **script_source_file**: `data/scripts/projectiles/all_deathcrosses.lua` - The path to the script that controls the projectile's logic.
*   **execute_every_n_frame**: `-1` - Indicates that the script does not execute on a fixed frame interval.
*   **execute_on_added**: `1` - The script's `execute_on_added` function is called when the projectile is spawned.

### LifetimeComponent
This component determines how long the projectile exists before being destroyed.

*   **lifetime**: `2` - The projectile will exist for 2 seconds.

### AudioComponent
This component manages the sound effects associated with the projectile.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the projectile's sounds.
*   **event_root**: `player_projectiles/all_spell` - The root event name for player projectile sounds.
*   **set_latest_event_position**: `1` - The sound event will be positioned at the projectile's latest known position.