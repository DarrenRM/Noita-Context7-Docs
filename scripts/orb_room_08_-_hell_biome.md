---
title: Orb Room 08 - Hell Biome
category: scripts
---

# Orb Room 08 - Hell Biome

This script defines the configuration and spawning logic for a specific orb room biome located in the Hell area of Noita. It leverages shared orb room functionalities and customizes the visual and entity placement for this particular variant.

## Core Functionality

This script is responsible for:
- **Loading the visual representation** of the orb room.
- **Spawning the primary orb** and associated items.
- **Placing environmental elements** and particle effects.

## Key Attributes and Elements

### Biome Location
- **Location:** Hell

### Chest Level
- `CHEST_LEVEL = 3`: Indicates the difficulty or tier of chests that might appear in this biome.

### Core Dependencies
- `dofile_once("data/scripts/director_helpers.lua")`
- `dofile_once("data/scripts/biome_scripts.lua")`
- `dofile_once("data/scripts/lib/utilities.lua")`
- `dofile( "data/scripts/biomes/orbrooms/orbroom_shared.lua" )`: Imports shared logic for all orb rooms.

### Initialization Function
- `init( x, y, w, h )`: This function is called when the biome is initialized.
    - `LoadPixelScene( "data/biome_impl/orbroom.png", "data/biome_impl/orbroom_visual.png", x, y, "data/biome_impl/orbroom_background.png", true )`: Loads the visual assets for the orb room, including its main image, visual overlay, and background.

### Orb and Item Spawning
- `spawn_orb(x, y)`: This function handles the placement of the main orb and related entities.
    - `EntityLoad( "data/entities/items/orbs/orb_08.xml", x, y )`: Spawns the specific orb for this room (orb_08).
    - `EntityLoad( "data/entities/items/books/book_08.xml", x - 30, y + 40 )`: Spawns a related book item.
    - `EntityLoad( "data/entities/misc/music_energy_000.xml", x, y - 10 )`: Spawns a music entity.
    - `spawn_material_checker(...)`: Two instances of this function are called to spawn material checkers, likely for environmental effects or interactions. These are configured with `magic_liquid_polymorph` and specific particle emitters.
    - `EntityLoad( "data/entities/particles/gold_dust.xml", x, y )`: Spawns gold dust particles for visual flair.

### Unused/Placeholder Functions
The following functions are defined but have empty implementations, suggesting they are either placeholders for future development or not utilized in this specific orb room variant:
- `spawn_small_enemies( x, y )`
- `spawn_big_enemies( x, y )`
- `spawn_items( x, y )`
- `spawn_props( x, y )`
- `spawn_props2( x, y )`
- `spawn_props3( x, y )`
- `spawn_lamp( x, y )`
- `load_pixel_scene( x, y )`
- `load_pixel_scene2( x, y )`
- `spawn_unique_enemy( x, y )`
- `spawn_unique_enemy2( x, y )`
- `spawn_unique_enemy3( x, y )`
- `spawn_ghostlamp( x, y )`
- `spawn_candles( x, y )`
- `spawn_potions( x, y )`
- `spawn_wands( x, y )`

## Summary

Orb Room 08 is a specialized biome within the Hell area, characterized by its unique orb (`orb_08.xml`) and associated items. It relies heavily on shared orb room scripts for its core mechanics but defines its own visual assets and specific entity placements, including material checkers and decorative particles. Many standard enemy and item spawning functions are present but remain unimplemented in this script.