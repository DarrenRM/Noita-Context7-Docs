---
title: Physics Temple Door Entity
category: entities
---

# Physics Temple Door Entity

This document describes the `physics_templedoor.xml` entity, which represents a destructible temple door in Noita.

## Key Components

### Base Entity

The entity inherits from `base_item_physics.xml`, providing fundamental physics properties.

### PhysicsImageShapeComponent

Defines the visual representation and physical material of the door.

*   **`image_file`**: `data/props_gfx/temple_door.png` - Specifies the sprite for the door.
*   **`material`**: `metal_prop` - Sets the physical material, influencing its interaction with other physics objects.

### PhysicsBodyComponent

Configures the physics simulation for the door.

*   **`allow_sleep`**: `1` - Allows the body to enter a sleep state when inactive to save performance.
*   **`angular_damping`**: `0.01` - Reduces rotational velocity over time.
*   **`gridworld_box2d`**: `1` - Integrates the physics body into the grid-based physics world.
*   **`linear_damping`**: `0.1` - Reduces linear velocity over time.
*   **`kills_entity`**: `1` - Indicates that this physics body can destroy other entities it collides with.
*   **`force_add_update_areas`**: `1` - Ensures the physics body is always considered for updates, even if off-screen.

### LuaComponent

Attaches a Lua script to the entity for custom behavior.

*   **`_enabled`**: `0` - The script is initially disabled.
*   **`execute_every_n_frame`**: `1` - The script will execute every frame once enabled.
*   **`remove_after_executed`**: `1` - The Lua component will be removed after its script has executed.
*   **`script_source_file`**: `data/scripts/props/physics_templedoor.lua` - The path to the Lua script that controls the door's behavior.

### CameraBoundComponent

Manages the entity's visibility and interaction based on camera proximity.

*   **`max_count`**: `20` - The maximum number of such entities that can be active within the camera's view.
*   **`distance`**: `1000` - The maximum distance from the camera for the entity to be considered.