---
title: Player Projectile - All Rockets
category: entities
---

---

# Player Projectile - All Rockets

This entity defines a generic player projectile, specifically designed to be used as a base for various rocket-like projectiles. It leverages a Lua script for its core behavior and includes components for lifetime and audio.

## Key Components

### LuaComponent

This component dictates the projectile's behavior through an external Lua script.

*   **`script_source_file`**: `data/scripts/projectiles/all_rockets.lua` - The primary script governing the projectile's logic.
*   **`execute_every_n_frame`**: `-1` - Indicates that the script does not execute on a fixed frame interval.
*   **`execute_on_added`**: `1` - The script's `execute_on_added` function will be called once when the projectile is spawned.

### LifetimeComponent

Determines how long the projectile exists before being destroyed.

*   **`lifetime`**: `2` - The projectile will exist for 2 seconds.

### AudioComponent

Manages the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/all_spell` - The root event name for player projectile sounds.
*   **`set_latest_event_position`**: `1` - Ensures the sound event plays at the projectile's current position.

## Entity Tags

*   **`projectile_player`**: Identifies this entity as a projectile fired by the player.