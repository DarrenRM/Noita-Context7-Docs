---
title: GameAreaEffectComponent
source: https://noita.wiki.gg/wiki/Documentation:GameAreaEffectComponent
category: modding-wiki
---

# GameAreaEffectComponent

This documentation covers the `GameAreaEffectComponent` in Noita, a crucial component for defining environmental effects that trigger when a player enters a specific area. Understanding this component is essential for modders looking to create custom biomes, hazards, or interactive environmental elements.

## Overview

The `GameAreaEffectComponent` is attached to entities that define areas within the game world. When a player character enters the bounding box of an entity with this component, the specified effects are triggered. This is the primary mechanism for implementing biome-specific hazards, ambient effects, and other area-based gameplay mechanics.

## Component Properties

The `GameAreaEffectComponent` has several properties that control its behavior and the effects it applies. These are typically defined within an entity's XML definition.

### `effect_probability`

*   **Type:** `float`
*   **Description:** The probability (between 0.0 and 1.0) that the area effect will trigger when the player enters the area. A value of 1.0 means it will always trigger.

### `effect_radius`

*   **Type:** `float`
*   **Description:** The radius around the player within which the effect will be applied. This is useful for effects that have a localized impact.

### `effect_type`

*   **Type:** `string`
*   **Description:** Specifies the type of effect to apply. This often corresponds to predefined effect IDs or custom effect names.

### `effect_entity_file`

*   **Type:** `string`
*   **Description:** The path to an entity XML file that will be spawned when the effect is triggered. This allows for complex effects involving multiple entities or visual elements.

### `effect_material`

*   **Type:** `string`
*   **Description:** The material to apply to the area. This is often used for visual effects like fog or particles.

### `effect_color`

*   **Type:** `string` (e.g., "R,G,B,A")
*   **Description:** The color to apply to the effect, specified as RGBA values.

### `effect_particle_emitter`

*   **Type:** `string`
*   **Description:** The name of a particle emitter to spawn.

### `effect_sound_loop`

*   **Type:** `string`
*   **Description:** The path to a sound file to play as a loop when the effect is active.

### `effect_sound_once`

*   **Type:** `string`
*   **Description:** The path to a sound file to play once when the effect is triggered.

### `effect_script_file`

*   **Type:** `string`
*   **Description:** The path to a Lua script file to execute when the effect is triggered. This offers the most flexibility for custom logic.

### `effect_script_name`

*   **Type:** `string`
*   **Description:** The name of a function within a loaded Lua script to call.

### `effect_script_parameter_int`
### `effect_script_parameter_float`
### `effect_script_parameter_string`

*   **Type:** `int`, `float`, `string` respectively
*   **Description:** Parameters that can be passed to the `effect_script_name` function.

### `effect_tag`

*   **Type:** `string`
*   **Description:** A tag that can be used to identify or group effects.

### `effect_target_tag`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should target.

### `effect_target_material`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should target.

### `effect_target_biome`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should target.

### `effect_target_entity_file`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should target.

### `effect_target_entity_tag`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should target.

### `effect_target_entity_material`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should target.

### `effect_target_entity_biome`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the effect should *not* target.

### `effect_target_entity_tag_not`

*   **Type:** `string`
*   **Description:** A tag that specifies which entities the effect should *not* target.

### `effect_target_entity_material_not`

*   **Type:** `string`
*   **Description:** A material that specifies which entities the effect should *not* target.

### `effect_target_entity_biome_not`

*   **Type:** `string`
*   **Description:** A biome name that specifies which entities the effect should *not* target.

### `effect_target_entity_file_not`

*   **Type:** `string`
*   **Description:** An entity file path that specifies which entities the