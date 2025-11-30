---
title: Trap Laser Enabled
category: entities
---

# Trap Laser Enabled

This entity represents a laser trap that can be activated by electricity. When activated, it emits a laser beam and particles. It also has physics properties and can be damaged, eventually exploding.

## Key Components

### PhysicsBody2Component
Handles the physical behavior of the trap.

*   `allow_sleep`: `1` - Allows the physics body to go to sleep when inactive.
*   `angular_damping`: `0` - No angular damping.
*   `linear_damping`: `0` - No linear damping.

### PhysicsImageShapeComponent
Defines the visual shape and material of the trap.

*   `is_root`: `1` - This is the root component for the physics shape.
*   `centered`: `1` - The image is centered.
*   `image_file`: `data/props_gfx/trap_laser.png` - The sprite used for the trap.
*   `material`: `steel` - The material of the trap, affecting its physics and damage interactions.

### ElectricityReceiverComponent
Enables the trap to react to electrical input.

*   `radius`: `6` - The radius around the trap that can receive electrical signals.
*   `active_time_frames`: `15` - How many frames the trap remains active after receiving a signal.

### Entity (name="laser")
This nested entity defines the laser emitter itself.

*   `LaserEmitterComponent`:
    *   `is_emitting`: `1` - The laser is set to emit by default when this entity is active.
*   `InheritTransformComponent`:
    *   `Transform`:
        *   `position.x`: `7` - Offsets the laser emitter's position relative to the trap's origin.

### SpriteParticleEmitterComponent
Responsible for emitting cosmetic electric sparks when the trap is active.

*   `_tags`: `particles_a` - Tag for particle system management.
*   `_enabled`: `0` - Disabled by default, activated when the trap receives electricity.
*   `sprite_file`: `data/particles/spark_electric.xml` - The particle sprite to use.
*   `color.r`, `color.g`, `color.b`, `color.a`: Defines the color of the emitted particles (greenish-yellow).
*   `gravity.y`: `10` - Particles are affected by gravity.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `128` - Controls the timing of particle emissions.
*   `count_min`, `count_max`: `3`, `10` - The number of particles emitted per burst.
*   `randomize_rotation`: Controls random rotation of particles.
*   `randomize_position`: Controls random positioning of particles within a radius.

### ParticleEmitterComponent
Emits green sparks when the trap is active.

*   `_tags`: `particles_b` - Tag for particle system management.
*   `_enabled`: `0` - Disabled by default, activated when the trap receives electricity.
*   `emitted_material_name`: `spark_green` - The material of the emitted particles.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines the velocity range of emitted particles.
*   `count_min`, `count_max`: `20`, `60` - The number of particles emitted per burst.
*   `lifetime_min`, `lifetime_max`: `0.1`, `0.75` - The duration particles exist.
*   `emit_cosmetic_particles`: `1` - These are cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `128` - Controls the timing of particle emissions.
*   `is_emitting`: `1` - The emitter is active when enabled.
*   `draw_as_long`: `1` - Particles are drawn as long streaks.

### DamageModelComponent
Defines how the trap takes damage and its health.

*   `hp`: `30` - The trap's health points.
*   `materials_that_damage`: `fire,lava,acid` - Materials that can damage the trap.
*   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage taken from specific materials.
*   `falling_damage_damage_max`, `falling_damage_damage_min`: Defines damage from falling.
*   `fire_damage_amount`: `0.4` - Damage taken from fire.
*   `damage_multipliers`:
    *   `melee`: `0.1` - Takes reduced melee damage.
    *   `electricity`: `0` - Immune to electricity damage.

### ExplodeOnDamageComponent
Defines the explosion behavior when the trap is destroyed or heavily damaged.

*   `explode_on_death_percent`: `1` - Always explodes on death.
*   `explode_on_damage_percent`: `0.0` - Does not explode from partial damage.
*   `physics_body_destruction_required`: `0.15` - The physics body needs to be at least 15% destroyed to trigger an explosion on death.
*   `config_explosion`:
    *   `damage`: `2.6` - The damage dealt by the explosion.
    *   `camera_shake`: `10` - The intensity of camera shake.
    *   `explosion_radius`: `16` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_016_electric.xml` - The visual effect of the explosion.
    *   `load_this_entity`: `data/entities/projectiles/thunderball.xml` - Spawns a thunderball projectile upon explosion.
    *   `ray_energy`: `25000` - The energy of the explosion's rays.
    *   `physics_explosion_power`: Defines the force of the physics explosion.
    *   `audio_event_name`: `explosions/electric` - The sound effect played during the explosion.