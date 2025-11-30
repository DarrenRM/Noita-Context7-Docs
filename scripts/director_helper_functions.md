---
title: Director Helper Functions
category: scripts
---

# Director Helper Functions

This file contains utility functions used by the Noita director system for spawning entities, loading scenes, and managing probabilities. These functions are crucial for procedural generation and ensuring varied gameplay experiences.

## Core Spawning Logic

### `random_from_table(what, x, y)`

Selects a random entry from a table based on probabilities, considering spawn conditions.

*   **`what`**: A table containing potential entities or scenes to spawn. Each entry should have a `prob` field.
*   **`x`, `y`**: Coordinates used for procedural randomization.

**Key Attributes within `what` entries:**

*   **`prob`**: The probability of this entry being selected.
*   **`spawn_check`**: An optional function that must return `true` for the entry to be considered.
*   **`ngpluslevel`**: The New Game Plus level required for this entry to be considered.
*   **`parallel`**: A boolean indicating if this entry can spawn in parallel worlds.
*   **`entity`**: The entity XML file to load (for direct entity spawning).
*   **`entities`**: A table of entities to load (for group spawning).
*   **`material_file`**: The material file for pixel scenes.
*   **`visual_file`**: The visual file for pixel scenes.
*   **`background_file`**: The background file for pixel scenes.
*   **`sprite_file`**: The sprite file for background sprites.
*   **`z_index`**: The Z-index for pixel scenes or background sprites.
*   **`color_material`**: A table for mapping colors to materials in pixel scenes.

### `spawn(what, x, y, rand_x, rand_y)`

Spawns an entity or scene selected by `random_from_table`, applying a default offset.

*   **`what`**: The table of spawnable items (see `random_from_table`).
*   **`x`, `y`**: Base coordinates for spawning.
*   **`rand_x`, `rand_y`**: Maximum random offset from the base coordinates.

### `spawn2(what, x, y, rand_x, rand_y)`

Similar to `spawn`, but spawns without the default 5,5 offset.

### `DEBUG_spawn_all(what, x, y, width)`

Spawns all entities from a table sequentially, useful for debugging.

## Scene and Sprite Loading

### `load_random_pixel_scene(what, x, y)`

Loads a random pixel scene from the provided table.

*   **`what`**: A table of pixel scene definitions (see `random_from_table` for key attributes).
*   **`x`, `y`**: Coordinates for loading the scene.

### `load_random_background_sprite(what, x, y)`

Loads a random background sprite from the provided table.

*   **`what`**: A table of background sprite definitions (see `random_from_table` for key attributes).
*   **`x`, `y`**: Coordinates for loading the sprite.

## Entity Loading Helpers

### `entity_load_camera_bound(entity_data, x, y, rand_x, rand_y)`

Loads entities, handling groups and random positioning within bounds.

*   **`entity_data`**: Data defining the entity or group of entities to load. Can be a string (entity file) or a table with `entity`, `entities`, `min_count`, `max_count`, `offset_x`, `offset_y`.
*   **`x`, `y`**: Base coordinates for spawning.
*   **`rand_x`, `rand_y`**: Maximum random offset from the base coordinates.

### `entity_load_chest(x, y, chest_type, force_level)`

Loads a chest entity with specified type and level.

*   **`x`, `y`**: Coordinates for the chest.
*   **`chest_type`**: The type of chest (e.g., "chest", "chest_stash"). Defaults to "chest".
*   **`force_level`**: An optional level to force for the chest's contents.

### `entity_load_stash(x, y)`

Loads a stash entity. Currently loads a heart pickup, but has commented-out code for a proper stash.

## Utility Functions

### `check_newgame_plus_level(level)`

Checks if the current New Game Plus level meets or exceeds the specified level.

### `check_parallel(status, x)`

Checks if parallel world spawning is enabled and if a parallel world position is valid.

### `init_total_prob(value, x)`

Calculates the `total_prob` for a table of spawnable items, considering spawn conditions.

### `is_empty(what)`

Checks if a value is nil or an empty string.

### `is_table(t)`

Checks if a value is a Lua table.

### `spawn_with_limited_random(what, x, y, rand_x, rand_y, entities_to_randomize)`

Spawns entities with limited randomization applied only to specified entity types.

*   **`what`**: The table of spawnable items.
*   **`x`, `y`**: Base coordinates for spawning.
*   **`rand_x`, `rand_y`**: Maximum random offset from the base coordinates.
*   **`entities_to_randomize`**: A table of entity names (without `.xml`) that should have their positions randomized.