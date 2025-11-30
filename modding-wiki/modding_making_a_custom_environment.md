---
title: Modding: Making a Custom Environment
source: https://noita.wiki.gg/wiki/Modding:_Making_a_custom_environment
category: modding-wiki
---

# Modding: Making a Custom Environment

This documentation guides you through the process of creating custom environments and biomes in Noita. Understanding how Noita generates its world is crucial for modders looking to add new areas, modify existing ones, or ensure compatibility between different mods.

## How Biome Loading Works

Noita determines which biome map to load using the `BIOME_MAP` magic number. By default, this is set to `data/biome_impl/biome_map.png`. The coordinates within this map are relative to its center, with X:0 being the horizontal center and Y:0 being 14 pixels down from the top.

You can change the biome map in three ways:

1.  **Overwrite the default file:** Place your custom `biome_map.png` in `mods/yourmod/data/biome_impl/`.
2.  **Static redirection:** Use `ModMagicNumbersFileAdd` in your `init.lua` to point to a different static file:
    ```xml
    <MagicNumbers BIOME_MAP="mods/yourmod/yourmap.png"></MagicNumbers>
    ```
3.  **Dynamic redirection:** Point to a Lua script for conditional loading:
    ```xml
    <MagicNumbers BIOME_MAP="mods/yourmod/yourmap.lua"></MagicNumbers>
    ```
    The third option is essential for mod compatibility as it allows for conditional loading.

Once a biome map is loaded, Noita parses `data/biome/_biomes_all.xml`. For each entry in this file, it reads the `biome_filename` (e.g., `data/biome/coalmine.xml`). This file, in turn, defines the `wang_template_file` (for generating the biome's structure) and the `lua_script` (which runs at game startup and stays loaded). Both of these files must exist, or the game will crash.

The `Documentation: Biome` page provides a comprehensive list of available fields in biome XML files.

The world's origin (0,0) is determined by the center of the biome map horizontally and the `biome_offset_y` defined in `_biomes_all.xml` vertically.

### Biome Generation

Biome generation occurs dynamically as the camera moves. When the game needs to generate a new area, it checks the biome map based on the camera's coordinates. One pixel on the biome map corresponds to a 512x512 chunk in the game world.

To determine the biome map pixel for a given camera coordinate (e.g., x=1098, y=824):

*   Divide X by 512: 1098 / 512 = 2.144, rounded down to `2`.
*   Divide Y by 512: 824 / 512 = 1.609, rounded down to `1`.
*   This gives you a relative position of (2, 1) from the center.
*   To get the absolute pixel on a 70x35 map:
    *   X: (70 / 2) + 2 = 35 + 2 = `37`
    *   Y: 14 (default `biome_offset_y`) + 1 = `15`
*   The pixel at (37, 15) on `biome_map.png` has the color `ffd57917`. The game then finds the `<Biome>` entry in `_biomes_all.xml` with this color, which points to `data/biome/coalmine.xml`.

Shades of grey in wang tiles are filled with materials defined in the biome's `<Materials>` section, while other colors directly place corresponding materials as defined in `data/materials.xml`'s `wang_colors` attribute.

### Biome Scripts

Enemies and items are placed by examining pixel colors within wang tiles. When a wang tile is placed for the first time in the camera's viewport, the game attempts to call a predefined function in the biome's `lua_script`. Some of these functions are hardcoded and listed in `data/scripts/wang_scripts.csv` (e.g., `ffffd171,spawn_orb,-1,-1,-1,-1`). If the corresponding function (e.g., `spawn_orb(x, y)`) is not found in the biome's Lua script, an error will occur when running `noita_dev.exe` without crashing the game.

You can import default scripts using:

```lua
dofile_once("data/scripts/biome_scripts.lua")
```

However, you still need to define any missing functions to avoid errors like `Couldn't find function: spawn_props`.

You can also register custom pixel colors and their associated scripts:

```lua
RegisterSpawnFunction(0xffabcdef, "my_function_name")
function my_function_name(x, y)
-- This function is called for every pixel of color ffabcdef found in a wang tile or pixel scene.
end
```

The color must start with `0xFF` and be followed by the desired HEX color.

A special color, `0xffffeedd`, can also be registered:

```lua
RegisterSpawnFunction(0xffffeedd, "init")
```

This function runs every time a biome chunk is loaded, and its pixel does not need to be placed anywhere.

### Where does the tree to the left of the starting position and the skull in the desert come from?

These are global pixel scenes defined in `data/biome/_pixel_scenes.xml` with absolute world coordinates. This path is hardcoded and cannot be changed without overwriting the file.

The `BiomeMapLoad_KeepPlayer` function is used by New Game+ to reload the world:

```lua
BiomeMapLoad_KeepPlayer(filename, pixel_scenes='data/biome/_pixel_scenes.xml')
```

This function can be called while the game is running and the map has already been loaded. `filename` can be a biome map image or a map loading script. However, this function is not always reliable and can sometimes crash the game.

## How to Make Biome Mods Compatible

### Problems

Modding biomes presents compatibility challenges because new biomes must be added to `data/biome/_biomes_all.xml`. This file cannot be modified programmatically, requiring mods to overwrite it. If multiple mods do this, the last loaded mod's version will prevail, potentially nullifying others. A unified `_biomes_all.xml` containing all biomes from active mods is necessary. Furthermore, all referenced files (biome XMLs, wang templates, Lua scripts) must exist, even if the mod defining them is inactive, to prevent game crashes.

### Simple Solution (February 2025)

This approach involves creating alternate versions of `_biomes_all.xml` with different names. Your mod's `init.lua` can then use `ModTextFileSetContent` to dynamically switch between these variants based on which compatible mods are enabled. This avoids redundant biome files, as your "standard" definition file doesn't need to include unused biomes.

The example below demonstrates how to swap `_biomes_all.xml` files based on mod activation:

```lua
if ModIsEnabled("Mod2") then
	ModTextFileSetContent("data/biome/_biomes_all.xml", ModTextFileGetContent("data/biome/_biomes_all_compat.xml"))
	ModTextFileSetContent("mods/Mod2/files/scripts/biomes/biome_map.lua", ModTextFileGetContent("mods/myMod/files/scripts/biomes/biome_map_mod2_compat.lua"))
else
	ModMagicNumbersFileAdd( "mods/myMod/files/magic_numbers.xml")
end
```

In this example:
*   `"Mod2"` is the mod you want to be compatible with.
*   `"data/biome/_biomes_all_compat.xml"` contains biome definitions for both `myMod` and `Mod2`.
*   `"mod/myMod/files/scripts/biomes/biome_map_mod2_compat.lua"` is a version of the map loading script for `Mod2` that includes biomes from `myMod`.
*   `"mod/myMod/files/magic_numbers.xml"` is a standard magic numbers file that redirects the game's default biome map definition, used only if no compatible mods are active.

### Alternate Solution

This method requires all mods to adhere to a strict set of shared files:

*   A unified `data/biome/_biomes_all.xml`.
*   Consistent `biome.xml` and `wang_template_file` definitions across all mods.
*   A shared biome map loading script defined by `MagicNumbers:BIOME_MAP`.
*   A consistent biome map height to ensure `biome_offset_y` remains compatible.

These shared files must be kept up-to-date by all mod developers.

**Two approaches for managing shared files:**

*   **A) Duplication:** Each mod includes a duplicate copy of the shared files. This avoids external dependencies but can lead to conflicts if an outdated mod is loaded last.
*   **B) Dependency Mod:** A separate mod acts as a dependency for all biome mods, containing all shared files. This simplifies updates for mod developers but is hindered by Steam Workshop's limitations on collaborative mod development and ownership transfer.

To maintain organization, it's recommended to place shared files in a dedicated subfolder, e.g., `data/shared/ModName`.

**Making Lua Scripts Independent:**

You can use a "dummy script" approach. A shared `dummy_script.lua` can conditionally load the actual biome script:

```lua
if ModIsEnabled("MyCoolMod") then
  dofile_once("mods/MyCoolMod/biome.lua")
end
```

If `MyCoolMod` is not active, its biome functions won't be called, preventing errors.

**Handling Map Loading:**

To manage map loading dynamically, point `MagicNumbers:BIOME_MAP` to a Lua script:

```xml
<MagicNumbers BIOME_MAP="mods/yourmod/yourmap.lua"></MagicNumbers>
```

This script can then use `BiomeMap*` functions:

```lua
BiomeMapSetSize(70, 45)
if ModIsEnabled("SomeMod") and ModIsEnabled("OtherMod") then
  -- Has both SomeMod's pixels placed and OtherMod's.
  BiomeMapLoadImage(0, 0, "data/biome_impl/biome_map_somemod_othermod.png")
elseif not ModIsEnabled("SomeMod") and ModIsEnabled("OtherMod") then
  -- Only has OtherMod's pixels placed.
  BiomeMapLoadImage(0, 0, "data/biome_impl/biome_map_othermod.png")
end
-- etc
```

Alternatively, use `BiomeMapSetPixel` for dynamic pixel painting:

```lua
BiomeMapSetSize(70, 45)
BiomeMapLoadImage(0, 0, "data/biome_impl/biome_map.png")
if ModIsEnabled("SomeMod") then
  BiomeMapSetPixel(35, 14, 0xffabcdef)
end
if ModIsEnabled("OtherMod") then
  BiomeMapSetPixel(40, 14, 0xfffedcba)
end
```

**Important Note:** The last mod to overwrite `data` files takes precedence. However, the **first** mod that defines `MagicNumbers:BIOME_MAP` will have its script loaded; subsequent definitions will be ignored.

## How to Make Your Mod Compatible with Nightmare Mode and New Game+

### Nightmare Mode

Nightmare mode attempts to use its own map generation script by setting `MagicNumbers:BIOME_MAP`. You can append to its map loading script using:

```lua
ModLuaFileAppend("mods/nightmare/files/biome_map.lua", "your_map_loading_script.lua")
```

Any `BiomeMapSetSize` and `BiomeMapLoadImage` calls can be overwritten by simply calling them again. Appending your usual map loading script should ensure compatibility regardless of mod loading order.

### New Game+

New Game+ initialization occurs in `data/entities/animals/boss_centipede/ending/sampo_start_ending_sequence.lua`. The critical part is in `data/scripts/newgame_plus.lua` line 71:

```lua
BiomeMapLoad_KeepPlayer("data/biome_impl/biome_map_newgame_plus.lua", "data/biome/_pixel_scenes_newgame_plus.xml")
```

To hijack this, append the following to `biome_map_newgame_plus.lua`:

```lua
setfenv(do_newgame_plus, setmetatable({
  BiomeMapLoad_KeepPlayer = function(map_file, pixel_scenes_file)
    BiomeMapLoad_KeepPlayer("your_map_loading_script.lua")
  end
}, {
  __index = _G
}))
```

This redirects the `BiomeMapLoad_KeepPlayer` call within the `do_newgame_plus` function to your own version.

### Compatibility Example

[Example mods demonstrating compatibility](https://drive.google.com/open?id=1exlxZ_9WFXGm53i4d1Arx4dD4oxtOerH) (Note: This link may be outdated or broken).

## Material Reference for Mapping

To easily select colors for wang tiles and pixel scenes, use the provided color reference image.

[Download the color reference image from GitHub](https://raw.githubusercontent.com/ryyst/noita-utils/master/colors.png). The wiki's image compression can alter colors, so downloading directly from GitHub is recommended.

## Pixel Scenes

**Pixel Scenes** are images that can be randomly chosen by the generator or manually defined in `data/biome/_pixel_scenes.xml`.

*   Use the reference colors from the thumbnail image to draw pixel scenes.
*   The color `FFFFFF` uses materials from the biome it loads in, eliminating the need to draw them yourself.
*   Special colors can be registered in your biome's Lua script using `RegisterSpawnFunction` for spawning entities at specific locations within your scene.

**Example Pixel Scene Image:**

(Image of a pixel scene would be displayed here if available)

You can spawn your scene in-game using the 'T' key in devmode.

### Splicing Large Pixel Scenes

Pixel scenes are limited to 512x512 pixels. For larger scenes, use the `noita.exe` command prompt tool:

```bash
cd C:/path/to/your/Noita/mods/yourmod
C:/path/to/your/Noita/noita.exe -splice_pixel_scene files/largescene.png -x 500 -y 1000
```

This will generate `yourmod/data/biome_impl/spliced/largescene.xml` and a folder with `.plz` files. Add the XML file to the `PixelSceneFiles` section in `data/biome/_pixel_scenes.xml` to spawn the scene at the specified coordinates (x=500, y=1000).

### Adding Pixel Scenes to Biome Generation

1.  **Draw your pixel scene.**
2.  **Create a `.lua` file** to append it to the scene pool:

    ```lua
    table.insert(g_pixel_scene_02, {
      prob = 1000,
      material_file = "mods/yourmod/files/scene.png",
      visual_file = "",
      background_file = "",
      is_unique = 0
    })
    ```
    *   Use `g_pixel_scene_01` for vertical scenes, `g_pixel_scene_02` for horizontal ones.
    *   `prob`: 0-1000, with 1000 being the most common.
    *   `material_file`: Spawns the materials.
    *   `visual_file`: Adds visual elements on top of materials (e.g., wand pedestals). Has no effect on air.
    *   `background_file`: The background image.
    *   `color_material`: Replaces pixels with a random pick from a table:
        ```lua
        color_material = { ["fff0bbee"] = { "oil", "alcohol", "gunpowder_explosive" } }
        ```
3.  **Append your scene script** to the desired biome's Lua file using `ModLuaFileAppend` in your `init.lua`:

    `ModLuaFileAppend("data/scripts/biomes/coalmine.lua", "mods/somemod/files/examplescene.lua")`

## Wang Tiles

For creating your own wang tiles, Horscht's [web-based wang tiler](https://thehorscht.github.io/NoitaWangTiler/) is a useful tool for previewing their in-game appearance.

Examples of wang tiles from the [Coal Pits](https://noita.wiki.gg/wiki/Coal_Pits):

*   (Image of Coalmine wang tiles)
*   (Zoomed image of Coalmine wang tiles)