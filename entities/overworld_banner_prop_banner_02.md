---
title: Overworld Banner Prop (Banner 02)
category: entities
---

# Overworld Banner Prop (Banner 02)

This entity defines a decorative banner prop found in the overworld. It utilizes physics components to simulate its behavior and visual elements for its appearance.

## Key Components

### `PhysicsBody2Component`

This component defines the physical properties of the banner's structure.

*   **`allow_sleep`**: `1` - Allows the physics body to enter a sleep state when inactive, optimizing performance.
*   **`angular_damping`**: `0` - No resistance to rotational movement.
*   **`linear_damping`**: `0` - No resistance to linear movement.

### `PhysicsImageShapeComponent`

This component defines the visual representation and collision shape for parts of the banner.

*   **`body_id`**: Identifies which physics body this shape is associated with.
*   **`offset_x`, `offset_y`**: Adjusts the position of the image relative to its physics body.
*   **`image_file`**: Specifies the graphical asset used for this part of the prop.
    *   `data/props_gfx/overworld/pole_02.png`
    *   `data/props_gfx/overworld/pole_01_crossbeam.png`
*   **`material`**: `wood_prop_noplayerhit` - Defines the material properties, indicating it's a wooden prop that players cannot hit.
*   **`is_root`**: `1` - Marks this component as the root of the physics body.

### `PhysicsJoint2Component`

These components define the connections and constraints between different physics bodies, simulating how the banner is assembled.

*   **`type`**:
    *   `WELD_JOINT_ATTACH_TO_NEARBY_SURFACE`: Attaches a body to a nearby surface, likely for the main pole.
    *   `WELD_JOINT`: Creates a rigid weld between two specified bodies.
*   **`body1_id`, `body2_id`**: The IDs of the physics bodies being joined.
*   **`offset_x`, `offset_y`**: The relative position of the joint.
*   **`break_force`, `break_distance`**: The force or distance at which the joint will break.
*   **`break_on_body_modified`**: `1` - The joint will break if a connected body is modified.
*   **`ray_x`, `ray_y`**: Used for surface attachment joints to determine the attachment point.

### Child Entities (Verlet Chains)

The banner's cloth-like elements are implemented as separate entities using `verlet_chains`.

*   **`Base file="data/entities/verlet_chains/banner/banner.xml"`**: The main banner cloth.
    *   **`InheritTransformComponent`**: Allows inheriting and modifying the transform of the base entity.
    *   **`Transform position.x="-1" position.y="15"`**: Offsets the banner cloth relative to its parent.
*   **`Base file="data/entities/verlet_chains/ribbon/ribbon_01.xml"`**: A ribbon element.
    *   **`Transform position.x="12" position.y="12"`**: Offsets the ribbon.
*   **`Base file="data/entities/verlet_chains/ribbon/ribbon_02.xml"`**: Another ribbon element.
    *   **`Transform position.x="12" position.y="13"`**: Offsets the ribbon.

### `LuaComponent`

This component adds scripting functionality to the entity.

*   **`script_physics_body_modified="data/scripts/props/release_child_entities.lua"`**: Executes a Lua script when a physics body is modified. This script is likely responsible for releasing any attached child entities (like the banner cloth) when the main structure is damaged or broken.
*   **`remove_after_executed`**: `1` - The Lua component will be removed after its script has executed.
*   **`execute_every_n_frame`**: `-1` - The script is executed only once.