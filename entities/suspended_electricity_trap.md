---
title: Suspended Electricity Trap
category: entities
---

# Suspended Electricity Trap

This entity represents a suspended trap that emits electricity when activated. It's designed to be a hazard that can be triggered by player interaction or environmental effects.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the trap.

*   `allow_sleep`: `1` - Allows the physics body to enter a sleep state when inactive.
*   `angular_damping`: `0` - No damping applied to rotational movement.
*   `linear_damping`: `0` - No damping applied to linear movement.

### PhysicsImageShapeComponent
Defines the visual representation and collision shape of the trap.

*   `is_root`: `1` - This is the primary visual component.
*   `body_id`: `100` - Identifier for the physics body.
*   `centered`: `1` - The image is centered on its origin.
*   `image_file`: `data/props_gfx/trap_electricity.png` - The sprite used for the trap.
*   `material`: `steel` - The material type, influencing interactions.

### ElectricityReceiverComponent
Enables the trap to receive and react to electrical energy.

*   `radius`: `6` - The radius around the trap that can receive electricity.
*   `active_time_frames`: `100` - The duration (in frames) the trap remains active after receiving electricity.

### LuaComponent (Electricity Effect)
Handles the script logic for the electrical pulse.

*   `_tags`: `electricity_effect` - Tags the component for specific game logic.
*   `script_source_file`: `data/scripts/props/physics_trap_electricity_pulse.lua` - The Lua script that controls the trap's behavior.
*   `execute_every_n_frame`: `128` - The script logic executes every 128 frames.

### SpriteParticleEmitterComponent (Particles A)
Responsible for emitting visual sparks when the trap is active.

*   `_tags`: `particles_a` - Tags for particle system management.
*   `_enabled`: `0` - Disabled by default, activated by script.
*   `sprite_file`: `data/particles/spark_electric.xml` - The particle sprite to use.
*   `emission_interval_min_frames`: `128`
*   `emission_interval_max_frames`: `128`
*   `count_min`: `3`
*   `count_max`: `10`
*   `randomize_rotation.min`: `-3.1415`
*   `randomize_rotation.max`: `3.1415`
*   `randomize_position.min_x`: `-14`
*   `randomize_position.max_x`: `14`
*   `randomize_position.min_y`: `-14`
*   `randomize_position.max_y`: `14`

### ParticleEmitterComponent (Particles B)
Another particle emitter, likely for a different visual effect or type of spark.

*   `_tags`: `particles_b`
*   `_enabled`: `0`
*   `emitted_material_name`: `spark_electric`
*   `x_vel_min`: `-50`
*   `x_vel_max`: `50`
*   `y_vel_min`: `-100`
*   `y_vel_max`: `50`
*   `count_min`: `20`
*   `count_max`: `60`
*   `lifetime_min`: `0.1`
*   `lifetime_max`: `0.75`
*   `emission_interval_min_frames`: `128`
*   `emission_interval_max_frames`: `128`
*   `is_emitting`: `1`

### DamageModelComponent
Defines how the trap takes damage and its own damage properties.

*   `hp`: `30` - Hit points of the trap.
*   `materials_damage`: `fire,lava,acid` - Materials that can damage the trap.
*   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage values for each material.
*   `falling_damage_damage_max`: `1.2`
*   `falling_damage_height_max`: `250`
*   `fire_damage_amount`: `0.4`
*   `damage_multipliers`:
    *   `melee`: `0.1` - Reduced damage from melee attacks.
    *   `electricity`: `0` - Immune to electrical damage.

### ExplodeOnDamageComponent
Determines what happens when the trap takes sufficient damage.

*   `explode_on_death_percent`: `1` - Explodes when health reaches 0%.
*   `physics_body_destruction_required`: `0.15` - Requires 15% of physics body destruction to trigger explosion.
*   `config_explosion`:
    *   `damage`: `2.6` - The damage dealt by the explosion.
    *   `camera_shake`: `10` - The intensity of camera shake.
    *   `explosion_radius`: `16` - The radius of the explosion.
    *   `load_this_entity`: `data/entities/projectiles/thunderball.xml` - Spawns a thunderball projectile upon explosion.
    *   `ray_energy`: `25000` - Energy of the electrical discharge.
    *   `physics_explosion_power.min`: `1.7`
    *   `physics_explosion_power.max`: `2.3`
    *   `audio_event_name`: `explosions/electric` - The sound effect for the explosion.

### LuaComponent (Chain Generation)
Handles the logic for creating chains to the ceiling.

*   `script_source_file`: `data/scripts/props/chain_to_ceiling.lua` - The script responsible for chain generation.
*   `execute_on_added`: `1` - Executes the script when the entity is added to the game.
*   `execute_every_n_frame`: `5` - Runs the script every 5 frames.
*   `execute_times`: `-1` - Executes indefinitely.

### VariableStorageComponent (Chain Variables)
Stores variables related to the chain generation.

*   `chain_0_x`: `0` - X-coordinate offset for the chain.
*   `chain_0_y`: `-6` - Y-coordinate offset for the chain.
*   `chain_strength_multiplier`: `5` - Multiplier for chain strength.