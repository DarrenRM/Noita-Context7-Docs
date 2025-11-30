---
title: Overworld Winter Ruins Spawner
category: scripts
---

# Overworld Winter Ruins Spawner

This script is responsible for procedurally generating winter ruins in the Noita overworld. It places various structural elements, props, and enemies to create a unique and atmospheric environment.

## Key Parameters

These variables control the overall generation process and spacing of elements.

*   `structure_spacing`: The horizontal distance between generated structures and props.
*   `end_spacing`: Padding added at the beginning and end of the generation area.
*   `structure_height_random`: The maximum random variation applied to the vertical placement of structures.
*   `extra_ruins_chance`: The probability of spawning additional, potentially larger, ruin structures.
*   `collapse_chance`: The probability that the generated ruins will experience a collapse event.

## Generation Components

The script defines several tables that hold information about the different types of assets that can be spawned.

### Bases

These are the primary ground structures for the ruins.

| File                                                | Width | Probability |
| :-------------------------------------------------- | :---- | :---------- |
| `data/biome_impl/overworld/snowy_ruins_base_01`     | 184   | 0.75        |
| `data/biome_impl/overworld/snowy_ruins_base_02`     | 93    | 1.0         |
| `data/biome_impl/overworld/snowy_ruins_base_03`     | 138   | 1.0         |

### Structures

These are the vertical elements that form the ruins, such as pillars.

| File                                                | Height | Probability |
| :-------------------------------------------------- | :----- | :---------- |
| `data/biome_impl/overworld/snowy_ruins_pillar_01`   | 84     | 1.0         |
| `data/biome_impl/overworld/snowy_ruins_pillar_02`   | 35     | 1.0         |
| `data/biome_impl/overworld/snowy_ruins_pillar_03`   | 113    | 0.6         |
| `data/biome_impl/overworld/snowy_ruins_pillar_04`   | 100    | 0.8         |
| `data/biome_impl/overworld/snowy_ruins_pillar_05`   | 34     | 1.0         |

### Props

Smaller decorative elements that add detail to the ruins.

| File                                       | Probability |
| :----------------------------------------- | :---------- |
| `data/entities/props/overworld/banner_01.xml` | 0.4         |
| `data/entities/props/overworld/banner_02.xml` | 0.4         |
| `data/entities/props/overworld/banner_03.xml` | 0.5         |

### Snow Piles

Decorative snow formations.

| File                                          | Probability |
| :-------------------------------------------- | :---------- |
| `data/entities/props/overworld/snow_pile_01.xml` | 1.0         |
| `data/entities/props/overworld/snow_pile_02.xml` | 1.0         |

### Enemies

Potential hostile entities that can spawn within the ruins.

| File                                     | Probability |
| :--------------------------------------- | :---------- |
| `nil` (no enemy)                         | 15.0        |
| `data/entities/animals/miner.xml`        | 1.0         |
| `data/entities/animals/shotgunner.xml`   | 1.0         |
| `data/entities/animals/scavenger_mine.xml` | 1.0         |
| `data/entities/animals/scavenger_smg.xml` | 1.0         |
| `data/entities/animals/scavenger_grenade.xml` | 1.0         |
| `data/entities/animals/iceskull.xml`     | 0.1         |
| `data/entities/animals/icemage.xml`      | 0.1         |

## Generation Logic

The script follows these steps to create the ruins:

1.  **Select Base:** A base structure is chosen randomly based on its probability. The generation position is adjusted to center the base.
2.  **Place Decorations:** The script iterates through the available horizontal space, randomly placing structures and props. It attempts to avoid repeating consecutive structures.
3.  **Place Base:** The selected base structure is loaded last to ensure it covers any overlapping elements.
4.  **Collapse or Snow:** Based on `collapse_chance`, the ruins either trigger a collapse event or have snow piles sprinkled on top.
5.  **Spawn Enemies:** Enemies are placed within the generated ruins area based on their respective probabilities.
6.  **Extra Ruins:** With a small chance (`extra_ruins_chance`), additional, potentially larger, ruin structures are spawned.
7.  **Cleanup:** The spawner entity itself is removed after its task is complete.

## Helper Functions

*   `load_pixel_scene(file, x, y)`: A utility function to load pixel-based scene assets.

```lua
local function load_pixel_scene(file, x, y)
	--print("placing " .. file .. " to " .. x .. ", " .. y)
	LoadPixelScene( file .. ".png", file .. "_visual.png", x, y, "", true)
end
```