---
title: Orb 07 Pitcheck B Entity
category: entities
---

# Orb 07 Pitcheck B Entity

This entity is a trigger designed to detect when the player enters a specific "pit" area. When triggered, it executes a Lua script.

## Key Components

### CollisionTriggerComponent

This component defines the collision area that, when entered by an entity with the `player_unit` tag, will activate the entity.

*   **`width`**: 96
*   **`height`**: 430
*   **`radius`**: 430
*   **`destroy_this_entity_when_triggered`**: 0 (The trigger itself is not destroyed upon activation)
*   **`required_tag`**: `player_unit` (Only the player can trigger this)

### LuaComponent

This component links the collision trigger to a specific Lua script that will be executed upon activation.

*   **`script_collision_trigger_hit`**: `data/scripts/buildings/orb_07_pitcheck_b.lua` (The script to run when the trigger is hit)
*   **`execute_every_n_frame`**: -1 (The script executes only once when triggered)

## Purpose

The primary purpose of this entity is to act as a localized trigger. The comment `<!-- this spawns squidward -->` suggests that the associated Lua script (`orb_07_pitcheck_b.lua`) is responsible for spawning a specific entity (likely "squidward") when the player enters the defined collision area. This is a common pattern for creating unique events or encounters in specific locations within the game world.