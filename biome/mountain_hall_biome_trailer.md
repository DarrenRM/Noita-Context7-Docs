---
title: Mountain Hall Biome Trailer
category: biome
---

# Mountain Hall Biome Trailer

This document describes the configuration for the "Mountain Hall" biome, specifically tailored for use in Noita's trailer or introductory sequences. It focuses on defining the visual elements, environmental features, and initial entity spawns for this specific area.

## Core Biome Configuration

This biome is designed to be a visually distinct area within the mountain, likely serving as an introductory or cinematic segment.

### Visual Scene Loading

The `init` function is responsible for loading the visual components of the biome. These are defined by `.png` files that dictate the background, foreground, and visual overlays.

| Parameter | Description |
|---|---|
| `LoadPixelScene( "data/biome_impl/trailer/mountain_hall.png", "data/biome_impl/trailer/mountain_hall_visual.png", x, y, "data/biome_impl/trailer/mountain_hall_background.png", true )` | Loads the primary visual scene for the mountain hall, including its visual layer and background. |
| `LoadPixelScene( "data/biome_impl/trailer/mountain_hall_text.png", "data/biome_impl/trailer/mountain_hall_text_visual.png", x, y, "", true )` | Loads a text overlay for the hall, likely for titles or labels. |
| `LoadPixelScene( "data/biome_impl/mountain/hall_b.png", "data/biome_impl/mountain/hall_b_visual.png", x+512, y+512, "", true )` | Loads a specific segment of the hall, likely a bottom-right portion. |
| `LoadPixelScene( "data/biome_impl/mountain/hall_br.png", "data/biome_impl/mountain/hall_br_visual.png", x+512, y+512, "", true )` | Loads another segment of the hall, likely a bottom-right portion. |
| `LoadPixelScene( "data/biome_impl/mountain/hall_r.png", "data/biome_impl/mountain/hall_r_visual.png", x+512, y, "", true )` | Loads a right segment of the hall. |

### Environmental Elements

The biome incorporates dynamic environmental elements, specifically various types of vines, using a Verlet chain system for realistic physics.

| Element Type | Description |
|---|---|
| `load_verlet_rope_with_two_joints` | Loads a Verlet chain with two connection points, creating longer, more flexible vines. |
| `load_verlet_rope_with_one_joint` | Loads a Verlet chain with one connection point, creating shorter, more rigid vines. |

### Spawn Functions

Specific functions are registered to be called at certain color values within the biome's pixel scene data. These functions are responsible for spawning entities or triggering events.

| Color (Hex) | Function Name | Description |
|---|---|---|
| `0xffffeedd` | `init` | The primary initialization function for the biome. |
| `0xffFF5A00` | `spawn_crate` | Spawns an explosive physics box. |
| `0xffFF2D00` | `spawn_waterspout` | Spawns a dripping water entity. |

## Entity Spawning

The biome defines specific configurations for spawning certain types of entities.

### Small Enemies

The `g_small_enemies` and `g_small_enemies_helpless` tables define the probabilities and types of smaller creatures that can spawn within the biome.

**`g_small_enemies` (Primary)**

This table is currently configured to spawn no entities, with a placeholder for future additions.

| Attribute | Description |
|---|---|
| `total_prob` | Total probability for spawning entities in this group. |
| `prob` | Probability of a specific entity spawning. |
| `min_count` | Minimum number of entities to spawn. |
| `max_count` | Maximum number of entities to spawn. |
| `entity` | Path to the entity's XML file. |

**`g_small_enemies_helpless` (Secondary)**

This table defines a variety of passive animals that can spawn.

| Attribute | Description |
|---|---|
| `total_prob` | Total probability for spawning entities in this group. |
| `prob` | Probability of a specific entity spawning. |
| `min_count` | Minimum number of entities to spawn. |
| `max_count` | Maximum number of entities to spawn. |
| `entity` | Path to the entity's XML file. |
| `data/entities/animals/sheep.xml` | Sheep entity. |
| `data/entities/animals/deer.xml` | Deer entity. |
| `data/entities/animals/elk.xml` | Elk entity. |
| `data/entities/animals/duck.xml` | Duck entity. |

### Other Spawn Functions

*   **`spawn_crate(x, y)`**: Loads an `explosive_physics_box.xml` entity at the specified coordinates.
*   **`spawn_waterspout(x, y)`**: Loads a `dripping_water_heavy.xml` entity at the specified coordinates.
*   **`spawn_chest(x, y)`**: This function is commented out and appears to be a placeholder for chest spawning logic, with references to `building_chest_stash.xml` and `chest_tutorial`.

## Dependencies

This biome relies on several external Lua files for its functionality:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biomes/mountain/mountain.lua`
*   `data/scripts/lib/utilities.lua`