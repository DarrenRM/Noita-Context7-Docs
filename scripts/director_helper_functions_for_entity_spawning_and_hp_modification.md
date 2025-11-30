---
title: Director Helper Functions for Entity Spawning and HP Modification
category: scripts
---

# Director Helper Functions for Entity Spawning and HP Modification

This document outlines helper functions used in Noita's director system for spawning entities and modifying their HP, particularly within camera-bound areas and for biome-specific adjustments.

## Key Functions

### `IMPL_load_entity_hp_mods_with_camera_bound(entity_file, x, y, hp_multiplier, biome)`

This function loads an entity, optionally modifies its HP based on a multiplier, and saves it to a specified biome path if it's an animal entity. Otherwise, it loads the entity within camera bounds.

**Key Attributes/Elements:**

*   **`entity_file`**: Path to the entity's `.xml` file.
*   **`x`, `y`**: Coordinates for entity placement.
*   **`hp_multiplier`**: A factor to scale the entity's maximum HP.
*   **`biome`**: The name of the biome to save the entity to (if applicable).

**Behavior:**

*   If `entity_file` is in `data/entities/animals/`:
    *   Loads the entity.
    *   Retrieves and modifies its `DamageModelComponent`'s `max_hp` and `hp` based on `hp_multiplier`.
    *   Constructs a new `entity_file` path based on the provided `biome`.
    *   Saves the modified entity to the new path.
*   Otherwise:
    *   Loads the entity using `EntityLoadCameraBound`.

### `entity_load_camera_bound_hp(entity_data, x, y, rand_x, rand_y, hp_multiplier, biome)`

This is a more comprehensive function for loading entities, handling groups of entities, and applying HP multipliers. It uses procedural randomness for placement.

**Key Attributes/Elements:**

*   **`entity_data`**: A table containing entity information. Can include:
    *   `entities`: A list of entities or entity groups to spawn.
    *   `entity`: The primary entity to spawn.
    *   `min_count`, `max_count`: Range for the number of entities to spawn.
    *   `offset_x`, `offset_y`: Additional positional offsets.
*   **`x`, `y`**: Base coordinates for spawning.
*   **`rand_x`, `rand_y`**: Maximum random offset from the base coordinates.
*   **`hp_multiplier`**: Factor to scale entity HP.
*   **`biome`**: The biome name for HP modification.

**Behavior:**

*   Iterates through `entity_data.entities` if present, spawning each sub-entity with random offsets and applying HP modifications.
*   Handles `min_count` and `max_count` for spawning multiple instances of an entity.
*   If `entity_data.entity` is present, it spawns that entity with random offsets and applies HP modifications.
*   Returns `0` if no entities are spawned, `1` otherwise.

### `spawn_hp_mult(what, x, y, rand_x, rand_y, hp_multiplier, biome)`

A utility function to select a random entity from a table (`what`) and then spawn it using `entity_load_camera_bound_hp` with specified parameters.

**Key Attributes/Elements:**

*   **`what`**: A table containing potential entities to spawn.
*   **`x`, `y`**: Base coordinates for spawning.
*   **`rand_x`, `rand_y`**: Maximum random offset from the base coordinates.
*   **`hp_multiplier`**: Factor to scale entity HP.
*   **`biome`**: The biome name for HP modification.

**Behavior:**

*   Selects a random entity from the `what` table using `random_from_table`.
*   Calls `entity_load_camera_bound_hp` to spawn the selected entity with the provided parameters.

---

**Note:** These functions are primarily used internally by the Noita director system to manage entity placement and difficulty scaling across different biomes. Modders can leverage these to customize entity spawns and their properties.