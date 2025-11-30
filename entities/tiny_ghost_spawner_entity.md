---
title: Tiny Ghost Spawner Entity
category: entities
---

# Tiny Ghost Spawner Entity

This entity is responsible for spawning and managing "tiny ghosts" that attach to and harass nearby enemies. It acts as a persistent spawner that periodically creates these ghost entities.

## Key Components

### LifetimeComponent
*   **lifetime**: `1200` - The duration in frames this spawner entity will exist.

### LuaComponent (Spawner Logic)
*   **script_source_file**: `data/scripts/animals/tiny_ghost_spawn.lua` - The primary script that handles the logic for spawning tiny ghosts.
*   **execute_every_n_frame**: `60` - The spawner will attempt to spawn a tiny ghost every 60 frames.

### Nested Entity (The Tiny Ghost)
This section defines the properties and behavior of the tiny ghost entity that is spawned.

#### SpriteComponent
*   **image_file**: `data/projectiles_gfx/tiny_ghost.xml` - Specifies the graphical representation of the tiny ghost.
*   **_enabled**: `0` - This sprite is initially disabled, likely enabled by a script when the ghost is active.

#### LuaComponent (Ghost Behavior Scripts)
These components define the various behaviors of the spawned tiny ghost. They are initially disabled (`_enabled="0"`) and are activated by other scripts.

*   **script_source_file**: `data/scripts/animals/tiny_ghost_shoot_nerfed.lua`
    *   **execute_every_n_frame**: `110` - Controls the firing rate of the tiny ghost's projectiles.
*   **script_source_file**: `data/scripts/animals/tiny_ghost_move.lua`
    *   **execute_every_n_frame**: `1` - Controls the movement logic of the tiny ghost, executing every frame for smooth motion.
*   **script_enabled_changed**: `data/scripts/animals/tiny_ghost_enabled_changed.lua`
    *   **execute_every_n_frame**: `-1` - This script is likely triggered when the ghost's enabled state changes.

#### AudioComponent
*   **file**: `data/audio/Desktop/animals.bank` - The audio bank containing sounds for the tiny ghost.
*   **event_root**: `animals/tiny_ghost` - The root event name for general tiny ghost sounds.
*   **_enabled**: `0` - Audio is initially disabled.

#### AudioLoopComponent
*   **file**: `data/audio/Desktop/animals.bank` - The audio bank for looping sounds.
*   **event_name**: `animals/tiny_ghost/movement_loop` - The specific event for the tiny ghost's movement sound loop.
*   **set_speed_parameter**: `1` - Indicates that the playback speed of the loop can be controlled.
*   **auto_play**: `1` - The movement loop will start playing automatically when the component is enabled.
*   **_enabled**: `0` - Audio loop is initially disabled.