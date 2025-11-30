---
title: Utility Box Spawner
category: scripts/buildings
---

# Utility Box Spawner

This script is responsible for spawning a "utility box" entity at a specific location. It's likely used as part of a building or event that introduces these boxes into the game world.

## Key Functionality

*   **Entity Spawning:** Creates an instance of `data/entities/items/pickup/utility_box.xml`.
*   **Randomized Placement:** The spawned utility box is placed at a slightly randomized horizontal position relative to the spawner's location.
*   **Screen Shake:** Triggers a screen shake effect upon spawning.

## Core Attributes

| Attribute       | Description                                                                                                |
| :-------------- | :--------------------------------------------------------------------------------------------------------- |
| `entity_id`     | The unique identifier for the entity executing this script.                                                |
| `pos_x`, `pos_y` | The X and Y coordinates of the spawner entity.                                                             |
| `SetRandomSeed` | Initializes the random number generator using game frame number and entity position for deterministic randomness. |
| `EntityLoad`    | The primary function to load and place a new entity into the game world.                                   |
| `GameScreenshake` | Triggers a visual screen shake effect with a specified intensity.                                          |

## Example Usage (Conceptual)

This script would typically be attached to an entity that acts as a "spawner" or "generator" within the game. For instance, a special building or a triggered event could have this script attached to it.

```lua
-- Example of how this script might be called within another entity's XML
-- (This is illustrative and not directly from the provided Lua file)

<entity name="my_utility_spawner_building">
    <components>
        <script name="data/scripts/buildings/spawn_utility_boxes.lua" />
        <!-- Other components for the building -->
    </components>
</entity>
```