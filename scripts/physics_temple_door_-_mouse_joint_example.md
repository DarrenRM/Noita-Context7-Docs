---
title: Physics Temple Door - Mouse Joint Example
category: guides
---

-- This script is intended to be used with AI-assisted modding tools for Noita.
-- It provides a basic example of how to create a physics-based joint,
-- specifically a mouse joint, which can be used to attach entities to the player's cursor.
-- The script defines a function `do_mouse_joint` that adds a mouse joint to the entity
-- it's attached to. The joint is positioned slightly above the entity's origin.
--
-- The commented-out section shows potential further modifications, such as
-- adjusting joint properties or setting a timeout to remove the joint.
--
-- For AI-assisted modding, this script can serve as a template for:
-- - Understanding how to interact with Noita's physics engine.
-- - Creating dynamic and interactive elements in mods.
-- - Implementing player-controlled physics objects.
--
-- Key functions used:
-- - GetUpdatedEntityID(): Retrieves the ID of the entity the script is attached to.
-- - PhysicsAddJoint(): Adds a physics joint between two entities or an entity and a fixed point.
--   - The arguments are:
--     - `entity_id`: The ID of the first entity.
--     - `entity_id2`: The ID of the second entity (or -1 for a fixed point).
--     - `joint_type`: The type of joint to create (e.g., "MOUSE_JOINT").
--     - `pos_x`, `pos_y`: The local offset from the entity's origin for the joint.
--
-- Example usage:
-- Attach this script to an entity in your Noita mod. When the entity is loaded,
-- the `do_mouse_joint()` function will be called, creating a mouse joint.
--
-- Note: The commented-out code suggests advanced usage that might require
-- further exploration of Noita's API for `PhysicsJointComponent` and `Component_SetTimeOut`.
```

---
title: Physics Temple Door - Mouse Joint Example
category: scripts
---

# Physics Temple Door - Mouse Joint Example

This script demonstrates the creation of a physics-based mouse joint in Noita.

## Core Functionality

The primary function, `do_mouse_joint()`, is responsible for adding a physics joint to the entity it's attached to. This joint is configured as a "MOUSE_JOINT", allowing it to be controlled by the player's cursor.

### `do_mouse_joint()`

This function performs the following actions:

1.  **Get Entity ID**: Retrieves the unique identifier of the entity the script is currently attached to using `GetUpdatedEntityID()`.
2.  **Define Joint Position**: Sets local offset coordinates (`pos_x`, `pos_y`) for the joint. In this case, the joint is positioned `0` units horizontally and `-13` units vertically relative to the entity's origin.
3.  **Add Mouse Joint**: Utilizes `PhysicsAddJoint()` to create the mouse joint.
    *   The first argument is the `entity_id` of the object to be controlled.
    *   The second argument (`1`) is a placeholder and might refer to a specific body within the entity.
    *   The third argument (`-1`) indicates that the joint is attached to a fixed point in the world (effectively, the mouse cursor's position).
    *   `pos_x` and `pos_y` define the local anchor point on the entity.
    *   `"MOUSE_JOINT"` specifies the type of joint.

### Key Attributes/Elements

*   **`GetUpdatedEntityID()`**: Essential for targeting the correct entity.
*   **`PhysicsAddJoint()`**: The core function for creating physics constraints.
*   **`"MOUSE_JOINT"`**: The specific type of joint, enabling cursor control.
*   **`pos_x`, `pos_y`**: Define the anchor point on the entity, influencing how it's pulled.
*   **`-1` (for `entity_id2`)**: Indicates attachment to a world-fixed point, typically the mouse.

### Example Usage

To use this script:

1.  Create or select an entity in your Noita mod.
2.  Attach this Lua script to that entity.
3.  When the entity loads in-game, it will gain a physics joint that can be manipulated by the player's mouse cursor.

### Commented-Out Code (Advanced)

The script includes commented-out sections that hint at more advanced functionalities:

*   **`EntityGetComponent( entity_id, "PhysicsJointComponent" )`**: Suggests how to access and modify properties of existing physics joints.
*   **`ComponentSetValue( joint, "delta_y", -1 )`**: Shows how to alter specific joint parameters, like the vertical offset.
*   **`Component_SetTimeOut( 5*60, "data/scripts/props/physics_stopmousejoint.lua" )`**: Indicates a mechanism to automatically remove the joint after a set duration (5 minutes in this example) by executing another script.

These commented sections are valuable for understanding how to further customize and control physics joints beyond their initial creation.