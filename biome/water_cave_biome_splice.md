---
title: Water Cave Biome Splice
category: biome
---

# Water Cave Biome Splice

This document describes the configuration for splicing the "Water Cave" biome into Noita. It utilizes a pixel scene to define the biome's layout and appearance.

## Core Configuration

The primary configuration is handled by the `wizard_physics.exe` tool, which splices a pixel scene into the game's biome data.

### Key Parameters

*   **`data/biome_impl/spliced/watercave.png`**: This is the pixel scene file that defines the visual and structural elements of the Water Cave biome. The colors within this image are mapped to specific in-game materials and entities.
*   **`-x -2048`**: Specifies the X-coordinate offset for placing the biome.
*   **`-y 0`**: Specifies the Y-coordinate offset for placing the biome.

## Usage

This configuration is intended to be executed as part of the Noita modding build process, likely within a batch script (`.bat` file) to automate the biome splicing.

```lua
-- Example of how this might be called within a larger Lua script for modding:
-- (This is illustrative and not directly from the .bat file)

local function spliceWaterCave()
    -- Assuming a function exists to execute external commands
    execute_command("wizard_physics.exe -splice_pixel_scene data/biome_impl/spliced/watercave.png -x -2048 -y 0")
end

-- Call the function to splice the biome
-- spliceWaterCave()
```

## Notes

*   The actual mapping of colors in `watercave.png` to in-game elements is defined elsewhere, likely in configuration files that `wizard_physics.exe` reads.
*   The offsets (`-x`, `-y`) are crucial for determining where the Water Cave biome will appear in the game world relative to other biomes.