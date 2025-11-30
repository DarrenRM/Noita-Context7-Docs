---
title: Mestari Secret Biome Configuration
category: biome
---

# Mestari Secret Biome Configuration

This file defines the configuration and spawning logic for the "Mestari Secret" biome in Noita. It primarily focuses on loading a specific pixel scene and defining functions for spawning various entities within this biome.

## Core Configuration

*   **`CHEST_LEVEL = 3`**: Indicates the general difficulty or tier of chests found within this biome.

## Initialization Function

*   **`init( x, y, w, h )`**: This is the primary function called when the biome is initialized.
    *   It loads the visual and background assets for the "secret lab" pixel scene.
    *   **`LoadPixelScene( "data/biome_impl/secret_lab.png", "data/biome_impl/secret_lab_visual.png", x, y, "data/biome_impl/secret_lab_background.png", true )`**: This is the key function call that defines the visual layout and elements of the biome.

## Spawn Functions (Unused/Placeholder)

The following functions are defined but appear to be empty or are not actively used in the provided snippet for this specific biome. They represent potential hooks for spawning different types of entities.

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

## Specific Spawn Function

*   **`spawn_orb(x, y)`**: This function is designed to spawn specific entities.
    *   **`EntityLoad( "data/entities/animals/boss_wizard/boss_wizard.xml", x + 20, y )`**: Spawns the "boss\_wizard" entity.
    *   Commented-out lines suggest potential for spawning books or music energy entities.

## Dependencies

*   `dofile_once("data/scripts/director_helpers.lua")`
*   `dofile_once("data/scripts/biome_scripts.lua")`
*   `dofile_once("data/scripts/lib/utilities.lua")`