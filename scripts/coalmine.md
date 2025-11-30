---
title: coalmine
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/coalmine.lua
---

# coalmine

This file, `coalmine.lua`, defines the characteristics and contents of the Coal Mine biome in Noita. It acts as a blueprint for how this specific area of the game world is generated, including the types of enemies that spawn, the structures and environmental elements present, and the probabilities associated with their appearance. This biome is typically one of the early areas players encounter, characterized by its dark, rocky terrain and the presence of coal.

## File Structure

The file is written in Lua and uses a data-driven approach to define biome elements. The primary structure involves defining global tables (variables) that hold configurations for various aspects of the biome. These tables often contain:

*   **`total_prob`**: A cumulative probability, likely used for normalization or internal calculations within the game's generation system.
*   **Entries within tables**: These are typically tables themselves, each representing a specific entity, structure, or spawnable item.
*   **`prob`**: The probability of this specific entry appearing.
*   **`min_count` / `max_count`**: The minimum and maximum number of instances of this entry to spawn.
*   **`entity`**: A string path to an `.xml` file defining the entity (e.g., an enemy, item, or structure).
*   **`entities`**: For entries that can spawn multiple distinct entities, this is a table of entity paths.
*   **`material_file` / `visual_file`**: Paths to image files used for defining the visual and physical properties of environmental elements (pixel scenes).
*   **`background_file`**: Path to a background image file.
*   **`is_unique`**: A flag (0 or 1) indicating if this element should only appear once.
*   **`spawn_check`**: A Lua function that can be used to conditionally spawn an entity based on game state or time.
*   **`color_material`**: A table mapping specific color codes (hex strings) to lists of material types, used for defining how liquids or other substances behave within structures like oil tanks.

The file also includes calls to `dofile_once` and `dofile` to include other necessary Lua scripts, such as helper functions for director logic, biome generation, and item generation.

## Key Patterns

Several patterns are evident in the sampled content:

*   **Enemy Spawning (`g_small_enemies`, `g_big_enemies`)**: These tables define lists of enemies that can spawn within the biome. Each entry specifies the enemy's entity file, its spawn probability, and the number of instances. The `g_small_enemies` and `g_big_enemies` likely represent different categories or tiers of enemies.
*   **Environmental Elements (`g_pixel_scene_01`, `g_oiltank`)**: These tables define recurring environmental features.
    *   `g_pixel_scene_01` appears to define various "pixel scenes" or tile sets that make up the terrain. Each scene has associated material, visual, and potentially background files.
    *   `g_oiltank` defines different configurations for oil tanks, including their visual appearance and, crucially, the `color_material` attribute. This attribute maps specific colors within the tank's texture to different liquid types (e.g., "water", "oil", "lava", "poison", "magic\_liquid\_teleportation"). This allows for varied liquid contents within these structures.
*   **Conditional Spawning**: The `spawn_check` function within an entry for `miner_santa` demonstrates a pattern for conditional spawning. This function checks the current month and day to determine if the entity should spawn, suggesting seasonal events or content.
*   **Entity Definitions**: The `entity` fields consistently point to `.xml` files located in `data/entities/`. This indicates a modular design where specific game objects are defined separately and then referenced by biome files.
*   **Probability-Based Generation**: The use of `prob` values throughout the file highlights that the game's generation system relies heavily on random chance and weighted probabilities to populate the biome.
*   **Color Mapping for Materials**: The `color_material` in `g_oiltank` is a significant pattern, showing how specific colors in a texture can be dynamically assigned different material properties by the game engine.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **Small Enemy Definition (`g_small_enemies`)**:
    ```lua
    {
        prob   		= 0.25,
        min_count	= 1,
        max_count	= 2,
        entity 	= "data/entities/animals/miner_weak.xml"
    },
    ```
    **Explanation**: This entry defines a "weak miner" enemy. It has a 25% chance (`prob = 0.25`) of spawning, and if it does, between 1 and 2 instances (`min_count = 1`, `max_count = 2`) will appear. The enemy's definition is found in `data/entities/animals/miner_weak.xml`.

2.  **Pixel Scene Definition (`g_pixel_scene_01`)**:
    ```lua
    {
        prob   			= 0.5,
        material_file 	= "data/biome_impl/coalmine/coalpit01.png",
        visual_file		= "data/biome_impl/coalmine/coalpit01_visual.png",
        background_file	= "",
        is_unique		= 0,
    },
    ```
    **Explanation**: This entry defines a specific environmental element, likely a type of coal pit. It has a 50% chance (`prob = 0.5`) of being used in the biome's generation. The `material_file` and `visual_file` specify the image assets that define its physical properties and appearance, respectively. `is_unique = 0` means multiple instances of this scene can appear.

3.  **Conditional Oil Tank (`g_oiltank`)**:
    ```lua
    {
        prob   			= 0.0004,
        material_file 	= "data/biome_impl/coalmine/oiltank_1.png",
        visual_file		= "data/biome_impl/coalmine/oiltank_1_visual.png",
        background_file	= "",
        is_unique		= 0,
        color_material = { ["fff0bbee"] = { "magic_liquid_teleportation", "magic_liquid_polymorph", "magic_liquid_random_polymorph", "magic_liquid_berserk", "magic_liquid_charm", "magic_liquid_invisibility", "magic_liquid_hp_regeneration", "salt", "blood", "gold", "honey" } }
    },
    ```
    **Explanation**: This is a special, rare (`prob = 0.0004`) oil tank configuration. It uses the same base visual assets as other oil tanks but has a unique `color_material` mapping. The hex color `fff0bbee` within its texture is associated with a variety of powerful "magic liquids" and other special substances, making this a potentially very rewarding find.

## Reference

This file contains 1255 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/coalmine.lua).

---