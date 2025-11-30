---
title: Big Acid Fungus Prop
category: entities
---

# Big Acid Fungus Prop

This document details the `physics_fungus_acid_big.xml` entity, a large, physics-enabled, acid-filled fungus prop.

## Core Components

### PhysicsBody2Component
Manages the physical properties of the fungus.

*   `is_static`: `0` (The fungus is not fixed in place and can move.)
*   `allow_sleep`: `1` (Allows the physics body to enter a sleep state when inactive to save performance.)
*   `angular_damping`: `0.01` (Resistance to rotational movement.)
*   `linear_damping`: `0.5` (Resistance to linear movement.)
*   `init_offset_y`: `52` (Initial vertical offset for the physics body.)

### MaterialInventoryComponent
Defines the materials contained within the fungus and how they behave.

*   `drop_as_item`: `0` (The fungus does not drop as an item when destroyed.)
*   `on_death_spill`: `1` (Spills its contents upon death.)
*   `leak_on_damage_percent`: `1` (Leaks material when damaged.)
*   `leak_pressure_min`: `0.5`
*   `leak_pressure_max`: `1.0`
*   `kill_when_empty`: `1` (The fungus is destroyed when its contents are depleted.)
*   `count_per_material_type`:
    *   `Material material="acid" count="1200"` (Contains 1200 units of acid.)

### DamageModelComponent
Handles damage and health for the fungus.

*   `hp`: `0.6` (Very low health, indicating it's easily destroyed.)
*   `air_needed`: `0` (Does not require air.)
*   `blood_material`: `slime_green` (The material that spills when damaged, not blood.)
*   `blood_spray_material`: `acid` (The material sprayed when damaged.)
*   `damage_multipliers`:
    *   `fire="40.0"` (Takes significantly more damage from fire.)

### ExplodeOnDamageComponent
Defines the explosion behavior when the fungus is damaged or destroyed.

*   `explode_on_death_percent`: `1` (Explodes when it dies.)
*   `explode_on_damage_percent`: `0.0` (Does not explode from partial damage.)
*   `physics_body_modified_death_probability`: `0.9` (High chance of explosion if its physics body is modified upon death.)
*   `physics_body_destruction_required`: `0.25` (Requires at least 25% of its physics body to be destroyed for explosion chance.)
*   `config_explosion`:
    *   `camera_shake`: `40`
    *   `explosion_radius`: `40`
    *   `explosion_sprite`: `data/particles/explosion_025_fuel.xml`
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_green.xml`
    *   `create_cell_material`: `fire`
    *   `physics_explosion_power.min`: `0.8`
    *   `physics_explosion_power.max`: `1.8`
    *   `spark_material`: `acid`
    *   `audio_event_name`: `explosions/slime`

### LuaComponent
Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/props/physics_fungus.lua` (The script controlling its behavior.)
*   `execute_every_n_frame`: `1` (The script runs every frame.)

## Visuals and Structure

### PhysicsImageShapeComponent
These components define the visual representation and physical shape of the fungus, composed of multiple parts.

*   **Cap:**
    *   `body_id="100"`
    *   `is_root="1"`
    *   `image_file="data/props_gfx/physics_fungus_acid_cap_03.png"`
    *   `material="fungus_loose_green"`
*   **Stalk Segments (body_id 101-106):**
    *   Multiple instances with varying `offset_y` to create a segmented stalk.
    *   `image_file="data/props_gfx/physics_fungus_acid_stalk.png"`
    *   `material="fungus_loose_green"`
*   **Foot:**
    *   `body_id="107"`
    *   `image_file="data/props_gfx/physics_fungus_acid_foot.png"`
    *   `material="fungus_loose_green"`

## Physics Joints

The fungus is constructed from multiple connected physics bodies using `PhysicsJoint2Component`.

### Stalk Joints (body_id 100-107)
These are `REVOLUTE_JOINT`s connecting the cap to the stalk segments and the stalk segments to each other, forming a flexible stalk.

*   `joint_id`: Sequentially numbered from 1 to 7.
*   `body1_id`, `body2_id`: Define which physics bodies are connected.
*   `break_force`: `10` (The force required to break the joint.)
*   `break_distance`: `5`

### Ground Joint
A special joint that attaches the fungus to the nearest surface.

*   `type`: `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`
*   `body1_id`: `107` (Connects the foot of the fungus to the ground.)
*   `break_force`: `35`
*   `break_distance`: `8`
*   `ray_x`, `ray_y`: Define the raycast for finding the surface.

## Other Components

### LightComponent
Provides a light source emanating from the fungus.

*   `radius`: `120`
*   `r`, `g`, `b`: `32`, `255`, `250` (A greenish-cyan light.)

### VariableStorageComponent
Stores a variable for potential use by scripts.

*   `name`: `lift`
*   `value_int`: `-35`

### AudioLoopComponent
Plays a looping sound effect.

*   `tags`: `sound_spray`
*   `file`: `data/audio/Desktop/materials.bank`
*   `event_name`: `materials/spray_fungus`