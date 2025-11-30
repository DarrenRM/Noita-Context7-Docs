---
title: Secret Altar Biome Script
category: scripts/
---

# Secret Altar Biome Script

This script defines the behavior and entity spawning for the "Secret Altar" biome in Noita. It handles the initialization of the biome's visual elements and the placement of specific entities.

## Core Functions

### `init(x, y, w, h)`

This is the primary initialization function for the biome.

*   **`LoadPixelScene(...)`**: Loads the visual representation of the secret altar biome using a pixel scene file.
*   **`EntityLoad(...)`**: Spawns the "book\_physics.xml" entity, likely a boss or significant prop, at a specific offset within the biome.

### `spawn_lamp2(x, y)`

This function is responsible for spawning decorative lamps and chandeliers within the biome. It utilizes the `g_lamp2` table to determine which entities to spawn and their placement.

### `spawn_small_enemies(x, y)`

This function is intended to spawn small enemies. Currently, it's configured to spawn a `chest_secret.xml` entity.

## Entity Spawning Tables

These tables define the probabilities and entities to be spawned by the respective spawn functions.

### `g_small_enemies`

This table dictates what "small enemies" are spawned.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `total_prob`| Total probability for this group (currently 0). |
| `prob`      | Probability of spawning this specific entity.   |
| `min_count` | Minimum number of entities to spawn.            |
| `max_count` | Maximum number of entities to spawn.            |
| `entity`    | Path to the entity XML file to spawn.           |

**Key Entity:**

*   `data/entities/items/chest_secret.xml`

### `g_lamp2`

This table defines the entities related to lighting and decorative elements.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `total_prob`| Total probability for this group (currently 0). |
| `prob`      | Probability of spawning this specific entity.   |
| `min_count` | Minimum number of entities to spawn.            |
| `max_count` | Maximum number of entities to spawn.            |
| `entity`    | Path to the entity XML file to spawn.           |
| `offset_x`  | Horizontal offset for spawning.                 |
| `offset_y`  | Vertical offset for spawning.                   |

**Key Entities:**

*   `data/entities/props/physics/chain_torch.xml`
*   `data/entities/props/physics_chandelier.xml`

### `g_candles`

This table defines the different types of candles that can be spawned.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `total_prob`| Total probability for this group (currently 0). |
| `prob`      | Probability of spawning this specific entity.   |
| `min_count` | Minimum number of entities to spawn.            |
| `max_count` | Maximum number of entities to spawn.            |
| `entity`    | Path to the entity XML file to spawn.           |

**Key Entities:**

*   `data/entities/props/physics_candle_1.xml`
*   `data/entities/props/physics_candle_2.xml`
*   `data/entities/props/physics_candle_3.xml`

## Registration

### `RegisterSpawnFunction(id, function_name)`

This function registers specific spawn functions to be called by the game's director system based on certain conditions (likely related to biome IDs or other game states).

*   **`0xffffeedd`**: Registers the `init` function.
*   **`0xffC8C800`**: Registers the `spawn_lamp2` function.