---
title: Physics Tube Lamp Entity
category: entities
---

# Physics Tube Lamp Entity

This document describes the `physics_tubelamp.xml` entity, which represents a breakable tube lamp in Noita. It utilizes physics components to simulate its behavior and includes visual and functional elements for its operation and destruction.

## Key Components and Attributes

### PhysicsBody2Component
This component defines the physical properties of the tube lamp.

*   `is_static`: `0` - The lamp is not fixed and can be moved by physics.
*   `allow_sleep`: `1` - The body can enter a sleep state when not in motion to save performance.
*   `angular_damping`: `0.01` - Reduces rotational velocity over time.
*   `linear_damping`: `0.3` - Reduces linear velocity over time.
*   `init_offset_y`: `-3` - The initial vertical offset of the physics body.

### PhysicsImageShapeComponent
These components define the visual shapes and collision areas of the lamp.

*   **Main Body:**
    *   `image_file`: `data/props_gfx/tubelamp.png` - The primary sprite for the lamp.
    *   `material`: `glass_box2d` - The material used for collision and interaction.
*   **Wires (two instances):**
    *   `image_file`: `data/props_breakable_gfx/wire_vertical_5_00.png` - The sprite for the wires.
    *   `material`: `metal_wire_nohit` - A material that is not directly hit by projectiles.
    *   `offset_x`, `offset_y`: Define the position of the wires relative to the main body.

### PhysicsJoint2Component
These components define the connections between different parts of the lamp and its attachment to the environment.

*   **Body to Wire Joints (two instances):**
    *   `type`: `REVOLUTE_JOINT` - Creates a revolute joint allowing rotation.
    *   `body1_id`, `body2_id`: Connects the main body (`100`) to the wire shapes (`101`, `102`).
    *   `break_force`: `10` - The force required to break this joint.
    *   `break_distance`: `2` - The distance at which the joint breaks.
*   **Wire to Ceiling Joints (two instances):**
    *   `type`: `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` - Attaches the wire to the nearest surface above it.
    *   `body1_id`: The wire shape (`101`, `102`).
    *   `break_force`: `8` - The force required to break this joint.
    *   `break_distance`: `2` - The distance at which the joint breaks.
    *   `ray_y`: `-16` - The direction and length of the raycast to find the attachment surface.

### LightComponent
These components add light effects to the lamp.

*   `radius`: `150` - The range of the light.
*   `blinking_freq`: `1` - The frequency of the blinking effect.
*   `r`, `g`, `b`: `200`, `230`, `255` - The color of the light (a bluish-white).
*   `offset_x`: Positions the light source relative to the lamp.

### MaterialInventoryComponent
Manages the materials contained within the lamp, particularly for its destruction effects.

*   `on_death_spill`: `1` - Spills its contents when destroyed.
*   `leak_on_damage_percent`: `1` - Leaks when damaged.
*   `leak_pressure_min`, `leak_pressure_max`: Control the pressure of the leaked material.
*   `kill_when_empty`: `1` - The entity is destroyed when its material is depleted.
*   `count_per_material_type`:
    *   `Material material="spark_electric" count="100"` - Contains 100 units of `spark_electric` material.

### DamageModelComponent
Defines how the lamp takes damage and its health.

*   `hp`: `0.7` - The health points of the lamp.
*   `falling_damage_damage_max`, `falling_damage_damage_min`: Define damage from falling.
*   `fire_damage_amount`: `0.2` - The amount of damage taken from fire.

### ExplodeOnDamageComponent
Handles the explosion effect when the lamp is destroyed or sufficiently damaged.

*   `explode_on_death_percent`: `1` - Explodes when health reaches 0.
*   `physics_body_destruction_required`: `0.6` - The physics body needs to be at least 60% destroyed for the explosion to trigger.
*   `config_explosion`: Contains detailed settings for the explosion:
    *   `damage`: `1` - The base damage of the explosion.
    *   `camera_shake`: `5` - The intensity of camera shake.
    *   `explosion_radius`: `10` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_016_electric.xml` - The visual effect of the explosion.
    *   `create_cell_material`: `spark_electric` - The material created by the explosion.
    *   `physics_explosion_power`: Controls the force of the physics-based explosion.

### LuaComponent
These components enable scripting for dynamic behavior.

*   **`script_physics_body_modified`:**
    *   `script_physics_body_modified="data/scripts/props/physics_tube_lamp.lua"` - This script likely handles the initial setup and damage-related logic for the lamp.
*   **`electricity_effect` (two instances):**
    *   `_enabled="0"` - These components are initially disabled and are likely activated by the main Lua script.
    *   `script_source_file="data/scripts/props/physics_tube_lamp_electricity_pulse.lua"` - This script handles the electrical pulsing effect.
    *   `execute_every_n_frame="60"` - The script executes every 60 frames.

### SpriteParticleEmitterComponent
Emits particles for visual effects, specifically related to electricity.

*   `_tags="electricity_effect"` - Tagged to be enabled/disabled with the electricity effect.
*   `_enabled="0"` - Initially disabled.
*   `sprite_file`: `data/particles/spark_electric.xml` - The particle sprite.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `60` - Emits particles every 60 frames.
*   `count_min`, `count_max`: `3`, `10` - The number of particles emitted per interval.
*   `randomize_rotation`, `randomize_position`: Controls the spread and orientation of particles.

### ParticleEmitterComponent
Emits materials as particles, also related to the electrical effect.

*   `_tags="electricity_effect"` - Tagged to be enabled/disabled with the electricity effect.
*   `_enabled="0"` - Initially disabled.
*   `emitted_material_name`: `spark_electric` - The material to emit.
*   `x_vel_min`, `y_vel_max`: Define the velocity range of emitted particles.
*   `count_min`, `count_max`: `20`, `60` - The number of particles emitted per interval.
*   `lifetime_min`, `lifetime_max`: `0.1`, `0.75` - The duration particles exist.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `60` - Emits particles every 60 frames.