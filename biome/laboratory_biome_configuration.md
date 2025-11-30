---
title: Laboratory Biome Configuration
category: biome
---

# Laboratory Biome Configuration

This document outlines the configuration for the Laboratory biome in Noita, focusing on key elements relevant to AI-assisted modding.

## Biome Registration

The Laboratory biome is registered with specific spawn functions.

### Spawn Functions

*   **`init`**: Triggered during biome initialization.
    *   Associated Entity ID: `0xffffeedd`
*   **`spawn_target`**: Triggered for spawning specific entities.
    *   Associated Entity ID: `0xffb4a00a`

## Initialization (`init` function)

The `init` function is responsible for setting up the biome's visual and structural elements.

```lua
function init( x, y, w, h )
	-- LoadPixelScene( "data/biome_impl/mountain_lake.png", "", x, y, "", true )
	-- LoadPixelScene( "data/biome_impl/mountain_lake_top.png", "", x, y-88, "", true )
end
```

*   **Commented-out `LoadPixelScene` calls**: These indicate potential visual assets that could be loaded for the biome. Modders can uncomment or replace these to customize the biome's appearance.

## Entity Spawning (`spawn_target` function)

The `spawn_target` function handles the placement of specific entities within the biome.

```lua
function spawn_target(x, y)
	EntityLoad( "data/entities/props/dummy_target.xml", x, y )
end
```

*   **`EntityLoad`**: This function is used to load an entity from an XML file at the specified coordinates.
    *   **Entity**: `data/entities/props/dummy_target.xml` - This suggests the presence of a "dummy target" prop, which could be a placeholder or a specific interactive element.

## Global Constants

*   **`CHEST_LEVEL`**: Set to `3`. This likely influences the type or rarity of chests that can spawn within this biome.

## Dependencies

The Laboratory biome relies on several helper scripts:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biomes/mountain/mountain.lua`