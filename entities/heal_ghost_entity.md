---
title: Heal Ghost Entity
category: entities
---

# Heal Ghost Entity

This document describes the `heal_ghost.xml` entity, which represents a "Heal Ghost" in Noita. This entity is designed to interact with the game world through its sprite, Lua scripts, and audio components.

## Core Components

### SpriteComponent

This component defines the visual appearance of the Heal Ghost.

*   **`image_file`**: Specifies the sprite definition file.
    *   `data/projectiles_gfx/heal_ghost.xml`

### LuaComponent (Scripting)

Multiple `LuaComponent`s are used to define the behavior and logic of the Heal Ghost.

*   **Script 1 (Shooting Logic)**
    *   **`script_source_file`**: `data/scripts/animals/heal_ghost_shoot.lua`
    *   **`execute_every_n_frame`**: `70` (This script executes every 70 frames, suggesting a periodic action like shooting or a specific behavior update.)

*   **Script 2 (Movement Logic)**
    *   **`script_source_file`**: `data/scripts/animals/tiny_ghost_move.lua`
    *   **`execute_every_n_frame`**: `1` (This script executes every frame, indicating continuous movement or constant state updates.)

*   **Script 3 (Enabled/Disabled State)**
    *   **`script_source_file`**: `data/scripts/animals/tiny_ghost_enabled_changed.lua`
    *   **`execute_every_n_frame`**: `-1` (This indicates the script is triggered by an event rather than a fixed frame rate, likely when the entity's enabled state changes.)

### AudioComponent

This component handles sound effects for the Heal Ghost.

*   **`file`**: `data/audio/Desktop/animals.bank` (The audio bank containing the sound events.)
*   **`event_root`**: `animals/tiny_ghost` (The base path for sound events related to this entity.)

### AudioLoopComponent

This component manages a looping sound for the Heal Ghost.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_name`**: `animals/tiny_ghost/movement_loop` (The specific sound event for the movement loop.)
*   **`set_speed_parameter`**: `1` (Likely links the loop's playback speed to an in-game parameter.)
*   **`auto_play`**: `1` (The sound loop starts automatically when the entity is spawned.)

### LifetimeComponent

This component defines how long the Heal Ghost entity persists in the game.

*   **`lifetime`**: `28800` (The entity will exist for 28800 frames before being removed.)