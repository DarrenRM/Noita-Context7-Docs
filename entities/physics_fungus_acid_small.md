---
title: Physics Fungus (Acid Small)
category: entities
---

# Physics Fungus (Acid Small)

This entity represents a small, physics-enabled fungus that leaks acid when damaged. It's designed to be a destructible prop with a distinct visual and physical presence.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the fungus.

*   `is_static`: `0` (The fungus is not fixed in place and can move.)
*   `allow_sleep`: `1` (Allows the physics body to go to sleep when inactive, saving performance.)
*   `angular_damping`: `0.01` (Reduces rotational velocity over time.)
*   `linear_damping`: `0.3` (Reduces linear velocity over time.)
*   `init_offset_y`: `28` (Initial vertical offset for the physics body.)

### PhysicsImageShapeComponent
Defines the visual representation and collision shape of the fungus. Multiple components are used to construct the fungus from different image parts (cap, stalk, foot).

*   `body_id`: Unique identifier for each physics body part.
*   `is_root`: `1` (Marks the primary body part.)
*   `centered`: `1` (Centers the image on its pivot point.)
*   `offset_x`, `offset_y`: Position of the image relative to the body's origin.
*   `image_file`: Path to the sprite image.
*   `material`: `fungus_loose_green` (The material used for collision and visual properties.)

### PhysicsJoint2Component
Connects different parts of the fungus together, creating a flexible structure.

*   `type`: `REVOLUTE_JOINT` (Allows rotation between connected bodies.)
*   `joint_id`: Identifies the joint.
*   `offset_x`, `offset_y`: Position of the joint.
*   `body1_id`, `body2_id`: The IDs of the bodies being connected.
*   `break_force`: The force required to break the joint.
*   `break_distance`: The distance at which the joint breaks.

A special `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` is used to anchor the fungus to the ground.

### MaterialInventoryComponent
Manages the materials contained within the fungus.

*   `drop_as_item`: `0` (Does not drop as an item when destroyed.)
*   `on_death_spill`: `1` (Spills its contents upon death.)
*   `leak_on_damage_percent`: `1` (Leaks when damaged.)
*   `leak_pressure_min`, `leak_pressure_max`: Controls the pressure of the leaked material.
*   `kill_when_empty`: `1` (The entity is destroyed when its material is depleted.)
*   `count_per_material_type`:
    *   `Material material="acid" count="500"`: Contains 500 units of acid.

### DamageModelComponent
Defines how the fungus takes damage and its reaction to it.

*   `hp`: `0.6` (Hit points of the fungus.)
*   `air_needed`: `0` (Does not require air.)
*   `ragdoll_material`: `fungus_loose_green` (Material for ragdoll effects.)
*   `blood_material`: `slime_green` (Material for blood splatters.)
*   `blood_sprite_directional`, `blood_sprite_large`: Paths to blood splatter particle effects.
*   `minimum_knockback_force`: `100000` (High knockback resistance.)
*   `damage_multipliers`:
    *   `fire="40.0"`: Takes significantly more damage from fire.

### ExplodeOnDamageComponent
Handles the explosion behavior of the fungus.

*   `explode_on_death_percent`: `1` (Explodes when health reaches 0%.)
*   `physics_body_modified_death_probability`: `0.9` (High chance of exploding when physics body is modified upon death.)
*   `physics_body_destruction_required`: `0.25` (Explosion is triggered if 25% of the physics body is destroyed.)
*   `config_explosion`: Contains detailed parameters for the explosion, including:
    *   `camera_shake`: `40`
    *   `explosion_radius`: `20`
    *   `explosion_sprite`: `data/particles/explosion_025_fuel.xml`
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_green.xml`
    *   `create_cell_material`: `fire`
    *   `physics_explosion_power`: `min="0.8", max="1.8"`
    *   `spark_material`: `acid`
    *   `audio_event_name`: `explosions/slime`

### LightComponent
Adds a light source to the entity.

*   `radius`: `50`
*   `r`, `g`, `b`: Color values (greenish-white).

### LuaComponent
Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/props/physics_fungus.lua`
*   `execute_every_n_frame`: `1` (Script executes every frame.)

### AudioLoopComponent
Plays a looping sound effect.

*   `event_name`: `materials/spray_fungus` (Likely related to the acid spray sound.)