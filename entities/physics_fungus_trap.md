---
title: Physics Fungus Trap
category: entities
---

# Physics Fungus Trap

This document describes the `physics_fungus_trap_02.xml` entity, a physics-based prop in Noita that functions as a trap. It's designed to react to damage and environmental interactions, potentially releasing harmful materials.

## Key Components and Attributes

This entity is composed of several components that define its behavior, appearance, and physical properties.

### PhysicsBody2Component

Defines the physical body of the trap.

*   `is_static`: `0` - The body is not static and can be moved.
*   `allow_sleep`: `1` - The body can enter a sleep state when not in motion to save performance.
*   `linear_damping`: `0.5` - Reduces linear velocity over time.
*   `init_offset_y`: `15` - Initial vertical offset.

### PhysicsImageShapeComponent

These components define the visual representation and collision shapes of the trap, composed of a cap, stalk, and foot.

*   **Cap (body_id="100")**:
    *   `image_file`: `data/props_gfx/physics_fungus_trap_cap_02.png`
    *   `material`: `fungus_loose`
    *   `centered`: `1`
    *   `offset_y`: `2`
*   **Stalk (body_id="101")**:
    *   `image_file`: `data/props_gfx/physics_fungus_trap_stalk.png`
    *   `material`: `fungus_loose`
    *   `offset_x`: `-3`
    *   `offset_y`: `3`
*   **Foot (body_id="102")**:
    *   `image_file`: `data/props_gfx/physics_fungus_trap_foot.png`
    *   `material`: `fungus_loose`
    *   `offset_x`: `-3`
    *   `offset_y`: `6`

### PhysicsJoint2Component

These define the connections between the different parts of the trap and its connection to the environment.

*   **Stalk Joints**:
    *   Connects the cap to the stalk (`body1_id="100"`, `body2_id="101"`).
    *   Type: `REVOLUTE_JOINT`
    *   `break_force`: `10`
    *   `break_distance`: `5`
    *   Connects the stalk to the foot (`body1_id="101"`, `body2_id="102"`).
    *   Type: `REVOLUTE_JOINT`
    *   `break_force`: `10`
    *   `break_distance`: `5`
*   **Ground Joint**:
    *   Attaches the foot to the nearby surface.
    *   Type: `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`
    *   `body1_id`: `102`
    *   `break_force`: `35`
    *   `break_distance`: `8`
    *   `ray_y`: `30` (raycast distance for surface detection)

### MaterialInventoryComponent

Manages the materials contained within the trap.

*   `on_death_spill`: `1` - Spills its contents upon death.
*   `leak_on_damage_percent`: `1` - Leaks when damaged.
*   `kill_when_empty`: `1` - The entity is destroyed when its material is depleted.
*   **Contents**:
    *   `fungus_powder_bad`: `500` units.

### DamageModelComponent

Defines how the trap takes damage and its resulting effects.

*   `hp`: `0.4` - Very low health, easily destroyed.
*   `fire_probability_of_ignition`: `100` - Highly susceptible to fire.
*   `ragdoll_material`: `fungus_loose_trippy` - Material used for ragdoll effects.
*   `blood_material`: `slime_yellow`
*   `blood_spray_material`: `fungus_powder_bad`
*   `minimum_knockback_force`: `100000` - High knockback resistance.
*   **Damage Multipliers**:
    *   `fire`: `40.0` - Takes significantly more damage from fire.

### ExplodeOnDamageComponent

Determines if and how the trap explodes when damaged.

*   `explode_on_death_percent`: `1` - Explodes when it dies.
*   `physics_body_modified_death_probability`: `0.9` - High chance of physics body modification on death.
*   `physics_body_destruction_required`: `0.25` - Requires 25% of its physics body to be destroyed to trigger explosion.
*   **Explosion Configuration**:
    *   `camera_shake`: `10`
    *   `explosion_radius`: `20`
    *   `explosion_sprite`: `data/particles/explosion_025_fuel.xml`
    *   `create_cell_material`: `fire`
    *   `hole_enabled`: `1`
    *   `particle_effect`: `1`
    *   `physics_explosion_power.min`: `0.8`
    *   `physics_explosion_power.max`: `1.8`
    *   `sparks_enabled`: `1`
    *   `spark_material`: `fungus_powder_bad`
    *   `audio_event_name`: `explosions/slime`

### LightComponent

Adds a light source to the entity.

*   `radius`: `80`
*   `r`: `32`
*   `g`: `255`
*   `b`: `250`

### LuaComponent

Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/props/physics_fungus.lua`
*   `execute_every_n_frame`: `1` - Executes the script every frame.

### AudioLoopComponent

Plays a looping sound effect.

*   `event_name`: `materials/spray_fungus`
*   `file`: `data/audio/Desktop/materials.bank`