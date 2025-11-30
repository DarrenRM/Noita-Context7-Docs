---
title: Orb Room 06 Configuration
category: scripts
---

# Orb Room 06 Configuration

This document details the configuration for a specific orb room biome in Noita, identified as `orbroom_06.lua`. It focuses on the entities and visual elements loaded when this biome is generated.

## Core Biome Settings

*   **CHEST\_LEVEL**: `3` - Indicates the general difficulty or tier associated with this orb room.

## Initialization and Loading

The `init` function is responsible for setting up the visual and structural aspects of the orb room.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/orbroom.png", "data/biome_impl/orbroom_visual.png", x, y, "data/biome_impl/orbroom_background.png", true )
end
```

*   **`LoadPixelScene`**: This function loads the visual assets for the orb room.
    *   `data/biome_impl/orbroom.png`: The primary pixel scene defining the room's layout.
    *   `data/biome_impl/orbroom_visual.png`: Additional visual details or overlays.
    *   `data/biome_impl/orbroom_background.png`: The background image for the room.
    *   `true`: Likely indicates that this scene should be rendered.

## Orb and Associated Entity Spawning

The `spawn_orb` function handles the placement of the main orb and other related items within the room.

```lua
function spawn_orb(x, y)
	EntityLoad( "data/entities/items/orbs/orb_06.xml", x, y )
	EntityLoad( "data/entities/items/books/book_06.xml", x - 30, y + 40 )
	EntityLoad( "data/entities/misc/music_energy_000.xml", x, y - 10 )

	spawn_material_checker( x - 197, y - 11, "blood_worm", "data/scripts/biomes/orbrooms/orbroom_shared.lua", "data/particles/image_emitters/orbrooms/05_01.xml", x, y - 100 )
	spawn_material_checker( x + 198, y - 11, "blood_worm", "data/scripts/biomes/orbrooms/orbroom_shared.lua", "data/particles/image_emitters/orbrooms/05_01.xml", x, y - 100 )

	EntityLoad( "data/entities/particles/gold_dust.xml", x, y )
end
```

### Key Entities Loaded:

*   **`data/entities/items/orbs/orb_06.xml`**: The primary orb for this room.
*   **`data/entities/items/books/book_06.xml`**: A book, likely providing a spell or lore.
*   **`data/entities/misc/music_energy_000.xml`**: A music-related entity, potentially affecting the room's ambiance.
*   **`data/entities/particles/gold_dust.xml`**: A particle effect, adding visual flair.

### `spawn_material_checker` Usage:

This function is called twice, suggesting it's used to create specific environmental effects or triggers.

*   **Parameters**:
    *   `x`, `y`: Position of the checker.
    *   `"blood_worm"`: Likely a material or entity type associated with the checker.
    *   `"data/scripts/biomes/orbrooms/orbroom_shared.lua"`: A shared script file.
    *   `"data/particles/image_emitters/orbrooms/05_01.xml"`: A particle emitter configuration.
    *   `x`, `y - 100`: Further positional parameters, possibly for the emitter's origin.

## Unused/Placeholder Functions

The following functions are defined but appear to be empty or are placeholders, indicating they are not actively used in this specific orb room configuration.

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