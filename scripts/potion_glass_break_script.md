---
title: Potion Glass Break Script
category: scripts
---

# Potion Glass Break Script

This script defines the behavior when a potion entity breaks, specifically causing it to shatter into glass shards.

## Core Functionality

The primary purpose of this script is to handle the destruction of potion entities by spawning multiple physics-based glass shard entities.

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the potion entity is destroyed. It triggers the spawning of glass shards.

*   **`entity_id`**: The ID of the potion entity that is breaking.
*   **`pos_x`, `pos_y`**: The position of the breaking potion.
*   **`SetRandomSeed( pos_x, pos_y )`**: Initializes a random seed based on the potion's position for varied shard behavior.
*   **`throw_glass_shard(...)`**: This function is called multiple times to spawn different glass shard entities at slightly offset positions relative to the original potion.

### `throw_glass_shard( potion_entity, entity_file, pos_x, pos_y )`

This helper function is responsible for creating and launching a single glass shard.

*   **`potion_entity`**: The entity ID of the potion that broke.
*   **`entity_file`**: The XML file path for the glass shard entity to be spawned (e.g., `data/entities/props/physics_glass_shard_01.xml`).
*   **`pos_x`, `pos_y`**: The desired spawn position for the shard.
*   **`edit_component( potion_entity, "VelocityComponent", ... )`**: Modifies the velocity of the original potion entity to influence the initial velocity of the shards.
*   **`EntityLoad( entity_file, pos_x, pos_y )`**: Loads the specified glass shard entity at the given position.
*   **`PhysicsApplyForce( entity, vx, vy )`**: Applies a calculated force to the newly spawned shard to give it initial momentum.

## Key Elements

*   **Entity Spawning**: Utilizes `EntityLoad` to create new entities from predefined XML files.
*   **Physics Interaction**: Employs `PhysicsApplyForce` and `VelocityComponent` manipulation to simulate realistic shard scattering.
*   **Randomization**: Uses `Random` and `SetRandomSeed` to ensure a slightly different shard pattern and velocity each time a potion breaks.
*   **Modular Design**: The `throw_glass_shard` function promotes reusability for spawning different types of shards.

## Example Usage (within the `death` function)

```lua
-- Spawns four different glass shard entities with slight positional offsets
throw_glass_shard( entity_id, "data/entities/props/physics_glass_shard_01.xml", pos_x-1, pos_y-1 )
throw_glass_shard( entity_id, "data/entities/props/physics_glass_shard_02.xml", pos_x-1, pos_y+1 )
throw_glass_shard( entity_id, "data/entities/props/physics_glass_shard_03.xml", pos_x+1, pos_y-1 )
throw_glass_shard( entity_id, "data/entities/props/physics_glass_shard_04.xml", pos_x+1, pos_y+1 )
```