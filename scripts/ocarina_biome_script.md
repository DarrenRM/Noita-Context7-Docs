---
title: Ocarina Biome Script
category: scripts
---

# Ocarina Biome Script

This script defines the behavior and content for the "Ocarina" biome in Noita. It primarily handles the loading of the biome's visual representation and the spawning of specific items.

## Core Functionality

### `init(x, y, w, h)`

This function is called when the Ocarina biome is initialized.

*   **Purpose:** Loads the visual assets for the Ocarina biome.
*   **Key Action:** `LoadPixelScene("data/biome_impl/ocarina.png", "", x, y, "", true)` - This loads the pixel art scene that defines the layout and appearance of the Ocarina biome.

### `spawn_secret(x, y)`

This function is responsible for spawning special items within the Ocarina biome, likely in a secret area.

*   **Purpose:** Spawns a sequence of "Ocarina Cards" and a flute.
*   **Key Actions:**
    *   Iterates through a predefined list of `ocarina_cards` (e.g., "OCARINA_A", "OCARINA_B", etc.).
    *   For each card, it uses `CreateItemActionEntity` to spawn the corresponding item at calculated positions relative to the `x` and `y` coordinates.
    *   Spawns a "flute" item using `EntityLoad("data/entities/items/flute.xml", x, y - 64)`.

## Registered Spawn Functions

The script registers specific functions to be called at certain points during gameplay or biome generation.

*   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Associates the `init` function with a specific internal identifier, likely for biome initialization.
*   `RegisterSpawnFunction( 0xff31d0b4, "spawn_secret" )`: Associates the `spawn_secret` function with another identifier, likely for triggering secret content spawning.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or intended for future expansion.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`
*   `spawn_wands( x, y )`
*   `spawn_orb(x, y)`