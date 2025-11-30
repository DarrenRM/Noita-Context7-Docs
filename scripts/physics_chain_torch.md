---
title: Physics Chain Torch
category: scripts
---

# Physics Chain Torch

This script defines the physics behavior for a chain-like structure, likely used for hanging torches or similar props in Noita. It utilizes `PhysicsAddBodyImage` to create individual segments of the chain and `PhysicsAddJoint` to connect them, simulating a flexible chain.

## Core Functionality: `do_chain()`

The `do_chain` function is responsible for setting up the physics simulation of the chain.

### Key Parameters and Operations:

*   **`entity_id`**: The unique identifier for the entity being manipulated.
*   **`pos_x`, `pos_y`, `offset`**: These variables define the initial positioning and spacing of the chain segments.
*   **`PhysicsAddBodyImage( entity_id, "data/props_gfx/torch_hang_chain.png", "metal_chain_nohit", x, y )`**: This function adds a physics body to the entity.
    *   The first argument is the `entity_id`.
    *   The second argument specifies the image file used for the physics body's shape.
    *   The third argument defines the material type, influencing its physical properties (e.g., "metal\_chain\_nohit" suggests a non-damaging metal chain).
    *   The `x` and `y` coordinates determine the position of the body.
*   **`PhysicsAddJoint( entity_id, body1_id, body2_id, [x_offset], [y_offset] )`**: This function connects two physics bodies with a joint.
    *   `entity_id`: The entity the bodies belong to.
    *   `body1_id`, `body2_id`: The IDs of the bodies to connect. If `body2_id` is `-1`, it connects to a fixed point in the world.
    *   Optional `x_offset` and `y_offset` can be used to fine-tune the joint's connection point relative to `body2_id`.

### Chain Segment Creation:

The script creates multiple chain segments by calling `PhysicsAddBodyImage` with slightly offset `y` positions.

```lua
	local t1 = PhysicsAddBodyImage( entity_id, "data/props_gfx/torch_hang_chain.png", "metal_chain_nohit", pos_x, pos_y + offset*0.4 )
	local t2 = PhysicsAddBodyImage( entity_id, "data/props_gfx/torch_hang_chain.png", "metal_chain_nohit", pos_x, pos_y + offset*1.4 )
	local t3 = PhysicsAddBodyImage( entity_id, "data/props_gfx/torch_hang_chain.png", "metal_chain_nohit", pos_x, pos_y + offset*2.4 )
```

### Joint Connections:

The script then connects these segments using `PhysicsAddJoint`.

```lua
	-- Connect the first segment to a fixed point (likely the torch itself or a ceiling)
	PhysicsAddJoint( entity_id, t1, 1, 0, -6 )

	-- Connect consecutive chain segments
	PhysicsAddJoint( entity_id, t1, t2 )
	PhysicsAddJoint( entity_id, t2, t3 )

	-- Connect the last segment to a fixed point in the world
	PhysicsAddJoint( entity_id, t3, -1, 0, pos_y + offset*2.75 )
```

The `t1, 1, 0, -6` and `t3, -1, 0, pos_y + offset*2.75` calls indicate connections to specific points relative to the entity's origin or to a fixed world position (`-1`).

## Usage

This script is intended to be attached to an entity that requires a physics-simulated chain, such as a torch that hangs and sways. The `do_chain()` function is called directly at the end of the script to initialize the physics setup when the entity is loaded.