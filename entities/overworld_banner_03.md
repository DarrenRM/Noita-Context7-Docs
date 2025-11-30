---
title: Overworld Banner 03
category: entities
---

# Overworld Banner 03

This entity represents a decorative banner found in the overworld. It utilizes physics components for its visual representation and a Verlet chain for the cloth-like appearance of the banner itself.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the banner's pole.

*   `allow_sleep`: `1` (Enables physics sleeping for performance)
*   `angular_damping`: `0` (No angular damping)
*   `linear_damping`: `0` (No linear damping)

### PhysicsImageShapeComponent
Defines the visual shape and material of the banner pole.

*   `body_id`: `0` (References the physics body)
*   `offset_x`: `-9` (Horizontal offset for the image)
*   `offset_y`: `-59` (Vertical offset for the image)
*   `image_file`: `data/props_gfx/overworld/pole_02.png` (The sprite for the banner pole)
*   `material`: `wood_prop_noplayerhit` (Material type, preventing player interaction)
*   `is_root`: `1` (This is the root physics object)

### PhysicsJoint2Component
Connects the banner pole to the environment, simulating a fixed attachment.

*   `type`: `WELD_JOINT_ATTACH_TO_NEARBY_SURFACE` (Type of joint, welding to a surface)
*   `body1_id`: `0` (The physics body being attached)
*   `break_force`: `2` (Force required to break the joint)
*   `break_distance`: `8` (Distance at which the joint breaks)
*   `break_on_body_modified`: `1` (Joint breaks if the body is modified)
*   `ray_x`: `0`
*   `ray_y`: `8`

### Cloth Components (Verlet Chains)
These entities define the visual appearance of the banner cloth using pre-defined ribbon assets.

*   Each `Entity` with a `Base` pointing to a `verlet_chains/ribbon/` file creates a segment of the banner.
*   `InheritTransformComponent` with `Transform` allows for precise positioning of each ribbon segment relative to the pole.

#### Example Ribbon Segment:
```xml
<Entity>
    <Base file="data/entities/verlet_chains/ribbon/ribbon_01.xml">
        <InheritTransformComponent>
            <Transform
                position.x="11"
                position.y="14" >
            </Transform>
        </InheritTransformComponent>
    </Base>
</Entity>
```

### LuaComponent
Handles script-based logic for the entity.

*   `script_physics_body_modified`: `data/scripts/props/release_child_entities.lua` (Script executed when the physics body is modified, likely to handle breaking or removal)
*   `remove_after_executed`: `1` (The script will be removed after execution)
*   `execute_every_n_frame`: `-1` (Script executes only once)

## Summary

The `banner_03.xml` entity creates a static banner object. It consists of a wooden pole with physics properties and a visual sprite. Attached to this pole are multiple ribbon entities, styled using Verlet chains, to simulate the flowing appearance of a banner. A Lua script is included to manage potential physics interactions or cleanup.