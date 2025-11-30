---
title: Shield Ghost Entity
category: entities
---

# Shield Ghost Entity

This document describes the configuration for the "Shield Ghost" entity in Noita, focusing on its visual representation, scripting behavior, and audio components.

## Core Components

### SpriteComponent

Defines the visual appearance of the Shield Ghost.

*   **`image_file`**: Specifies the sprite definition file.
    *   `data/projectiles_gfx/shield_ghost.xml`

### LuaComponent (Shooting Behavior)

Handles the entity's projectile firing logic.

*   **`script_source_file`**: Path to the Lua script responsible for shooting.
    *   `data/scripts/animals/shield_ghost_shoot.lua`
*   **`execute_every_n_frame`**: Controls the firing frequency.
    *   `70` frames

### LuaComponent (Movement Behavior)

Manages the entity's movement.

*   **`script_source_file`**: Path to the Lua script for movement.
    *   `data/scripts/animals/tiny_ghost_move.lua`
*   **`execute_every_n_frame`**: Sets the movement update interval.
    *   `1` frame

### LuaComponent (Enabled/Disabled State)

Handles logic when the entity's enabled state changes.

*   **`script_enabled_changed`**: Path to the Lua script for state changes.
    *   `data/scripts/animals/tiny_ghost_enabled_changed.lua`
*   **`execute_every_n_frame`**: Set to `-1` indicating it's event-driven.

### AudioComponent

Configures general audio events for the entity.

*   **`file`**: The audio bank file.
    *   `data/audio/Desktop/animals.bank`
*   **`event_root`**: The root event name for this entity's sounds.
    *   `animals/tiny_ghost`

### AudioLoopComponent

Manages a continuous looping sound for the entity.

*   **`file`**: The audio bank file.
    *   `data/audio/Desktop/animals.bank`
*   **`event_name`**: The specific looping sound event.
    *   `animals/tiny_ghost/movement_loop`
*   **`set_speed_parameter`**: `1` indicates the sound's speed will be controlled by game parameters.
*   **`auto_play`**: `1` means the sound starts automatically when the entity is spawned.

### LifetimeComponent

Determines how long the entity persists.

*   **`lifetime`**: The duration in frames before the entity despawns.
    *   `28800` frames (equivalent to 8 minutes in game time)