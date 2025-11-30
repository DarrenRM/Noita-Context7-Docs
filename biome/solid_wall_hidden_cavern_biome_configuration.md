---
title: Solid Wall Hidden Cavern Biome Configuration
category: biome
---

---

# Solid Wall Hidden Cavern Biome Configuration

This document details the configuration for the "Solid Wall Hidden Cavern" biome in Noita, focusing on its entity spawning behavior. This biome is characterized by its hidden nature within solid walls and is loaded via a pixel scene.

## Core Biome Functions

The `solid_wall_hidden_cavern.lua` script registers a primary initialization function that determines where the biome's unique pixel scene will be loaded.

### `init(x, y, w, h)`

This function is called by the game's director to initialize the biome.

-   **Pixel Scene Loading:** It randomly selects one of four potential vertical zones (`y` ranges) to load the `data/biome_impl/solid_wall_hidden_cavern.png` pixel scene. This ensures the biome appears in specific, hidden locations.
-   **Conditional Loading:** The `LoadPixelScene` function is called only if the current `y` coordinate falls within one of the designated spawn ranges for the selected random location.

## Entity Spawning Configuration

The script defines several global tables (`g_small_enemies`, `g_lamp`, `g_items`, etc.) that dictate the types and probabilities of entities that can spawn within this biome. However, for this specific biome, most of these spawn functions are intentionally left empty, indicating no custom spawning for those categories.

### Key Spawning Tables and Functions

While many spawn functions are empty, the `g_lamp` table and its associated `spawn_lamp` function are configured.

#### `g_lamp` Table

This table defines the probability and count for spawning lamps.

| Attribute   | Value                                     | Description                                                                 |
| :---------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `total_prob`| `0`                                       | Total probability for this group (effectively unused as individual probs sum to 1.0). |
| `prob`      | `0.2`                                     | Probability of spawning the entity.                                         |
| `min_count` | `1`                                       | Minimum number of entities to spawn.                                        |
| `max_count` | `1`                                       | Maximum number of entities to spawn.                                        |
| `entity`    | `"data/entities/props/physics/lantern_small.xml"` | The entity to spawn (a small lantern).                                      |

#### `g_ghostlamp` Table

This table defines the probability and count for spawning ghostly torches.

| Attribute   | Value                                           | Description                                                                 |
| :---------- | :---------------------------------------------- | :-------------------------------------------------------------------------- |
| `total_prob`| `0`                                             | Total probability for this group.                                           |
| `prob`      | `1.0`                                           | Probability of spawning the entity.                                         |
| `min_count` | `1`                                             | Minimum number of entities to spawn.                                        |
| `max_count` | `1`                                             | Maximum number of entities to spawn.                                        |
| `entity`    | `"data/entities/props/physics/chain_torch_ghostly.xml"` | The entity to spawn (a ghostly chain torch).                                |

#### `g_candles` Table

This table defines the probability and count for spawning various types of candles.

| Attribute   | Value                                   | Description                                                                 |
| :---------- | :-------------------------------------- | :-------------------------------------------------------------------------- |
| `total_prob`| `0`                                     | Total probability for this group.                                           |
| `prob`      | `0.33`                                  | Probability of spawning the entity.                                         |
| `min_count` | `1`                                     | Minimum number of entities to spawn.                                        |
| `max_count` | `1`                                     | Maximum number of entities to spawn.                                        |
| `entity`    | `"data/entities/props/physics_candle_1.xml"` | The entity to spawn (candle type 1).                                        |
| `prob`      | `0.33`                                  | Probability of spawning the entity.                                         |
| `min_count` | `1`                                     | Minimum number of entities to spawn.                                        |
| `max_count` | `1`                                     | Maximum number of entities to spawn.                                        |
| `entity`    | `"data/entities/props/physics_candle_2.xml"` | The entity to spawn (candle type 2).                                        |
| `prob`      | `0.33`                                  | Probability of spawning the entity.                                         |
| `min_count` | `1`                                     | Minimum number of entities to spawn.                                        |
| `max_count` | `1`                                     | Maximum number of entities to spawn.                                        |
| `entity`    | `"data/entities/props/physics_candle_3.xml"` | The entity to spawn (candle type 3).                                        |

### Empty Spawn Functions

The following spawn functions are defined but contain no logic, meaning no entities of these types will be spawned by this biome's script:

-   `spawn_small_enemies(x, y)`
-   `spawn_big_enemies(x, y)`
-   `spawn_items(x, y)`
-   `spawn_unique_enemy(x, y)`
-   `spawn_props(x, y)`
-   `spawn_potions(x, y)`

### `spawn_lamp(x, y)` Function

This function is responsible for spawning lamps within the biome. It calls the `spawn` function with the `g_lamp` table, placing the entity at `x, y+6`.

```lua
function spawn_lamp(x, y)
	spawn(g_lamp,x,y+6,0,0)
end
```