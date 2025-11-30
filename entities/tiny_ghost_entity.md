---
title: Tiny Ghost Entity
category: entities
---

# Tiny Ghost Entity

This document details the configuration of the "Tiny Ghost" entity in Noita, focusing on its visual representation, behavior scripts, and audio components.

## Core Components

The Tiny Ghost entity is defined by several key components that dictate its appearance, actions, and sound.

### SpriteComponent

This component defines the visual appearance of the Tiny Ghost.

*   **`image_file`**: Specifies the XML file containing the sprite's graphical data.
    *   `data/projectiles_gfx/tiny_ghost.xml`

### LuaComponent (Behavior Scripts)

Multiple `LuaComponent`s are used to define the entity's behavior. Each script is executed at a specific interval.

*   **`script_source_file`**: `data/scripts/animals/tiny_ghost_shoot.lua`
    *   **`execute_every_n_frame`**: `25` (This script runs every 25 frames, likely for shooting or attack logic).
*   **`script_source_file`**: `data/scripts/animals/tiny_ghost_move.lua`
    *   **`execute_every_n_frame`**: `1` (This script runs every frame, suggesting it handles continuous movement or AI updates).
*   **`script_enabled_changed`**: `data/scripts/animals/tiny_ghost_enabled_changed.lua`
    *   **`execute_every_n_frame`**: `-1` (This script is likely triggered by changes in the entity's enabled state, not on a fixed frame interval).

### AudioComponent

This component handles general audio events for the Tiny Ghost.

*   **`file`**: `data/audio/Desktop/animals.bank` (The audio bank containing the sound effects).
*   **`event_root`**: `animals/tiny_ghost` (The base event name for sounds associated with this entity).

### AudioLoopComponent

This component manages a looping sound effect for the Tiny Ghost.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_name`**: `animals/tiny_ghost/movement_loop` (The specific looping sound event).
*   **`set_speed_parameter`**: `1` (Likely links the sound's playback speed to an in-game parameter).
*   **`auto_play`**: `1` (The sound loop starts automatically when the entity is active).

### LifetimeComponent

This component determines how long the Tiny Ghost entity will exist.

*   **`lifetime`**: `28800` (The entity will persist for 28800 frames, approximately 8 minutes at 60 FPS).

## Entity Tags

*   **`tiny_ghost_event`**: This tag likely categorizes the entity for game logic or event handling.