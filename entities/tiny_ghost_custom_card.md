---
title: Tiny Ghost Custom Card
category: entities
---

# Tiny Ghost Custom Card

This entity defines the "Tiny Ghost" custom card in Noita, allowing players to summon and control a spectral companion.

## Core Components

### Base Entity (`base_custom_card.xml`)
This establishes the entity as a custom card, providing fundamental properties for its interaction within the game's UI and inventory.

*   **`SpriteComponent`**: Defines the visual representation of the card when viewed in the inventory or UI.
    *   `image_file`: `data/ui_gfx/gun_actions/tiny_ghost.png`
*   **`ItemActionComponent`**: Assigns a unique action ID to the card, enabling its functionality when used.
    *   `action_id`: `TINY_GHOST`

### In-Hand Functionality

These components dictate the behavior and appearance of the Tiny Ghost when it's actively held or summoned by the player.

*   **`SpriteComponent`**: Controls the visual appearance of the Tiny Ghost itself.
    *   `image_file`: `data/projectiles_gfx/tiny_ghost.xml`
*   **`LuaComponent` (Shooting)**: Manages the ghost's projectile firing behavior.
    *   `script_source_file`: `data/scripts/animals/tiny_ghost_shoot.lua`
    *   `execute_every_n_frame`: `25` (Fires approximately every 25 frames)
*   **`LuaComponent` (Movement)**: Handles the ghost's movement logic.
    *   `script_source_file`: `data/scripts/animals/tiny_ghost_move.lua`
    *   `execute_every_n_frame`: `1` (Updates movement every frame for smooth animation)
*   **`LuaComponent` (Enabled Change)**: Manages state changes when the ghost is enabled or disabled.
    *   `script_enabled_changed`: `data/scripts/animals/tiny_ghost_enabled_changed.lua`
    *   `execute_every_n_frame`: `-1` (Indicates this script runs on specific events, not on a fixed frame rate)

## Audio Components

### Sound Effects
These components manage the audio cues associated with the Tiny Ghost.

*   **`AudioComponent`**: Sets up the root event bank for the ghost's sounds.
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_root`: `animals/tiny_ghost`
*   **`AudioLoopComponent`**: Manages the looping sound for the ghost's movement.
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_name`: `animals/tiny_ghost/movement_loop`
    *   `set_speed_parameter`: `1` (Likely links movement speed to audio pitch/volume)
    *   `auto_play`: `1` (Starts playing automatically when the ghost is active)