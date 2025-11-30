---
title: New Game Plus Pixel Scene Definitions
category: biome
---

# New Game Plus Pixel Scene Definitions

This document outlines the configuration for pixel scenes used in Noita's New Game Plus mode, focusing on how custom scenes and background elements are integrated.

## Pixel Scene Files

This section lists external XML files that define spliced pixel scenes. These are pre-designed biome segments that can be incorporated into the game world.

### Key Elements:

*   **`<File>`**: Specifies the path to an external XML file containing a pixel scene definition.

### Listed Files:

*   `data/biome_impl/spliced/skull_in_desert.xml`
*   `data/biome_impl/spliced/boss_arena.xml`
*   `data/biome_impl/spliced/tree.xml`
*   `data/biome_impl/spliced/mountain_lake.xml`
*   `data/biome_impl/spliced/lake_statue.xml`
*   `data/biome_impl/spliced/moon.xml`
*   `data/biome_impl/spliced/gourd_room.xml`
*   `data/biome_impl/spliced/moon_dark.xml`
*   `data/biome_impl/spliced/skull.xml`

## Background Images

This section defines background images that can be placed within the game world. These are typically decorative elements that add visual depth to biomes.

### Key Elements:

*   **`<Image>`**: Defines a background image.
    *   `filename`: The path to the image file (e.g., `.png`).
    *   `x`: The horizontal position of the image.
    *   `y`: The vertical position of the image.

### Listed Images:

*   `data/biome_impl/hidden/boss_arena.png` (x: 3425, y: 12650)
*   `data/biome_impl/hidden/boss_arena_under.png` (x: 2976, y: 13792)
*   `data/biome_impl/hidden/boss_arena_under_right.png` (x: 4238, y: 15055)
*   `data/biome_impl/hidden/completely_random.png` (x: -5400, y: 21887)
*   `data/biome_impl/hidden/completely_random_2.png` (x: 4256, y: 26954)
*   `data/biome_impl/hidden/fungal_caverns_1.png` (x: 3419, y: 2652)
*   `data/biome_impl/hidden/holy_mountain_1.png` (x: 1785, y: 1325)
*   `data/biome_impl/hidden/jungle_right.png` (x: 2806, y: 6614)
*   `data/biome_impl/hidden/mountain_text.png` (x: 700, y: -440)
*   `data/biome_impl/hidden/under_the_wand_cave.png` (x: -4448, y: 4487)
*   `data/biome_impl/hidden/vault_inside.png` (x: -2120, y: 8446)
*   `data/biome_impl/hidden/crypt_left.png` (x: -4129, y: 10533)

## Buffered Pixel Scenes

This section defines pixel scenes that are loaded directly without referencing separate XML files. This allows for more granular control over scene placement and content.

### Key Elements:

*   **`<PixelScene>`**: Defines a pixel scene to be loaded.
    *   `pos_x`: The horizontal position of the scene.
    *   `pos_y`: The vertical position of the scene.
    *   `material_filename`: Path to the material definition file for the scene.
    *   `colors_filename`: Path to the color definition file for the scene.
    *   `background_filename`: Path to a background image file for the scene (can be empty).
    *   `clean_area_before`: If set to `1`, the area is cleared before loading the scene.
    *   `skip_biome_checks`: If set to `1`, biome compatibility checks are skipped.
    *   `skip_edge_textures`: If set to `1`, edge textures are not generated.
    *   `just_load_an_entity`: If present, loads a specific entity at the given position instead of a full pixel scene.

### Listed Buffered Scenes:

*   **Essence Altar (Overworld)**
    *   `pos_x`: -6948
    *   `pos_y`: -270
    *   `material_filename`: `data/biome_impl/overworld/essence_altar.png`
    *   `colors_filename`: `data/biome_impl/overworld/essence_altar_visual.png`
    *   `skip_biome_checks`: 1
    *   `skip_edge_textures`: 1

*   **Essence Altar (Desert)**
    *   `pos_x`: 12519
    *   `pos_y`: -30
    *   `material_filename`: `data/biome_impl/overworld/essence_altar_desert.png`
    *   `colors_filename`: `data/biome_impl/overworld/essence_altar_desert_visual.png`
    *   `skip_biome_checks`: 1
    *   `skip_edge_textures`: 1

*   **Essence Eater Entity**
    *   `pos_x`: -6888
    *   `pos_y`: -155
    *   `just_load_an_entity`: `data/entities/buildings/essence_eater.xml`

*   **Essence Eater Entity**
    *   `pos_x`: 12569
    *   `pos_y`: 30
    *   `just_load_an_entity`: `data/entities/buildings/essence_eater.xml`

*   **Maggot Spot Entity**
    *   `pos_x`: 14941
    *   `pos_y`: 16454
    *   `just_load_an_entity`: `data/entities/buildings/maggotspot.xml`

*   **Giga Fish Entity**
    *   `pos_x`: -14000
    *   `pos_y`: 10000
    *   `just_load_an_entity`: `data/entities/animals/boss_fish/fish_giga.xml`