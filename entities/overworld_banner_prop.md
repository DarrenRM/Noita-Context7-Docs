---
title: Overworld Banner Prop
category: entities
---

# Overworld Banner Prop

This entity defines a static banner prop found in the overworld. It utilizes physics components to create a visual representation of a banner attached to a wooden pole.

## Key Components

### PhysicsBody2Component
Defines the physical properties of the banner's pole.

*   `allow_sleep`: `1` (Allows the physics body to go to sleep when inactive)
*   `angular_damping`: `0` (No angular damping)
*   `linear_damping`: `0` (No linear damping)

### PhysicsImageShapeComponent (Pole)
Defines the visual shape and collision for the main pole of the banner.

*   `offset_x`: `-9`
*   `offset_y`: `-59`
*   `image_file`: `data/props_gfx/overworld/pole_01.png` (The sprite for the pole)
*   `material`: `wood_prop_noplayerhit` (Material type, likely affects interactions)
*   `is_root`: `1` (This is the primary physics body)

### PhysicsImageShapeComponent (Crossbeam)
Defines the visual shape and collision for the horizontal crossbeam of the banner.

*   `offset_x`: `-16`
*   `offset_y`: `-49`
*   `image_file`: `data/props_gfx/overworld/pole_01_crossbeam.png` (The sprite for the crossbeam)
*   `material`: `wood_prop_noplayerhit`

### PhysicsJoint2Component (WELD_JOINT_ATTACH_TO_NEARBY_SURFACE)
Attaches the pole to the environment.

*   `type`: `WELD_JOINT_ATTACH_TO_NEARBY_SURFACE` (Weld joint that attaches to the closest surface)
*   `body_id`: `0` (Attaches to the pole)
*   `break_force`: `2`
*   `break_distance`: `8`
*   `break_on_body_modified`: `1`
*   `ray_x`: `0`
*   `ray_y`: `8`

### PhysicsJoint2Component (WELD_JOINT)
Connects the crossbeam to the pole.

*   `type`: `WELD_JOINT` (Standard weld joint)
*   `body1_id`: `0` (The pole)
*   `body2_id`: `1` (The crossbeam)
*   `offset_x`: `-6`
*   `offset_y`: `-46`
*   `break_force`: `1`
*   `break_distance`: `8`
*   `break_on_body_modified`: `1`

### Cloths (Entities)
These entities define the visual cloth elements of the banner, using Verlet chain physics for dynamic movement.

*   **Banner Cloth:**
    *   `Base file`: `data/entities/verlet_chains/banner/banner.xml`
    *   `InheritTransformComponent` with `position.x="3"`, `position.y="11"`

*   **Ribbon 01:**
    *   `Base file`: `data/entities/verlet_chains/ribbon/ribbon_01.xml`
    *   `InheritTransformComponent` with `position.x="13"`, `position.y="12"`

*   **Ribbon 02:**
    *   `Base file`: `data/entities/verlet_chains/ribbon/ribbon_02.xml`
    *   `InheritTransformComponent` with `position.x="-4"`, `position.y="15"`

### LuaComponent
Handles script-based logic for the prop.

*   `script_physics_body_modified`: `data/scripts/props/release_child_entities.lua` (Likely used to clean up child entities when the main body is modified or destroyed)
*   `remove_after_executed`: `1`
*   `execute_every_n_frame`: `-1` (Indicates it runs once or on specific events)