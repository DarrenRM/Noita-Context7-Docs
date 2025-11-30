---
title: Orb Room 05 - Wand Cave
category: biome
---

# Orb Room 05 - Wand Cave

This script defines the content and spawning logic for a specific orb room biome in Noita, designated as "orbroom_05". This room is characterized by its association with wand-related elements.

## Core Functionality

The primary purpose of this script is to register a spawn function for the orb room and then define the `init` function which loads the visual and background assets for the room. The `spawn_orb` function is crucial for populating the room with specific items and effects.

## Key Attributes and Elements

### `CHEST_LEVEL`

*   **Value:** `3`
*   **Description:** Indicates the difficulty or tier of chests that might be associated with this biome. A higher number generally implies better loot.

### `RegisterSpawnFunction`

*   **Function:** `RegisterSpawnFunction( 0xffffeedd, "init" )`
*   **Description:** Registers the `init` function to be called when this biome is to be spawned. The `0xffffeedd` likely represents a unique identifier for this biome.

### `init( x, y, w, h )`

*   **Description:** This function is responsible for loading the visual representation of the orb room.
*   **Key Actions:**
    *   `LoadPixelScene("data/biome_impl/orbroom.png", "data/biome_impl/orbroom_visual.png", x, y, "data/biome_impl/orbroom_background.png", true)`: Loads the main visual layer, a visual overlay, and the background for the orb room at the specified coordinates (`x`, `y`).

### `spawn_orb(x, y)`

*   **Description:** This function populates the orb room with specific entities and effects when the orb is spawned.
*   **Key Entities Loaded:**
    *   `EntityLoad("data/entities/items/orbs/orb_05.xml", x, y)`: Spawns the primary orb for this room.
    *   `EntityLoad("data/entities/items/books/book_05.xml", x - 30, y + 40)`: Spawns a specific book, likely related to the orb's theme.
    *   `EntityLoad("data/entities/misc/music_energy_000.xml", x, y - 10)`: Adds a music or atmospheric effect.
    *   `EntityLoad("data/entities/particles/gold_dust.xml", x, y)`: Spawns decorative gold dust particles.
*   **Key Effects Spawned:**
    *   `spawn_material_checker(...)`: Two instances of this function are called, likely to create specific material effects (e.g., sand) around the orb, potentially for visual flair or interaction. These use specific particle emitter configurations (`data/particles/image_emitters/orbrooms/07_03.xml`).

## Unused/Placeholder Functions

The script includes numerous empty functions (e.g., `spawn_small_enemies`, `spawn_big_enemies`, `spawn_items`, etc.). These are likely placeholders or remnants from a more general orb room template and do not contribute to the functionality of this specific biome.

## Dependencies

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`
*   `data/scripts/biomes/orbrooms/orbroom_shared.lua`