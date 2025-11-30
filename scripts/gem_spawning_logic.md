---
title: Gem Spawning Logic
category: scripts
---

# Gem Spawning Logic

This script defines the logic for spawning small gems or bones around a specific entity. It's designed to be attached to an entity that should trigger this spawning behavior.

## Core Functionality

The script randomly determines a number of gems/bones to spawn and then iterates through that count, loading and applying a small force to each spawned item.

## Key Attributes

*   **`count`**: Determines the number of items to spawn. It's calculated using `Random(0,3) * Random(0,1)`, which results in a 50% chance of spawning 0 items, and a 50% chance of spawning 1, 2, or 3 items.
*   **`prefixes`**: A table defining the types of items that can be spawned. Each entry includes:
    *   `name`: The base name of the item prefix (e.g., "physics\_smallgem", "physics\_bone").
    *   `count`: The maximum number of variations for that prefix (e.g., if `count` is 5, it will try to spawn `prefix_01` through `prefix_05`).
*   **`EntityLoad`**: Used to load the actual item entity from its XML definition.
*   **`PhysicsApplyForce`**: Applies a random force to the spawned item, giving it a slight push.

## Spawning Process

1.  **Initialization**: Gets the current entity's ID and position.
2.  **Random Seed**: Sets a random seed based on game frame and entity position for more varied results.
3.  **Determine Spawn Count**: Calculates how many items to spawn.
4.  **Iteration**: If `count` is greater than 0, the script loops:
    *   **Select Item Type**: Randomly chooses a prefix from the `prefixes` table.
    *   **Generate Item Name**: Constructs the full item name by combining the prefix and a random variation number (e.g., "physics\_smallgem\_02").
    *   **Load Entity**: Loads the item entity at a slightly randomized position near the spawner.
    *   **Apply Force**: If the entity was successfully loaded, a random upward force is applied.

## Example Usage

This script would typically be attached to an entity that, upon its death or some other trigger, should drop a few small gems or bones.

```lua
-- Example of how this script might be included in another entity's XML:
-- <entity name="some_dying_creature">
--     <components>
--         <item name="script_component">
--             <param name="script_file" value="data/scripts/animals/spawn_gems.lua" />
--         </item>
--     </components>
-- </entity>
```