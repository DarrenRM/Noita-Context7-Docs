---
title: Physics Chandelier Entity
category: entities
---

# Physics Chandelier Entity

This document describes the `physics_chandelier.xml` entity, which represents a destructible chandelier with lighting and flame effects in Noita.

## Key Components

### PhysicsBodyComponent
Manages the physical properties of the chandelier.

*   `allow_sleep`: `1` - Allows the physics body to sleep when inactive.
*   `angular_damping`: `0.1` - Controls how quickly rotational motion decays.
*   `fixed_rotation`: `0` - Allows the chandelier to rotate freely.
*   `on_death_leave_physics_body`: `1` - Ensures the physics body remains after destruction.

### PhysicsImageShapeComponent
Defines the visual shape and material of the chandelier for physics interactions.

*   `image_file`: `data/props_gfx/chandelier.png` - The sprite used for the chandelier's shape.
*   `material`: `metal_nohit` - The material type, indicating it's not directly damaged by hits.

### LuaComponent (Script Execution)
Executes Lua scripts to control behavior.

*   **Primary Script:**
    *   `execute_every_n_frame`: `1` - Runs the script every frame.
    *   `remove_after_executed`: `1` - Removes the component after the script runs once.
    *   `script_source_file`: `data/scripts/props/physics_chandelier.lua` - The main script for chandelier logic.
*   **Damage Script:**
    *   `script_physics_body_modified`: `data/scripts/props/physics_chain_torch_damaged.lua` - Script executed when the physics body is modified (e.g., damaged).

### HitboxComponent
Defines the collision area of the chandelier.

*   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Define the bounding box for physics interactions.

### LightComponent
Adds a light source to the chandelier.

*   `radius`: `120` - The range of the light.
*   `fade_out_time`: `1.5` - How long the light takes to fade out.
*   `offset_y`: `-15` - Vertical offset of the light source.

### SpriteComponent (Flames)
Renders the flame animation on the chandelier.

*   `image_file`: `data/props_gfx/chandelier_flames.xml` - The sprite sheet for the flame animation.
*   `emissive`: `1` - Makes the sprite emit light.
*   `rect_animation`: `stand` - Specifies the default animation state.

### CameraBoundComponent
Manages the entity's visibility and behavior based on camera distance.

*   `max_count`: `50` - Maximum number of such entities the camera can track.
*   `distance`: `500` - The distance from the camera at which the entity becomes relevant.

### TorchComponent
Marks the entity as a torch, potentially affecting game mechanics related to light sources.

### DamageModelComponent
Defines how the chandelier takes damage and its health.

*   `hp`: `0.5` - The health points of the chandelier.
*   `blood_material`: `oil` - The material created when damaged (if applicable).
*   `falling_damages`: `0` - Does not take damage from falling.
*   `fire_probability_of_ignition`: `0` - Cannot ignite from fire.
*   `critical_damage_resistance`: `1` - High resistance to critical damage.
*   `ui_report_damage`: `0` - Does not report damage to the UI.