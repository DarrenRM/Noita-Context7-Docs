---
title: Physics Debug Table Entity
category: entities
---

# Physics Debug Table Entity

This entity demonstrates the use of `PhysicsBody2Component` and `PhysicsImageShapeComponent` to create a breakable table object with multiple connected parts. It utilizes `PhysicsJoint2Component` to define the connections between these parts.

## Key Components

### PhysicsBody2Component

This component defines the fundamental physics properties of the entity.

*   **allow\_sleep**: `1` - Allows the physics body to enter a sleep state when inactive, optimizing performance.
*   **angular\_damping**: `0` - No rotational friction applied.
*   **linear\_damping**: `0` - No linear friction applied.

### PhysicsImageShapeComponent

This component defines the physical shape of an entity based on an image file. Multiple instances are used to create the different parts of the table.

*   **body\_id**: Unique identifier for the physics body this shape is attached to.
*   **offset\_x**, **offset\_y**: Position offset of the shape relative to the entity's origin.
*   **image\_file**: Path to the sprite used for the shape.
*   **material**: The material type, affecting interactions with other physics objects (e.g., `wood_prop`).
*   **is\_root**: `1` - Indicates this is the primary body for the entity.

### PhysicsJoint2Component

This component creates a joint between two physics bodies, allowing them to interact physically.

*   **type**: `WELD_JOINT` - Creates a rigid connection between two bodies, as if they were welded together.
*   **break\_force**: `1.3` - The force required to break this joint.
*   **offset\_x**, **offset\_y**: Position offset of the joint.
*   **body1\_id**, **body2\_id**: The IDs of the two physics bodies being connected.

## Entity Structure Breakdown

The entity is constructed from several `PhysicsImageShapeComponent` instances, representing different parts of the table:

1.  **Table Top (Part 1)**:
    *   `body_id="0"`
    *   `image_file="data/props_breakable_gfx/table_a_00.png"`
    *   `material="wood_prop"`
    *   `is_root="1"`

2.  **Table Top (Part 2)**:
    *   `body_id="1"`
    *   `image_file="data/props_breakable_gfx/table_a_01.png"`
    *   `material="wood_prop"`
    *   Connected to `body_id="0"` via a `WELD_JOINT` at `offset_x="8", offset_y="0"`.

3.  **Feet (Left)**:
    *   `body_id="2"`
    *   `image_file="data/props_breakable_gfx/table_a_02.png"`
    *   `material="wood_prop"`
    *   Connected to `body_id="0"` via a `WELD_JOINT` at `offset_x="1", offset_y="2"`.

4.  **Feet (Right)**:
    *   `body_id="3"`
    *   `image_file="data/props_breakable_gfx/table_a_02.png"`
    *   `material="wood_prop"`
    *   Connected to `body_id="1"` via a `WELD_JOINT` at `offset_x="13", offset_y="2"`.

This setup creates a table where the two top pieces are welded together, and each top piece is then welded to its respective leg. The `break_force` on these joints determines how easily the table will shatter when subjected to force.