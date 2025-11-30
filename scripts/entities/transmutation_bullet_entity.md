---
title: Transmutation Bullet Entity
category: scripts/entities
---

# Transmutation Bullet Entity

This document describes the `transmutation_bullet.xml` entity, which defines a projectile with unique transmutation properties.

## Key Components and Attributes

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile behaviors.

*   **`VelocityComponent`**:
    *   `gravity_y`: `100` - Controls the downward acceleration of the projectile.
    *   `air_friction`: `-0.1` - Affects how air resistance slows the projectile.
    *   `mass`: `0.07` - The projectile's mass, influencing its interaction with physics.

### Homing (`<HomingComponent>`)

Enables the projectile to track its target.

*   `homing_targeting_coeff`: `130.0` - Strength of the homing behavior.
*   `homing_velocity_multiplier`: `0.86` - How much the homing affects the projectile's speed.

### Projectile (`<ProjectileComponent>`)

Defines the core characteristics and behaviors of the projectile.

*   **Movement & Trajectory**:
    *   `lob_min`, `lob_max`: `0.5`, `0.7` - Controls the arc of the projectile.
    *   `speed_min`, `speed_max`: `600`, `650` - The range of initial projectile speeds.
    *   `direction_random_rad`: `0.01` - Small random deviation in projectile direction.
    *   `lifetime`: `40` - Duration the projectile exists before expiring.
    *   `lifetime_randomness`: `7` - Variation in the projectile's lifetime.
*   **Impact & Destruction**:
    *   `on_death_explode`: `1` - The projectile explodes when its lifetime ends.
    *   `on_lifetime_out_explode`: `1` - Explicitly states explosion on lifetime expiry.
    *   `on_collision_die`: `1` - The projectile is destroyed upon collision.
    *   `explosion_dont_damage_shooter`: `1` - Prevents the explosion from harming the entity that fired it.
*   **Damage & Effects**:
    *   `damage`: `0` - This projectile itself deals no direct damage.
    *   `knockback_force`: `1.8` - The force applied to entities upon collision.
*   **Visuals & Audio**:
    *   `muzzle_flash_file`: `data/entities/particles/muzzle_flashes/muzzle_flash.xml` - Specifies the muzzle flash particle effect.
    *   `shoot_light_flash_r`, `g`, `b`, `radius`: `255`, `125`, `80`, `72` - Defines the color and radius of the light flash when fired.
*   **Explosion Configuration (`<config_explosion>`)**:
    *   `load_this_entity`: `data/scripts/streaming_integration/entities/transmutation_explosion.xml` - **Crucially**, this links to the entity responsible for the transmutation effect upon the projectile's death.
    *   `damage`: `0` - The explosion itself deals no damage.
    *   `camera_shake`: `0` - No camera shake is applied by the explosion.
    *   `explosion_radius`: `2` - The radius of the explosion's effect.
    *   `hole_enabled`: `1` - The explosion can create holes.
    *   `ray_energy`: `2000` - Energy value for raycasting effects.
    *   `max_durability_to_destroy`: `8` - How much durability the explosion can destroy.
    *   `physics_explosion_power.min`, `.max`: `0.02`, `0.1` - Controls the physics force of the explosion.

### Particle Emitter (`<ParticleEmitterComponent>`)

Generates visual particles.

*   `emitted_material_name`: `spark` - The type of material to emit.
*   `is_trail`: `1` - The particles form a trail behind the projectile.
*   `count_min`, `count_max`: `1`, `1` - Emits a single particle per emission.
*   `lifetime_min`, `lifetime_max`: `1.0`, `1.5` - Duration of each emitted particle.
*   `create_real_particles`: `0` - These are cosmetic particles, not physical entities.

### Audio (`<AudioComponent>`)

Handles sound effects.

*   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   `event_root`: `player_projectiles/bullet` - The specific sound event for this projectile.