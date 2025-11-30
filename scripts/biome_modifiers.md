---
title: biome_modifiers
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biome_modifiers.lua
---

# biome_modifiers

This file, `biome_modifiers.lua`, defines various modifiers that can be applied to biomes within the game Noita. These modifiers alter the gameplay experience by changing environmental properties, enemy behaviors, or introducing specific entities. They are crucial for adding variety and challenge to different areas of the game world. The script ensures these modifiers are applied consistently, even across game saves and loads, by re-initializing them when game systems are initialized.

## File Structure

The file primarily consists of Lua code that defines a table named `biome_modifiers`. Each entry in this table represents a single biome modifier. These entries are structured as Lua tables themselves, containing the following key-value pairs:

*   **`id`**: A unique string identifier for the modifier (e.g., `"MOIST"`, `"HIGH_GRAVITY"`).
*   **`ui_description`**: A localization key (prefixed with `$`) that points to the in-game text describing the modifier.
*   **`ui_decoration_file`**: The file path to a graphical asset used to visually represent the modifier in the UI.
*   **`probability`**: A floating-point number between 0 and 1 indicating the likelihood of this modifier being applied to a biome.
*   **`does_not_apply_to_biome`**: An optional table of biome names (strings) to which this modifier should *not* be applied.
*   **`action`**: A Lua function that is executed when the modifier is applied. This function typically uses `BiomeObjectSetValue` to modify biome properties.
*   **`inject_spawns_action`**: An optional Lua function that is executed to inject specific entities (props, enemies, etc.) into the biome when the modifier is active. This function often uses helper functions like `inject_spawn`.

Additionally, the file defines global constants like `CHANCE_OF_MODIFIER_PER_BIOME` and a list of `biomes` that can potentially have modifiers applied.

## Key Patterns

Several patterns are evident in the `biome_modifiers.lua` file:

*   **Modifier Definition Structure**: Each modifier follows a consistent table structure as described above.
*   **Environmental Effects**: Many modifiers directly alter environmental properties. For example, `MOIST` affects dust, fire, water stains, and projectile drag. `HIGH_GRAVITY` and `LOW_GRAVITY` modify entity gravity.
*   **Entity Spawning**: The `inject_spawns_action` is a common pattern for introducing specific entities that are thematic to the modifier. This can include traps (`mine.xml`, `trap_electricity_enabled.xml`), decorative elements (`furniture_tombstone_01.xml`), or specialized spawners (`tiny_ghost_spawner.xml`).
*   **Exclusion Lists**: The `does_not_apply_to_biome` field is used to prevent certain modifiers from appearing in specific, often foundational, biomes like `mountain_hall`.
*   **Localization and UI**: The use of `ui_description` and `ui_decoration_file` indicates a strong integration with the game's UI system for presenting modifiers to the player.
*   **Global Constants for Probability**: Constants like `CHANCE_OF_MODIFIER_PER_BIOME` suggest a global system for determining which biomes receive modifiers.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`MOIST` Modifier**:
    ```lua
    {
        id = "MOIST",
        ui_description="$biomemodifierdesc_moist",
        ui_decoration_file="data/ui_gfx/decorations_biome_modifier/moist.png",
        probability=0.7,
        action = function( biome_name, biome_filename )
            BiomeObjectSetValue( biome_filename, "modifiers", "dust_amount", 0.75 )
            BiomeObjectSetValue( biome_filename, "modifiers", "fire_extinguish_chance", 11 )
            BiomeObjectSetValue( biome_filename, "modifiers", "random_water_stains_chance", 5 )
            BiomeObjectSetValue( biome_filename, "modifiers", "random_water_stains_amount", 5 )
            BiomeObjectSetValue( biome_filename, "modifiers", "projectile_drag_coeff", 0.965 )
        end,
    },
    ```
    This modifier, with a high probability of 0.7, makes the biome "moist." Its `action` function modifies several biome properties: reducing dust, making fires extinguish easily, increasing the chance and amount of water stains, and increasing projectile drag.

2.  **`CONDUCTIVE` Modifier**:
    ```lua
    {
        id = "CONDUCTIVE",
        ui_description="$biomemodifierdesc_conductive",
        ui_decoration_file="data/ui_gfx/decorations_biome_modifier/conductive.png",
        probability=0.2,
        does_not_apply_to_biome={"mountain_hall","coalmine"},
        action = function( biome_name, biome_filename )
            BiomeObjectSetValue( biome_filename, "modifiers", "everything_is_conductive", true )
        end,
        inject_spawns_action = function()
            inject_spawn( g_props, 2, {
                prob   		= 0,
                min_count	= 1,
                max_count	= 1,
                offset_y 	= 0,
                entity 	=  "data/entities/props/physics/trap_electricity_enabled.xml",
            })
            -- ... other inject_spawn calls
        end,
    },
    ```
    This modifier, with a lower probability of 0.2, makes all materials conductive. It explicitly avoids applying to `mountain_hall` and `coalmine`. Its `inject_spawns_action` adds electricity-related traps to the biome.

3.  **`BOOBY_TRAPPED` Modifier**:
    ```lua
    {
        id = "BOOBY_TRAPPED",
        ui_description="$biomemodifierdesc_booby_trapped",
        ui_decoration_file="data/ui_gfx/decorations_biome_modifier/booby_trapped.png",
        probability=0.75,
        does_not_apply_to_biome={"mountain_hall"},
        action = function( biome_name, biome_filename )	end,
        inject_spawns_action = function()
            inject_spawn( g_props, 0.75, {
                prob   		= 0,
                min_count	= 1,
                max_count	= 1,
                offset_y 	= 0,
                entity 	=  "data/entities/projectiles/mine.xml",
            })
            -- ... other inject_spawn calls
        end,
    },
    ```
    This modifier, with a high probability of 0.75, makes the biome dangerous by adding mines. It also avoids the `mountain_hall`. The `action` function is empty, indicating that all its effects are achieved through spawning entities.

## Reference

This file contains 1295 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biome_modifiers.lua).

---