---
title: Trap Ignite Prop
category: entities
---

# Trap Ignite Prop

This entity represents a physics-based trap that ignites when activated by electricity. It's designed to release fire and alcohol gas, causing damage and explosions.

## Key Components

### PhysicsBody2Component
Handles the physical properties of the trap.

*   `allow_sleep`: `1` - Allows the physics body to go to sleep when inactive.
*   `angular_damping`: `0` - No angular damping.
*   `linear_damping`: `0` - No linear damping.

### PhysicsImageShapeComponent
Defines the visual representation and collision shape.

*   `is_root`: `1` - This is the root visual component.
*   `centered`: `1` - The image is centered.
*   `image_file`: `data/props_gfx/trap_ignite_a.png` - The sprite for the trap.
*   `material`: `steel` - The material type for physics interactions.

### ElectricityReceiverComponent
Enables the entity to react to electrical input.

*   `radius`: `6` - The radius within which electricity can activate this component.
*   `active_time_frames`: `100` - How long the trap remains active after receiving a signal.

### LuaComponent (Scripted Electricity Receiver)
Links the electrical activation to a specific script.

*   `script_electricity_receiver_switched`: `data/scripts/props/physics_trap.lua` - The script that handles the logic when the receiver is switched on.

### VariableStorageComponent (Enable Components)
These components define which other components should be enabled when the trap is activated.

*   `enable_component` (value: `electricity_effect`)
*   `enable_component` (value: `particles_a`)
*   `enable_component` (value: `particles_b`)
*   `enable_component` (value: `particles_c`)

### LuaComponent (Ignition Script)
This component executes a specific script for the ignition effect.

*   `_tags`: `electricity_effect` - This component is enabled by the `electricity_effect` tag.
*   `_enabled`: `0` - Disabled by default, enabled by `enable_component`.
*   `script_source_file`: `data/scripts/props/physics_trap_ignite.lua` - The script responsible for the ignition logic.
*   `execute_every_n_frame`: `160` - The script runs every 160 frames.

### ParticleEmitterComponent (Fire Particles)
Emits fire particles.

*   `_tags`: `particles_a` - Enabled by the `particles_a` tag.
*   `_enabled`: `0` - Disabled by default.
*   `emitted_material_name`: `fire` - The material to emit.
*   `create_real_particles`: `1` - Creates actual physics particles.
*   `lifetime_min`/`max`: `15`/`35` - Duration of emitted particles.
*   `count_min`/`max`: `100`/`100` - Number of particles emitted per burst.
*   `area_circle_radius.min`/`max`: `12`/`12` - The radius of the emission area.
*   `emission_interval_min_frames`/`max_frames`: `160`/`160` - Interval between particle emissions.
*   `set_magic_creation`: `1` - Particles are created with magic properties.

### ParticleEmitterComponent (Alcohol Gas Particles)
Emits alcohol gas particles.

*   `_tags`: `particles_b` - Enabled by the `particles_b` tag.
*   `_enabled`: `0` - Disabled by default.
*   `emitted_material_name`: `alcohol_gas` - The material to emit.
*   `create_real_particles`: `1` - Creates actual physics particles.
*   `lifetime_min`/`max`: `15`/`35` - Duration of emitted particles.
*   `count_min`/`max`: `500`/`500` - Number of particles emitted per burst.
*   `area_circle_radius.min`/`max`: `10`/`25` - The radius of the emission area.
*   `emission_interval_min_frames`/`max_frames`: `160`/`160` - Interval between particle emissions.
*   `set_magic_creation`: `1` - Particles are created with magic properties.

### SpriteParticleEmitterComponent (Explosion Sprite)
Emits a sprite-based particle effect, likely for the initial ignition flash.

*   `_tags`: `particles_c` - Enabled by the `particles_c` tag.
*   `_enabled`: `0` - Disabled by default.
*   `sprite_file`: `data/particles/explosion_032.xml` - The sprite to use.
*   `emission_interval_min_frames`/`max_frames`: `160`/`160` - Interval between emissions.
*   `count_min`/`max`: `1`/`1` - Emits a single sprite.

### DamageModelComponent
Defines how the entity takes damage and its properties.

*   `hp`: `30` - Hit points of the trap.
*   `materials_that_damage`: `fire,lava,acid` - Materials that can damage this entity.
*   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage values for the respective materials.
*   `fire_damage_amount`: `0.4` - Amount of fire damage it deals if it ignites.
*   `blood_material`: `alcohol_gas` - The material that is released when damaged (used for some effects).
*   `damage_multipliers`:
    *   `melee`: `0.1` - Reduced damage from melee attacks.
    *   `electricity`: `0` - Immune to electricity damage.

### ExplodeOnDamageComponent
Defines the explosion behavior when the entity takes damage or dies.

*   `explode_on_death_percent`: `1` - Always explodes upon death.
*   `physics_body_destruction_required`: `0.15` - The physics body needs to be at least 15% destroyed to trigger an explosion.
*   `config_explosion`:
    *   `damage`: `2.6` - Base damage of the explosion.
    *   `camera_shake`: `10` - Intensity of camera shake.
    *   `explosion_radius`: `32` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - The sprite for the explosion effect.
    *   `hole_enabled`: `1` - Creates a hole in the terrain.
    *   `load_this_entity`: `data/entities/projectiles/deck/mist_alcohol.xml` - An entity to spawn upon explosion (likely related to alcohol mist).
    *   `ray_energy`: `75000` - Energy of the explosion's damaging rays.
    *   `physics_explosion_power.min`/`max`: `1.7`/`2.3` - The force of the physics explosion.
    *   `audio_event_name`: `explosions/machine_small` - The sound effect played on explosion.