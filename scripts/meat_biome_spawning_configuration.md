---
title: Meat Biome Spawning Configuration
category: scripts
---

---

# Meat Biome Spawning Configuration

This script defines the entities and props that can spawn within the "Meat" biome in Noita. It utilizes a system of probability-based spawning for various categories of entities, including small and large enemies, unique encounters, items, and environmental props.

## Core Spawning Logic

The script registers several spawn functions that are called by the game's director system at specific points during level generation. These functions then utilize probability tables to determine which entities to spawn.

### Registered Spawn Functions

*   `init(x, y, w, h)`: A general initialization function, often called at the start of a biome.
*   `spawn_skulls(x, y)`: Spawns skull-themed props.
*   `spawn_cyst(x, y)`: Spawns meat cysts.
*   `spawn_vines(x, y)`: Spawns various types of meat vines.
*   `spawn_mouth(x, y)`: Spawns wall mouths and eyes.
*   `spawn_hanging_prop(x, y)`: Spawns suspended props like cages and chains.

## Entity Spawning Tables

The following tables define the probability and count for different entity types. The `prob` attribute determines the likelihood of an entity spawning, while `min_count` and `max_count` define the range of entities to spawn if the probability check passes.

### Small Enemies (`g_small_enemies`)

| Entity Path                                  | Probability | Min Count | Max Count |
| :------------------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/animals/shotgunner_hell.xml`  | 0.3         | 1         | 2         |
| `data/entities/animals/miner_hell.xml`       | 0.3         | 1         | 2         |
| `data/entities/animals/rat.xml`              | 0.5         | 1         | 4         |
| `data/entities/animals/sniper_hell.xml`      | 0.2         | 1         | 1         |
| `data/entities/animals/meatmaggot.xml`       | 0.1         | 1         | 1         |

### Big Enemies (`g_big_enemies`)

| Entity Path                                     | Probability | Min Count | Max Count | NG+ Level | Spawn Check Function |
| :---------------------------------------------- | :---------- | :-------- | :-------- | :-------- | :------------------- |
| `data/entities/animals/worm_big.xml`            | 0.05        | 1         | 1         |           |                      |
| `data/entities/animals/worm.xml`                | 0.01        | 1         | 1         |           |                      |
| `data/entities/animals/meatmaggot.xml`          | 0.1         | 2         | 3         |           |                      |
| `data/entities/animals/wizard_hearty.xml`       | 0.2         | 1         | 1         |           |                      |
| `data/entities/animals/slimespirit.xml`         | 0.1         | 1         | 1         |           |                      |
| `data/entities/buildings/hpcrystal.xml`         | 0.05        | 1         | 1         |           |                      |
| `data/entities/animals/easter/sniper.xml`       | 0.01        | 1         | 2         |           | `spawn_check`        |
| `data/entities/animals/bloodcrystal_physics.xml`| 0.2         | 1         | 1         |           |                      |
| `data/entities/animals/necrobot.xml`            | 0.1         | 1         | 1         |           |                      |
| `data/entities/animals/necrobot_super.xml`      | 0.06        | 1         | 1         | 1         |                      |
| `data/entities/animals/failed_alchemist.xml`    | 0.1         | 1         | 1         |           |                      |

### Unique Encounters (`g_unique_enemy`, `g_unique_enemy2`)

**`g_unique_enemy`**

| Entity Path                         | Probability | Min Count | Max Count |
| :---------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/animals/wizard_tele.xml` | 0.1         | 1         | 1         |
| `data/entities/animals/wizard_dark.xml` | 0.1         | 1         | 1         |
| `data/entities/animals/wizard_swapper.xml` | 0.07        | 1         | 1         |
| `data/entities/animals/necromancer.xml` | 0.1         | 1         | 1         |

**`g_unique_enemy2`**

| Entity Path                         | Probability | Min Count | Max Count |
| :---------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/animals/sniper_hell.xml` | 0.5         | 3         | 4         |

### Items (`g_items`)

| Entity Path                         | Probability | Min Count | Max Count |
| :---------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/items/wand_level_05.xml` | 5           | 1         | 1         |
| `data/entities/items/wand_level_06.xml` | 5           | 1         | 1         |
| `data/entities/items/wand_unshuffle_04.xml` | 5           | 1         | 1         |
| `data/entities/items/wand_unshuffle_05.xml` | 5           | 1         | 1         |

### Environmental Props

**Lanterns (`g_lamp`)**

| Entity Path                               | Probability | Min Count | Max Count |
| :---------------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/props/physics_lantern_small.xml` | 0.7         | 1         | 1         |

**General Props (`g_props`)**

| Entity Path                                     | Probability | Min Count | Max Count | Offset Y |
| :---------------------------------------------- | :---------- | :-------- | :-------- | :------- |
| `data/entities/props/physics_box_explosive.xml` | 0.5         | 1         | 1         | 0        |
| `data/entities/props/physics_propane_tank.xml`  | 0.2         | 1         | 1         | 0        |
| `data/entities/props/physics_barrel_oil.xml`    | 0.3         | 1         | 1         | 0        |
| `data/entities/props/physics_trap_electricity_enabled.xml` | 0.05        | 1         | 1         | 0        |

**Skulls (`g_skulls`)**

| Entity Path                     | Probability | Min Count | Max Count | Offset Y |
| :------------------------------ | :---------- | :-------- | :-------- | :------- |
| `data/entities/props/physics_skull_01.xml` | 1.5         | 1         | 1         | 0        |
| `data/entities/props/physics_skull_02.xml` | 1.5         | 1         | 1         | 0        |
| `data/entities/props/physics_skull_03.xml` | 1.5         | 1         | 1         | 0        |
| `data/entities/props/physics_bone_01.xml`  | 0.5         | 1         | 1         | 0        |
| ... (other bone variations)     | 0.5         | 1         | 1         | 0        |

**Ghostly Lanterns (`g_ghostlamp`)**

| Entity Path                                     | Probability | Min Count | Max Count | Offset Y |
| :---------------------------------------------- | :---------- | :-------- | :-------- | :------- |
| `data/entities/props/physics_chain_torch_ghostly.xml` | 1.0         | 1         | 1         | 10       |

**Candles (`g_candles`)**

| Entity Path                     | Probability | Min Count | Max Count |
| :------------------------------ | :---------- | :-------- | :-------- |
| `data/entities/props/physics_candle_1.xml` | 0.33        | 1         | 1         |
| `data/entities/props/physics_candle_2.xml` | 0.33        | 1         | 1         |
| `data/entities/props/physics_candle_3.xml` | 0.33        | 1         | 1         |

**Vines (`g_vines`)**

| Entity Path                                       | Probability | Min Count | Max Count |
| :------------------------------------------------ | :---------- | :-------- | :-------- |
| `data/entities/verlet_chains/meatvine/verlet_vine.xml` | 0.4         | 1         | 1         |
| `data/entities/verlet_chains/meatvine/verlet_vine_long.xml` | 0.3         | 1         | 1         |
| `data/entities/verlet_chains/meatvine/verlet_vine_short.xml` | 0.5         | 1         | 1         |
| `data/entities/verlet_chains/meatvine/verlet_vine_shorter.xml` | 0.5         | 1         | 1         |

**Mouths (`g_mouth`)**

| Entity Path                     | Probability | Min Count | Max Count |
| :------------------------------ | :---------- | :-------- | :-------- |
| `data/entities/buildings/wallmouth.xml` | 0.4         | 1         | 1         |
| `data/entities/buildings/walleye.xml`   | 0.3         | 1         | 1         |

**Hanging Props (`g_hanging_props`)**

| Entity Path                               | Probability | Min Count | Max Count |
| :---------------------------------------- | :---------- | :-------- | :-------- |
| `data/entities/props/suspended_cage.xml`  | 0.6         | 1         | 1         |
| `data/entities/props/suspended_cage_broken.xml` | 0.6         | 1         | 1         |
| `data/entities/props/suspended_chain.xml` | 0.6         | 1         | 1         |
| `data/entities/props/suspended_seamine.xml` | 0.1         | 1         | 1         |

## Helper Functions

The script also includes several helper functions that are called by the game to trigger specific spawning events or load predefined scenes.

*   `spawn_small_enemies(x, y)`: Calls the `spawn` function with `g_small_enemies`.
*   `spawn_big_enemies(x, y)`: Calls the `spawn` function with `g_big_enemies`.
*   `spawn_unique_enemy(x, y)`: Calls the `spawn` function with `g_unique_enemy`.
*   `spawn_unique_enemy2(x, y)`: Calls the `spawn` function with `g_unique_enemy2`.
*   `spawn_items(x, y)`: Loads a specific wand altar scene or spawns a utility box based on probability.
*   `spawn_lamp(x, y)`: Calls the `spawn` function with `g_lamp`.
*   `spawn_props(x, y)`: Calls the `spawn` function with `g_props`.
*   `spawn_skulls(x, y)`: Calls the `spawn` function with `g_skulls`.
*   `spawn_stones(x, y)`: Calls the `spawn` function with `g_stones` (though `g_stones` is not defined in this snippet).
*   `load_pixel_scene`, `load_pixel_scene_alt`, `load_pixel_scene2`, `load_pixel_scene3`, `load_pixel_scene4`: Placeholder functions for loading pixel scenes.
*   `spawn_altar_torch(x, y)`: Loads a specific altar torch entity.
*   `spawn_shopitem(x, y)`: Calls `generate_shop_item` to create a shop item.
*   `spawn_electricity_trap(x, y)`: Loads an electricity trap entity.
*   `spawn_burning_barrel(x, y)`: Loads a burning barrel entity.
*   `spawn_fish(x, y)`: Placeholder function for spawning fish.
*   `spawn_cyst(x, y)`: Spawns a meat cyst with a probability check.
*   `spawn_vines(x, y)`: Calls the `spawn` function with `g_vines`.
*   `spawn_mouth(x, y)`: Calls the `spawn` function with `g_mouth`.
*   `spawn_hanging_prop(x, y)`: Calls the `spawn` function with `g_hanging_props`.