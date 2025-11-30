---
title: Orb Room 07 Configuration
category: scripts
---

# Orb Room 07 Configuration

This document details the configuration for Orb Room 07, a specific biome element within Noita. It focuses on the entities and visual elements loaded when this orb room is generated.

## Core Functionality

The primary purpose of this script is to register the generation of Orb Room 07 and define its contents.

### `RegisterSpawnFunction`

-   **`0xffffeedd`**: This is a unique identifier or "magic number" associated with this specific orb room type.
-   **`"init"`**: This function is called when the orb room is to be spawned.

## Initialization (`init` function)

This function is responsible for setting up the visual and structural elements of the orb room.

### Visual Loading

-   **`LoadPixelScene`**: This function loads the visual representation of the orb room.
    -   `"data/biome_impl/orbroom.png"`: The main texture for the orb room.
    -   `"data/biome_impl/orbroom_visual.png"`: Additional visual details.
    -   `x`, `y`: The coordinates where the orb room is placed.
    -   `"data/biome_impl/orbroom_background.png"`: The background image for the orb room.
    -   `true`: Likely indicates whether to use a parallax effect or similar background layering.

### Structural Elements

-   **`EntityLoad`**: Loads specific entities into the game world.
    -   `"data/entities/misc/orb_07_pitcheck_b.xml"`: Loaded at `x - 64, y + 256`. This entity likely serves a role in checking the pit or terrain around the orb room.

## Orb Spawning (`spawn_orb` function)

This function defines the items and special effects that appear when the orb itself is spawned within the room.

### Key Entities Loaded

-   **`EntityLoad`**:
    -   `"data/entities/items/orbs/orb_07.xml"`: The primary orb entity for this room.
    -   `"data/entities/misc/orb_07_pitcheck_a.xml"`: Another pit-checking entity, likely a counterpart to `orb_07_pitcheck_b`.
    -   `"data/entities/items/books/book_07.xml"`: A specific book associated with this orb room.
    -   `"data/entities/misc/music_energy_000.xml"`: Likely triggers a specific music track or sound effect.
    -   `"data/entities/particles/gold_dust.xml"`: Adds a visual particle effect of gold dust.

### Material Checkers

These entities are responsible for checking the material in specific locations, likely for gameplay mechanics related to the orb.

-   **`spawn_material_checker`**:
    -   **Left Checker**:
        -   Position: `x - 197, y - 11`
        -   Material to check: `"slime"`
        -   Shared script: `"data/scripts/biomes/orbrooms/orbroom_shared.lua"`
        -   Particle emitter: `"data/particles/image_emitters/orbrooms/05_02.xml"`
        -   Target coordinates for particles: `x, y - 100`
    -   **Right Checker**:
        -   Position: `x + 198, y - 11`
        -   Material to check: `"slime"`
        -   Shared script: `"data/scripts/biomes/orbrooms/orbroom_shared.lua"`
        -   Particle emitter: `"data/particles/image_emitters/orbrooms/05_02.xml"`
        -   Target coordinates for particles: `x, y - 100`

## Unused Functions

The following functions are defined but appear to be empty or unused within this specific script. They are likely placeholders or inherited from a more general orb room template.

-   `spawn_small_enemies`
-   `spawn_big_enemies`
-   `spawn_items`
-   `spawn_props`
-   `spawn_props2`
-   `spawn_props3`
-   `spawn_lamp`
-   `load_pixel_scene`
-   `load_pixel_scene2`
-   `spawn_unique_enemy`
-   `spawn_unique_enemy2`
-   `spawn_unique_enemy3`
-   `spawn_ghostlamp`
-   `spawn_candles`
-   `spawn_potions`
-   `spawn_wands`