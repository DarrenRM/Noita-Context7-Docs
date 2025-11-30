---
title: Physics Chandelier Chain
category: scripts
---

# Physics Chandelier Chain

This script defines the physics behavior for a chandelier-like structure, creating a chain of connected physics bodies.

## Core Functionality

The `do_chain()` function is responsible for generating the physics elements and their connections.

### Key Physics Elements

The script utilizes `PhysicsAddBodyImage` to create individual segments of the chain.

*   **`PhysicsAddBodyImage( entity_id, image_path, material, pos_x, pos_y )`**: Adds a physics body to an entity, defined by an image.
    *   `entity_id`: The ID of the entity to which the physics body is added.
    *   `image_path`: The path to the image file defining the shape of the physics body (e.g., `"data/props_gfx/torch_hang_chain.png"`).
    *   `material`: The material of the physics body (e.g., `"aluminium"`). This affects its physical properties.
    *   `pos_x`, `pos_y`: The relative position of the physics body.

### Key Physics Connections

The script uses `PhysicsAddJoint` to link these physics bodies together, simulating a chain.

*   **`PhysicsAddJoint( entity_id, body_a, body_b, [offset_a_x], [offset_a_y] )`**: Adds a joint between two physics bodies.
    *   `entity_id`: The ID of the entity containing the physics bodies.
    *   `body_a`: The ID of the first physics body.
    *   `body_b`: The ID of the second physics body.
    *   `offset_a_x`, `offset_a_y` (optional): Offsets for the joint connection point on `body_a`.

### Chain Structure

The script creates a series of chain links with specific offsets to form a hanging chain.

*   **Link 1 (`t1`)**: Attached at `pos_x`, `pos_y + offset*0.4`.
*   **Link 2 (`t2`)**: Attached at `pos_x`, `pos_y + offset*1.4`.
*   **Link 3 (`t3`)**: Attached at `pos_x`, `pos_y + offset*2.4`.

### Joint Connections

*   **`PhysicsAddJoint( entity_id, t1, 1, 0, -8 )`**: Connects `t1` to a fixed point (represented by `1`) with an offset. This likely anchors the top of the chain.
*   **`PhysicsAddJoint( entity_id, t1, t2 )`**: Connects `t1` to `t2`.
*   **`PhysicsAddJoint( entity_id, t2, t3 )`**: Connects `t2` to `t3`.
*   **`PhysicsAddJoint( entity_id, t3, -1, 0, pos_y + offset*2.5 )`**: Connects `t3` to a fixed point (`-1`) at a specific position, likely the bottom anchor or a decorative element.

## Usage

This script is intended to be attached to an entity that should behave as a physics-based chandelier. The `do_chain()` function is called directly upon script execution.