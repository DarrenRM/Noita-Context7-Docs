---
title: Physics Trap - Ignite Enabled
category: data/entities
---

# Physics Trap - Ignite Enabled

This entity represents a physics-based trap that ignites when triggered by electricity. It's designed to be a hazard that can be activated remotely.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the trap.
- `allow_sleep`: `1` - Allows the object to enter a sleep state when inactive to save performance.
- `angular_damping`: `0` - No resistance to rotational movement.
- `linear_damping`: `0` - No resistance to linear movement.

### PhysicsImageShapeComponent
Defines the visual representation and collision shape.
- `image_file`: `data/props_gfx/trap_ignite_a.png` - The sprite used for the trap.
- `material`: `steel` - The material type, influencing interactions with other entities.

### ElectricityReceiverComponent
Enables the trap to react to electrical input.
- `radius`: `6` - The radius around the trap that can receive electrical signals.
- `active_time_frames`: `100` - The duration (in frames) the trap remains active after receiving a signal.

### LuaComponent
Attaches a Lua script to control the trap's behavior.
- `script_source_file`: `data/scripts/props/physics_trap_ignite.lua` - The script file that dictates the trap's logic.
- `execute_every_n_frame`: `160` - The script will execute its logic every 160 frames.

### ParticleEmitterComponent (x2)
Responsible for emitting particles when the trap is active.
- **First Emitter (`particles_a`)**:
    - `emitted_material_name`: `fire` - Emits fire particles.
    - `create_real_particles`: `1` - Creates actual game particles, not just cosmetic ones.
    - `lifetime_min`/`max`: `15`/`35` - Duration of emitted fire particles.
    - `count_min`/`max`: `100`/`100` - Number of fire particles emitted per burst.
    - `area_circle_radius.min`/`max`: `12`/`12` - The radius of the emission area.
    - `emission_interval_min_frames`/`max_frames`: `160`/`160` - How often particles are emitted.
- **Second Emitter (`particles_b`)**:
    - `emitted_material_name`: `alcohol_gas` - Emits alcohol gas particles.
    - `create_real_particles`: `1` - Creates actual game particles.
    - `lifetime_min`/`max`: `15`/`35` - Duration of emitted gas particles.
    - `count_min`/`max`: `500`/`500` - Number of gas particles emitted per burst.
    - `area_circle_radius.min`/`max`: `10`/`25` - The radius of the emission area.
    - `emission_interval_min_frames`/`max_frames`: `160`/`160` - How often particles are emitted.

### SpriteParticleEmitterComponent (`particles_c`)
Emits a specific sprite-based particle effect.
- `sprite_file`: `data/particles/explosion_032.xml` - The sprite to be used for this particle effect.
- `emission_interval_min_frames`/`max_frames`: `160`/`160` - Emission frequency.
- `count_min`/`max`: `1`/`1` - Emits a single particle per burst.

### DamageModelComponent
Defines how the trap takes damage and its properties.
- `hp`: `30` - The health points of the trap.
- `materials_that_damage`: `fire,lava,acid` - Materials that can damage the trap.
- `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage values for each material.
- `fire_damage_amount`: `0.4` - The amount of fire damage it deals if it ignites.
- `blood_material`: `alcohol_gas` - The material that is produced when damaged.
- `damage_multipliers`:
    - `melee`: `0.1` - Reduced damage from melee attacks.
    - `electricity`: `0` - Immune to electrical damage.

### ExplodeOnDamageComponent
Determines the trap's behavior when it takes damage or is destroyed.
- `explode_on_death_percent`: `1` - The trap will always explode upon death.
- `physics_body_destruction_required`: `0.15` - The trap needs to be at least 15% destroyed to trigger the explosion.
- `config_explosion`: Contains detailed settings for the explosion.
    - `damage`: `2.6` - The base damage of the explosion.
    - `camera_shake`: `10` - The intensity of camera shake during the explosion.
    - `explosion_radius`: `32` - The radius of the explosion's effect.
    - `load_this_entity`: `data/entities/projectiles/deck/mist_alcohol.xml` - An entity to spawn upon explosion (likely a projectile).
    - `damage_mortals`: `1` - The explosion damages living entities.
    - `physics_explosion_power.min`/`max`: `1.7`/`2.3` - The force of the physics-based explosion.
    - `delay.min`/`max`: `1`/`4` - A random delay before the explosion occurs.