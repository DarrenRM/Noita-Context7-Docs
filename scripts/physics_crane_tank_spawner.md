---
title: Physics Crane Tank Spawner
category: scripts
---

# Physics Crane Tank Spawner

This script defines functions for creating a physics-based crane tank structure in Noita. It utilizes `PhysicsAddBodyCreateBox` and `PhysicsAddBodyImage` to construct the tank's components and `PhysicsAddJoint` to connect them, simulating a suspension bridge-like mechanism.

## Key Functions

### `do_crane_section(entity_id, width, height, offset_x, offset_y)`

This function creates a single segment of the crane structure. It defines four physics bodies (three boxes and one image) and connects them using revolute joints to form a basic crane arm segment.

#### Parameters:

*   `entity_id`: The unique identifier for the entity being created.
*   `width`: The width of the crane segment.
*   `height`: The height of the crane segment.
*   `offset_x`: The X-coordinate offset for the segment's position.
*   `offset_y`: The Y-coordinate offset for the segment's position.

#### Created Bodies:

*   `body1`: A box-shaped body representing a structural element.
*   `body3`: Another box-shaped body, positioned to form the other side of the segment.
*   `body2`: A box-shaped body connecting `body1` and `body3`.
*   `body4`: An image-based body (`physics_cross_beam_1.png`) acting as a crossbeam.

#### Joints:

*   Revolute joints connect `body1` to `body2`, `body2` to `body3`, and `body1`, `body2`, `body3` to `body4`.

### `do_suspension_bridge()`

This function orchestrates the creation of the entire crane tank structure. It repeatedly calls `do_crane_section` to build multiple segments and then adds the main tank body, connecting it to the last segment.

#### Logic:

1.  Initializes variables for segment dimensions and body IDs.
2.  Loops three times to create multiple crane segments, stacking them vertically.
3.  In each iteration, it calls `do_crane_section` and connects the new segment to the previous one using revolute joints.
4.  After creating the segments, it adds the main tank body using `PhysicsAddBodyImage` with `physics_tank_visual.png` and `physics_tank.png` for visual and collision properties respectively.
5.  Finally, it connects the tank body to the last crane segment.

#### Created Tank Body:

*   `tanker`: An image-based body representing the main tank, using `data/biome_impl/physics_tank_visual.png` for visuals and `data/biome_impl/physics_tank.png` for physics.

## Key Attributes and Elements

*   **Materials**: Primarily uses `"wood_prop"` for structural components.
*   **Physics Bodies**:
    *   `PhysicsAddBodyCreateBox`: Used for creating rectangular structural elements.
    *   `PhysicsAddBodyImage`: Used for creating the crossbeam and the main tank body, allowing for custom sprites.
*   **Joints**:
    *   `PhysicsAddJoint`: Specifically uses `"REVOLUTE_JOINT"` to allow for rotational movement between connected bodies, simulating a flexible structure.
*   **Image Files**:
    *   `data/props_gfx/physics_cross_beam_1.png`: Sprite for the crossbeam.
    *   `data/biome_impl/physics_tank_visual.png`: Visual sprite for the tank.
    *   `data/biome_impl/physics_tank.png`: Physics sprite for the tank.
*   **Structure Generation**: The script employs a loop to procedurally generate multiple segments, creating a scalable structure.

This script is a foundational example of how to create complex physics-based props in Noita using Lua scripting.