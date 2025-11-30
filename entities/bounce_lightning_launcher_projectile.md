---
title: Bounce Lightning Launcher Projectile
category: entities
---

# Bounce Lightning Launcher Projectile

This document describes the configuration for the "Bounce Lightning Launcher" projectile entity in Noita.

## Core Components

### LuaComponent
This component defines the projectile's behavior through a Lua script.

*   **`script_source_file`**: `data/scripts/projectiles/bounce_lightning_launch.lua` - Specifies the Lua script responsible for the projectile's logic.
*   **`execute_on_added`**: `1` - Indicates that the script should execute immediately when the projectile is added to the game.

### AudioComponent
This component handles the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the projectile's sound events.
*   **`event_root`**: `player_projectiles/bullet_lightning` - The root event name for the projectile's sound effects.