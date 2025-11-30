---
title: Temporary Glass Break Potion Script
category: scripts
---

# Temporary Glass Break Potion Script

This script defines the behavior for a potion that breaks into glass shards upon destruction.

## Core Functionality

The primary function of this script is to simulate the shattering of a potion into multiple physics-based glass shards when the potion entity is destroyed.

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the potion entity is destroyed. It triggers the creation and scattering of glass shards.

*   **`entity_id`**: The unique identifier of the potion entity being destroyed.
*   **`pos_x`, `pos_y`**: The position of the potion entity at the time of destruction.
*   **`SetRandomSeed( pos_x, pos_y )`**: Initializes a random seed based on the potion's position to ensure varied shard behavior.
*   **`throw_glass_shard(...)`**: This function is called four times to create and launch individual glass shards. Each call specifies a different shard entity file and a slightly offset position.

### `throw_glass_shard( potion_entity, entity_file, pos_x, pos_y )`

This helper function creates a single glass shard and applies physics to it.

*   **`potion_entity`**: The entity ID of the potion that is breaking.
*   **`entity_file`**: The XML file path for the glass shard entity to be spawned (e.g., `data/entities/props/physics_glass_shard_01.xml`).
*   **`pos_x`, `pos_y`**: The initial position where the shard will be spawned.

#### Key Actions within `throw_glass_shard`:

1.  **Velocity Calculation**:
    *   `vx,vy = vec_rotate( Random(1,2), 0, Random(0,math.pi*2.0) )`: Generates an initial random velocity for the shard, with a magnitude between 1 and 2, and a random direction.
    *   `edit_component( potion_entity, "VelocityComponent", ... )`: Modifies the velocity of the *original potion entity* to influence the shard's initial velocity. It applies a slight rotation and scales down the potion's existing velocity, adding it to the shard's calculated velocity. This creates a more organic scattering effect.

2.  **Entity Spawning**:
    *   `local entity = EntityLoad( entity_file, pos_x, pos_y )`: Loads the specified glass shard entity at the given position.

3.  **Physics Application**:
    *   `PhysicsApplyForce( entity, vx, vy )`: Applies the calculated velocity as a force to the newly spawned shard, making it move.
    *   `component_write( EntityGetFirstComponent( entity, "PhysicsBodyComponent"), { on_death_really_leave_body=false} )`: Configures the physics body component to prevent the shard from leaving its body upon death (relevant for its own destruction).

4.  **Lifetime Management**:
    *   `component_write( EntityGetFirstComponent( entity, "LifetimeComponent"), { lifetime = 720 + Random(-120,120) } )`: Sets a random lifetime for the shard, ranging from 600 to 840 frames (10 to 14 seconds), after which it will disappear.