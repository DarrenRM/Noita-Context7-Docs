---
title: Trap Laser Enabled Left
category: entities
---

# Trap Laser Enabled Left

This entity represents a laser trap that is activated by electricity. When powered, it emits a laser beam.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the trap.
- `allow_sleep`: Whether the body can go to sleep when idle.
- `angular_damping`: Resistance to angular motion.
- `linear_damping`: Resistance to linear motion.

### PhysicsImageShapeComponent
Defines the visual shape and physical material of the trap.
- `is_root`: Indicates if this is the root shape component.
- `centered`: Whether the shape is centered on its origin.
- `image_file`: Path to the sprite image for the trap.
- `material`: The physical material of the trap (e.g., "steel").

### ElectricityReceiverComponent
Handles the trap's response to electrical input.
- `radius`: The radius around the trap that can receive electricity.
- `active_time_frames`: The number of frames the trap remains active after receiving a signal.

### Entity (name="laser")
This nested entity defines the laser beam itself.
- **LaserEmitterComponent**:
    - `laser_angle_add_rad`: Adds an angle to the laser's emission direction.
    - `is_emitting`: Whether the laser is currently active.
- **InheritTransformComponent**:
    - **Transform**:
        - `position.x`: Offsets the laser's position relative to the trap.

### SpriteParticleEmitterComponent
Responsible for emitting cosmetic particles when the trap is active.
- `_tags`: Tags associated with these particles.
- `_enabled`: Whether particle emission is currently active.
- `sprite_file`: Path to the particle sprite.
- `delay`: Initial delay before emitting particles.
- `lifetime`: Duration of each particle.
- `color`: Initial color of the particles.
- `velocity`: Initial velocity of the particles.
- `gravity`: Gravity applied to the particles.
- `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions.
- `count_min`, `count_max`: The number of particles emitted per burst.
- `randomize_rotation`: Randomizes the rotation of emitted particles.
- `randomize_position`: Randomizes the position of emitted particles within a range.

### ParticleEmitterComponent
Another component for emitting particles, likely for more distinct effects.
- `_tags`: Tags associated with these particles.
- `_enabled`: Whether particle emission is currently active.
- `emitted_material_name`: The material name of the particles to emit.
- `offset`: Offset from the emitter's origin.
- `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Range for position randomization.
- `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Range for velocity.
- `count_min`, `count_max`: Number of particles emitted.
- `lifetime_min`, `lifetime_max`: Duration of particles.
- `create_real_particles`: Whether to create actual physics particles.
- `emit_cosmetic_particles`: Whether to emit cosmetic particles.
- `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions.
- `is_emitting`: Whether the emitter is active.
- `draw_as_long`: Whether particles are drawn as long streaks.

### DamageModelComponent
Defines how the trap takes damage and its properties.
- `hp`: Hit points of the trap.
- `materials_that_damage`: List of materials that can damage the trap.
- `materials_how_much_damage`: How much damage each material inflicts.
- `damage_multipliers`: Modifiers for different damage types (e.g., melee, electricity).

### ExplodeOnDamageComponent
Determines what happens when the trap takes damage or is destroyed.
- `explode_on_death_percent`: Probability of exploding upon death.
- `explode_on_damage_percent`: Probability of exploding when taking damage.
- `physics_body_destruction_required`: The percentage of physics body destruction needed to trigger an explosion.
- `config_explosion`: Configuration for the explosion effect.
    - `damage`: Damage dealt by the explosion.
    - `camera_shake`: Amount of camera shake.
    - `explosion_radius`: Radius of the explosion.
    - `explosion_sprite`: Path to the explosion sprite.
    - `load_this_entity`: An entity to load upon explosion (e.g., a projectile).
    - `ray_energy`: Energy of any rays emitted by the explosion.
    - `physics_explosion_power`: Strength of the physics-based explosion force.
    - `audio_event_name`: The sound event to play for the explosion.