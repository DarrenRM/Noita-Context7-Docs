---
title: Solid Wall Tower Biome Configuration
category: biome
---

# Solid Wall Tower Biome Configuration

This document outlines the configuration for the "Solid Wall Tower" biome in Noita, focusing on its entity spawning and initialization logic.

## Core Configuration

*   **`CHEST_LEVEL`**: `3` - Indicates the general difficulty or loot tier associated with this biome.

## Initialization Function (`init`)

The `init` function is called when the biome is loaded. It is responsible for setting up the initial state of the biome.

### Key Actions:

*   **`EntityLoad( "data/entities/misc/rock_curse.xml", x + 256, y + 256 )`**: This is the primary action performed during initialization. It loads a specific entity, `rock_curse.xml`, at an offset position within the biome's spawn area. This suggests the biome is designed to immediately introduce a "curse" element.

## Unused Spawn Functions

The following functions are defined but appear to be unused or unimplemented within this specific biome script. They are likely placeholders or intended for use in other biome configurations.

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
*   `spawn_orb( x, y )`

## Dependencies

This script relies on several utility and helper files:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`