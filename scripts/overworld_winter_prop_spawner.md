---
title: Overworld Winter Prop Spawner
category: scripts
---

# Overworld Winter Prop Spawner

This script is responsible for spawning various props in the overworld, specifically in winter-themed areas. It includes logic to prevent spawning underground and uses a weighted probability system to determine which prop to spawn.

## Core Functionality

The primary purpose of this script is to dynamically place decorative and environmental props within the game world. It acts as a spawner entity that, upon activation, selects and loads a prop based on predefined probabilities.

## Key Attributes and Elements

### Prop Definitions

The script defines a table named `props` which contains a list of potential props to spawn. Each entry in this table is an object with the following key attributes:

*   **`file`**: (string) The file path to the entity XML definition of the prop to be spawned.
*   **`probability`**: (number) A weighted value that influences the likelihood of this prop being chosen. Higher values mean a greater chance of spawning.

Here's a summary of the props defined in the script:

| Prop File                                       | Probability | Description                               |
| :---------------------------------------------- | :---------- | :---------------------------------------- |
| `data/entities/props/overworld/snowy_rock_01.xml` | 1           | Snowy rock variant 1                      |
| `data/entities/props/overworld/snowy_rock_02.xml` | 1.5         | Snowy rock variant 2 (slightly more common) |
| `data/entities/props/overworld/snowy_rock_03.xml` | 1           | Snowy rock variant 3                      |
| `data/entities/props/overworld/snowy_rock_04.xml` | 1.3         | Snowy rock variant 4                      |
| `data/entities/props/overworld/snowy_rock_05.xml` | 1           | Snowy rock variant 5                      |
| `data/entities/props/overworld/snow_pile_01.xml`  | 1.2         | Snow pile variant 1                       |
| `data/entities/props/overworld/snow_pile_02.xml`  | 1.2         | Snow pile variant 2                       |
| `data/entities/props/overworld/banner_01.xml`     | 0.4         | Banner variant 1                          |
| `data/entities/props/overworld/banner_02.xml`     | 0.4         | Banner variant 2                          |
| `data/entities/props/overworld/banner_03.xml`     | 0.5         | Banner variant 3                          |
| `data/entities/props/overworld/winter_ruins_spawner.xml` | 0.6         | Spawns winter ruins elements              |

### Spawning Logic

1.  **Get Entity Position**: The script first retrieves the current entity's ID and its world coordinates (`pos_x`, `pos_y`).
2.  **Underground Check**: It checks if the entity's `pos_y` is greater than 40. If it is, the entity is killed to prevent spawning underground.
3.  **Weighted Selection**: The `pick_random_from_table_weighted` function is used to select a prop from the `props` table based on the assigned probabilities.
4.  **Entity Loading**: The selected prop's XML file is then loaded into the game world at the spawner's position using `EntityLoad`.
5.  **Self-Destruction**: After successfully spawning a prop, the spawner entity kills itself using `EntityKill`.

## AI Modding Considerations

*   **Custom Props**: To add new props, simply create a new XML entity file for your prop and add an entry to the `props` table with a desired `file` path and `probability`.
*   **Probability Tuning**: Adjust the `probability` values to control how frequently specific props appear.
*   **Environmental Control**: This script is a good example of how to control the visual and environmental elements of specific biomes. You can adapt this pattern for other biomes by changing the `props` table to include relevant entities.
*   **Conditional Spawning**: For more advanced AI modding, you could introduce additional checks before spawning, such as biome type, time of day, or player proximity, by modifying the initial checks or adding new logic before `EntityLoad`.