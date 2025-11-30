---
title: Test Physics Light Prop
category: scripts
---

# Test Physics Light Prop

This script defines a simple physics-based prop for testing purposes. It creates a chain-like structure using an image and applies physics to it.

## Key Functions

### `do_chain()`

This function is responsible for creating and configuring the physics-based chain entity.

#### Initialization

*   `entity_id`: Retrieves the ID of the entity being updated.
*   `pos_x`, `pos_y`: Defines the initial position of the chain.
*   `offset`: An offset value used in physics calculations.

#### Physics Setup

*   `PhysicsAddBodyImage( entity_id, "data/props_gfx/torch_hang_chain.png", "aluminium", pos_x, pos_y )`: Adds a physics body to the entity using the specified image (`torch_hang_chain.png`).
    *   **Material**: `aluminium` - This likely defines the physical properties of the chain.
    *   **Position**: `pos_x`, `pos_y` - Sets the initial coordinates.
*   `PhysicsAddJoint( entity_id, t0, 1 )`: Adds a joint to the physics body.
    *   `entity_id`: The entity to which the joint is attached.
    *   `t0`: The physics body created by `PhysicsAddBodyImage`.
    *   `1`: Likely a joint type or configuration parameter.

## Execution

The `do_chain()` function is called directly at the end of the script to execute the prop creation.