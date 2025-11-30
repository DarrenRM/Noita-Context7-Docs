---
title: Physics Heavy Test Prop
category: scripts
---

# Physics Heavy Test Prop

This script defines a simple physics-based prop for testing purposes in Noita. It creates a physics body with a specific image and material, and then attaches a joint to it.

## Key Functions

### `do_chain()`

This function is responsible for creating and configuring the physics prop.

### `PhysicsAddBodyImage( entity_id, image_path, material_name, pos_x, pos_y )`

Adds a physics body to an entity using an image file.

*   **`entity_id`**: The unique identifier of the entity to which the physics body will be added.
*   **`image_path`**: The path to the image file used for the physics body's shape.
*   **`material_name`**: The name of the material to be applied to the physics body.
*   **`pos_x`**: The X-coordinate offset for the physics body.
*   **`pos_y`**: The Y-coordinate offset for the physics body.

Returns the ID of the created physics body.

### `PhysicsAddJoint( entity_id, body_id, joint_type )`

Adds a joint to a physics body.

*   **`entity_id`**: The unique identifier of the entity.
*   **`body_id`**: The ID of the physics body to which the joint will be attached.
*   **`joint_type`**: The type of joint to add. In this case, `1` likely represents a specific joint type (e.g., a hinge or ball joint, depending on Noita's internal implementation).

## Script Logic

1.  **Get Entity ID**: `GetUpdatedEntityID()` retrieves the ID of the entity that is currently being processed.
2.  **Define Position and Offset**:
    *   `pos_x` is set to `-2`.
    *   `pos_y` is set to `-11`.
    *   `offset` is set to `-5.5`.
3.  **Add Physics Body**:
    *   `PhysicsAddBodyImage` is called to create a physics body.
    *   The image used is `"data/temp/martin_lol.png"`.
    *   The material is `"aluminium"`.
    *   The body is positioned with the defined `pos_x` and `pos_y`.
    *   The returned physics body ID is stored in `t0`.
4.  **Add Joint**:
    *   `PhysicsAddJoint` is called to add a joint to the physics body `t0`.
    *   The `joint_type` is set to `1`.
5.  **Execute `do_chain()`**: The `do_chain()` function is called to initiate the creation of the physics prop.

## Example Usage (for modders)

This script serves as a basic template for creating physics-enabled props. Modders can adapt this by:

*   Changing the `image_path` to use custom sprites.
*   Experimenting with different `material_name` values for varied physical properties.
*   Adjusting `pos_x`, `pos_y`, and `offset` to control the initial placement and orientation.
*   Exploring different `joint_type` values to create more complex physics interactions.