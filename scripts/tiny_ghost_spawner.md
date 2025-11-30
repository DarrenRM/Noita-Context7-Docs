---
title: Tiny Ghost Spawner
category: scripts
---

# Tiny Ghost Spawner

This script defines the behavior for a spawner entity that creates and attaches a "tiny ghost" to a nearby enemy.

## Core Functionality

The primary purpose of this script is to:
1.  Detect the closest enemy entity.
2.  If an enemy is found and it's not the player, it reduces the enemy's health.
3.  It then enables a pre-existing "ghost" child entity.
4.  Finally, it transfers ownership of the ghost to the enemy and removes the spawner itself.

## Key Attributes & Logic

*   **`collision_trigger(target_id)`**: This function is the main entry point for the spawner's logic. It's likely called when the spawner collides with something.
*   **`EntityGetClosestWithTag(x, y, "enemy")`**: Finds the nearest entity with the "enemy" tag.
*   **`IsPlayer(target_id)`**: Checks if the detected target is the player. The ghost is *not* applied to the player.
*   **`EntityGetAllChildren(entity_id)`**: Retrieves all child entities of the spawner. The script expects the "ghost" entity to be the first child.
*   **`component_readwrite( EntityGetFirstComponent(target_id, "DamageModelComponent"), { hp = 0, max_hp = 0 }, function(comp) ... end)`**: This is a crucial part for balancing. It modifies the `DamageModelComponent` of the target enemy:
    *   It reduces the enemy's `max_hp` by 75% of its current value, but also ensures it doesn't decrease by more than 3 points.
    *   It then sets the enemy's current `hp` to its new `max_hp`.
*   **`EntitySetComponentIsEnabled(ghost_id, comp, true)`**: Iterates through all components of the ghost entity and enables them. This likely makes the ghost visible and active.
*   **`EntityRemoveFromParent(ghost_id)`**: Detaches the ghost from the spawner.
*   **`EntityAddChild(target_id, ghost_id)`**: Attaches the ghost as a child to the target enemy.
*   **`EntityKill(entity_id)`**: Removes the spawner entity from the game.

## Example Usage (Conceptual)

This script would be attached to an entity in the game world. When this entity is spawned and interacts with an enemy (likely through collision), it triggers the ghost attachment and health reduction effect. The "ghost" entity itself would need to be defined elsewhere, likely as a child of the spawner entity when it's initially placed in the game.

```lua
-- Conceptual structure of the spawner entity in its definition file:
-- {
--   "id": "tiny_ghost_spawner",
--   "components": [
--     {
--       "id": "SpawnerComponent",
--       "spawn_entity": "data/entities/animals/tiny_ghost_spawner.xml", -- This file
--       "spawn_count": 1,
--       "spawn_radius": 0,
--       "spawn_delay": 0,
--       "spawn_target_tag": "enemy"
--     },
--     {
--       "id": "LuaComponent",
--       "script": "data/scripts/animals/tiny_ghost_spawn.lua"
--     }
--     -- Potentially other components like Transform, Hitbox, etc.
--   ],
--   "children": [
--     {
--       "id": "tiny_ghost_entity", -- The ghost entity itself
--       "components": [
--         { "id": "TransformComponent" },
--         { "id": "SpriteComponent", "sprite": "data/sprites/ghost.png", "is_enabled": false }, -- Initially disabled
--         { "id": "DamageModelComponent", "hp": 1, "max_hp": 1 }, -- Example ghost stats
--         -- ... other ghost components
--       ]
--     }
--   ]
-- }
```