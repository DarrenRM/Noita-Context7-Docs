---
title: Orb Room 02 Biome Configuration
category: biome
---

# Orb Room 02 Biome Configuration

This document details the configuration for `orbroom_02.lua`, a specific type of orb room biome in Noita. This biome is located within the "frozen vault" area.

## Core Biome Properties

*   **`CHEST_LEVEL`**: `3` - Indicates the general tier or difficulty level associated with chests found in this biome.
*   **Location**: Frozen Vault

## Initialization and Scene Loading

The `init` function is responsible for setting up the visual and structural elements of the orb room.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/orbroom.png", "data/biome_impl/orbroom_visual.png", x, y, "data/biome_impl/orbroom_background.png", true )
end
```

*   **`LoadPixelScene`**: This function loads the primary visual assets for the biome.
    *   `data/biome_impl/orbroom.png`: The base pixel data defining the room's layout.
    *   `data/biome_impl/orbroom_visual.png`: Defines visual effects and details within the room.
    *   `data/biome_impl/orbroom_background.png`: The background image for the biome.
    *   `true`: Likely indicates that the scene should be loaded with collision data.

## Orb Spawning Logic

The `spawn_orb` function defines the specific entities and effects that appear when the orb room is generated.

```lua
function spawn_orb(x, y)
	EntityLoad( "data/entities/items/orbs/orb_02.xml", x, y )
	EntityLoad( "data/entities/items/books/book_02.xml", x - 30, y + 40 )
	EntityLoad( "data/entities/misc/music_energy_000.xml", x, y - 10 )

	spawn_material_checker( x - 197, y - 11, "blood", "data/scripts/biomes/orbrooms/orbroom_shared.lua", "data/particles/image_emitters/orbrooms/07_01.xml", x, y - 100 )
	spawn_material_checker( x + 198, y - 11, "blood", "data/scripts/biomes/orbrooms/orbroom_shared.lua", "data/particles/image_emitters/orbrooms/07_01.xml", x, y - 100 )

	EntityLoad( "data/entities/particles/gold_dust.xml", x, y )
end
```

### Key Entities Spawned:

*   **`data/entities/items/orbs/orb_02.xml`**: The primary orb item for this room.
*   **`data/entities/items/books/book_02.xml`**: A spell book, likely providing a specific spell.
*   **`data/entities/misc/music_energy_000.xml`**: A musical entity, potentially affecting the ambient sound.
*   **`data/entities/particles/gold_dust.xml`**: A particle effect, adding visual flair.

### Material Checkers and Effects:

The `spawn_material_checker` function is used to create specific environmental effects.

*   **Left Checker**:
    *   Position: `x - 197, y - 11`
    *   Material: `"blood"`
    *   Script: `"data/scripts/biomes/orbrooms/orbroom_shared.lua"`
    *   Particle Emitter: `"data/particles/image_emitters/orbrooms/07_01.xml"`
    *   Target Position: `x, y - 100`
*   **Right Checker**:
    *   Position: `x + 198, y - 11`
    *   Material: `"blood"`
    *   Script: `"data/scripts/biomes/orbrooms/orbroom_shared.lua"`
    *   Particle Emitter: `"data/particles/image_emitters/orbrooms/07_01.xml"`
    *   Target Position: `x, y - 100`

These material checkers likely interact with the "blood" material and use the specified particle emitter to create dynamic visual effects or environmental hazards/features.

## Unused Spawn Functions

The following functions are defined but appear to be empty or unused in this specific biome script. They are likely placeholders or inherited from a more general template.

*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `spawn_lamp`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`
*   `spawn_wands`