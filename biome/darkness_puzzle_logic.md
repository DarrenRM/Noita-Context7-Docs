---
title: Darkness Puzzle Logic
category: biome
---

# Darkness Puzzle Logic

This script defines the logic for a "darkness puzzle" within Noita's biomes. When a specific condition is met (implied by `material_area_checker_success`), it triggers a series of events related to darkness and magical elements.

## Key Functions

### `material_area_checker_success( pos_x, pos_y )`

This function is called when the conditions for the darkness puzzle are met. It handles the spawning of visual effects, sound, and other entities.

#### Core Actions:

*   **Spawn Magical Symbol:**
    *   `EntityLoad( "data/entities/particles/image_emitters/magical_symbol.xml", x, y )`
    *   Loads a particle effect representing a magical symbol at the puzzle's location.

*   **Play Sound Effect:**
    *   `GamePlaySound( "data/audio/Desktop/projectiles.snd", "player_projectiles/crumbling_earth/create", x, y )`
    *   Plays a specific sound effect, likely related to crumbling earth or creation, at the puzzle's location.

*   **Spawn Darkness Chest:**
    *   `EntityLoad( "data/biome_impl/static_tile/chest_darkness.xml", x, y )`
    *   Loads a special "darkness chest" entity. This chest is likely tied to the puzzle's reward or progression.

*   **Spawn Music Energy:**
    *   `EntityLoad( "data/entities/misc/music_energy_100.xml", x, y )`
    *   Loads an entity that provides 100 units of "music energy," potentially influencing the game's soundtrack or ambiance.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: This line ensures that utility functions are loaded, though specific utilities used within this snippet are not detailed here.

## Summary

The `puzzle_logic_darkness.lua` script acts as a trigger for a specific in-game event. Upon successful completion of an implied check, it visually and audibly marks the event with a magical symbol and sound, provides a unique "darkness chest," and adds a significant amount of "music energy" to the game environment.