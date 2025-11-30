---
title: Physics Suspension Bridge Spawner
category: scripts
---

---

# Physics Suspension Bridge Spawner

This script defines a mechanism for procedurally generating a suspension bridge made of physics-based segments. It uses raycasting to determine the available space and then spawns a series of connected rectangular physics bodies to form the bridge.

## Core Functionality

The primary function `do_suspension_bridge()` orchestrates the creation of the bridge. It performs the following key steps:

1.  **Determine Bridge Span:**
    *   Uses a helper function `raytrace` to cast rays horizontally from the entity's position to find the extent of the available space.
    *   `raytrace(x, y, direction, max_length)`: Casts rays from `(x, y)` in the specified `direction` up to `max_length`. It returns the furthest hit point.
    *   Calculates `min_x` and `max_x` to define the bridge's horizontal boundaries.

2.  **Calculate Segment Properties:**
    *   Determines the total `bridge_width` based on the raycast results.
    *   Defines the number of `segments` (defaulting to 6) and an `overlap` value for connecting segments.
    *   Calculates the `width` and `height` of each individual bridge segment.

3.  **Spawn Physics Bodies and Joints:**
    *   Iterates through the calculated number of `segments`.
    *   For each segment:
        *   `PhysicsAddBodyCreateBox(entity_id, "wood_prop", pos_x, pos_y, width, height)`: Creates a rectangular physics body.
            *   `entity_id`: The ID of the entity spawning the body.
            *   `"wood_prop"`: The material tag for the body.
            *   `pos_x`, `pos_y`: The position of the body's center.
            *   `width`, `height`: The dimensions of the box.
        *   `PhysicsAddJoint(entity_id, body_id0, body_id1, offset_x, offset_y, joint_type, is_motor)`: Connects two physics bodies with a joint.
            *   `entity_id`: The ID of the entity managing the joint.
            *   `body_id0`, `body_id1`: The IDs of the bodies to connect. `-1` can be used to connect to the world or a fixed point.
            *   `offset_x`, `offset_y`: The relative offset from the center of `body_id0` where the joint is attached.
            *   `joint_type`: The type of joint (e.g., `"REVOLUTE_JOINT"`).
            *   `is_motor`: Whether the joint acts as a motor.
    *   Connects each new segment to the previous one using a `REVOLUTE_JOINT` to allow for flexibility.
    *   The first segment is connected to the world (implicitly or explicitly via a fixed point), and the last segment is also connected to the world.

## Key Attributes and Parameters

*   **`raytrace` function:**
    *   `x0`, `y0`: Starting coordinates for raycasting.
    *   `x_direction`: Direction of the ray (-1 for left, 1 for right).
    *   `max_length`: Maximum distance to cast the ray.

*   **`do_suspension_bridge` function:**
    *   `segments`: Number of individual planks that make up the bridge.
    *   `overlap`: The amount each segment overlaps with the next for joint connection.
    *   `height`: The vertical dimension of each bridge segment.
    *   `"wood_prop"`: The material tag applied to each bridge segment. This influences its physical properties and appearance.
    *   `"REVOLUTE_JOINT"`: The type of joint used to connect segments, allowing them to pivot relative to each other.

## Example Usage

This script is typically attached to an entity that acts as a "spawner" for the bridge. When the game processes this entity, the `do_suspension_bridge()` function is called, and the bridge is generated in the game world.

```lua
-- Example of how this script might be attached to an entity
-- (This is conceptual and not part of the provided script itself)

-- In an entity definition file:
-- entity_new("suspension_bridge_spawner", {
--     transform = { x = 100, y = 50 },
--     components = {
--         { id = "scripts", script_path = "data/scripts/props/physics_spawners/physics_suspension_bridge.lua" }
--     }
-- })
```

## Notes for Modding

*   **Customization:** Adjust `segments`, `overlap`, and `height` to change the bridge's appearance and behavior.
*   **Materials:** The `"wood_prop"` tag can be replaced with other material tags defined in Noita's data to alter the bridge's physical properties (e.g., density, friction).
*   **Joint Types:** Experiment with different `joint_type` values if Noita supports them for more complex bridge mechanics.
*   **Raycasting:** The `raytrace` function is crucial. Its parameters (`max_length`, the offset in the loop `y - 3 + i * 3`) can be modified to change how the bridge detects its environment.