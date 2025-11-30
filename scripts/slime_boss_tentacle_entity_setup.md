---
title: Slime Boss Tentacle Entity Setup
category: scripts
---

# Slime Boss Tentacle Entity Setup

This script defines the physics bodies and joints for the tentacles of the Slime Boss enemy in Noita. It's responsible for creating the visual and physical representation of these appendages.

## Core Functionality

The primary function `add_tentacles()` is responsible for:

1.  **Getting Entity ID**: Retrieves the unique identifier for the entity being processed.
2.  **Defining Initial Position**: Sets a base `pos_x` and `pos_y` for the first tentacle segment.
3.  **Adding Physics Bodies**: Uses `PhysicsAddBodyImage` to attach visual sprites as physics bodies to the entity. Each tentacle segment is defined by a separate image file.
    *   `data/enemies_gfx/slimeboss_tentacle_0.png`
    *   `data/enemies_gfx/slimeboss_tentacle_1.png`
    *   `data/enemies_gfx/slimeboss_tentacle_2.png`
    *   `data/enemies_gfx/slimeboss_tentacle_3.png`
    *   The `meat` material is applied to these bodies.
    *   Subsequent tentacles are offset horizontally (`pos_x+22*n`) to create a chain.
4.  **Adding Physics Joints**: Uses `PhysicsAddJoint` to connect the tentacle segments, creating a flexible chain-like structure.
    *   A joint connects the entity's main body to the first tentacle segment (`t0`).
    *   Subsequent joints connect each tentacle segment to the next (`t0` to `t1`, `t1` to `t2`, `t2` to `t3`).

## Key Attributes & Elements

*   **`add_tentacles()` function**: The main entry point for setting up the tentacle physics.
*   **`GetUpdatedEntityID()`**: Essential for associating physics with the correct entity.
*   **`PhysicsAddBodyImage( entity_id, image_path, material, pos_x, pos_y )`**:
    *   `entity_id`: The target entity.
    *   `image_path`: Path to the sprite for the tentacle segment.
    *   `material`: Defines the physical properties (e.g., "meat").
    *   `pos_x`, `pos_y`: Relative position of the body.
*   **`PhysicsAddJoint( entity_id, body_a, body_b )`**:
    *   `entity_id`: The target entity.
    *   `body_a`, `body_b`: The physics bodies to connect. If `body_b` is an integer (like `1`), it connects to the entity's kinetic body.

## Example Usage (within the script)

```lua
-- This line directly calls the function to add tentacles when the script is loaded.
add_tentacles()
```

## Modding Considerations

*   **Visuals**: To change the appearance of the tentacles, replace the `.png` files referenced in `PhysicsAddBodyImage`. Ensure the new sprites have similar dimensions and pivot points for proper joint connection.
*   **Physics**: Adjusting the `pos_x` offsets in `PhysicsAddBodyImage` can alter the initial spread of the tentacles. Modifying the joint types or parameters (if more advanced joint functions were used) could change their flexibility and behavior.
*   **Material**: Changing the `material` string in `PhysicsAddBodyImage` can affect how the tentacles interact with the game world (e.g., damage, collision properties).