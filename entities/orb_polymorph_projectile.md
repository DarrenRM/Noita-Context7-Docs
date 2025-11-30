---
title: Orb Polymorph Projectile
category: entities
---

---

# Orb Polymorph Projectile

This document describes the `orb_polymorph.xml` entity, which defines a projectile used by the boss centipede in Noita. This projectile exhibits homing behavior and applies a random polymorph effect upon collision or when its lifetime expires.

## Key Components and Attributes

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component defines the fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.8"`: A relatively low mass.

### Homing Behavior (`HomingComponent`)

This component enables the projectile to track its target.

*   `target_tag="prey"`: The projectile targets entities tagged as "prey".
*   `homing_targeting_coeff="2"`: Controls the strength of the homing behavior.
*   `detect_distance="350"`: The maximum distance at which the projectile can detect its target.
*   `homing_velocity_multiplier="0.99"`: Slightly reduces the projectile's speed when homing.

### Projectile Logic (`ProjectileComponent`)

This is the core component defining the projectile's behavior, effects, and interactions.

*   **Movement & Trajectory**:
    *   `lob_min="0.8"`, `lob_max="1.0"`: Defines the minimum and maximum lobbing behavior.
    *   `speed_min="100"`, `speed_max="120"`: The projectile's speed range.
    *   `die_on_low_velocity="0"`: The projectile does not die if its velocity becomes too low.
    *   `on_death_explode="1"`: The projectile explodes when it dies.
    *   `on_lifetime_out_explode="1"`: The projectile explodes when its lifetime ends.
    *   `explosion_dont_damage_shooter="1"`: The explosion does not harm the entity that fired it.
    *   `on_collision_die="1"`: The projectile dies upon colliding with something.
*   **Damage & Effects**:
    *   `damage="0.3"`: The base damage dealt by the projectile.
    *   `damage_game_effect_entities="data/entities/misc/effect_polymorph_random.xml,"`: Upon death (from collision or lifetime), this entity spawns a random polymorph effect.
*   **Bouncing**:
    *   `bounces_left="10"`: The projectile can bounce up to 10 times.
    *   `bounce_always="1"`: The projectile will always attempt to bounce.
    *   `bounce_at_any_angle="1"`: Bouncing occurs regardless of the collision angle.
    *   `bounce_energy="0.85"`: The projectile retains 85% of its energy after each bounce.
*   **Lifetime**:
    *   `lifetime="400"`: The projectile exists for 400 frames.
*   **Explosion Configuration (`config_explosion`)**:
    *   `never_cache="1"`: The explosion effect is not cached.
    *   `camera_shake="0.5"`: Causes moderate camera shake upon explosion.
    *   `explosion_radius="1"`: The radius of the explosion.
    *   `explosion_sprite="data/particles/explosion_016_plasma_pink.xml"`: The visual effect of the explosion.
    *   `create_cell_probability="1"`: Always creates a cell upon explosion.
    *   `create_cell_material="plasma_fading"`: The material of the created cell.
    *   `ray_energy="10000"`: High energy for raycasting effects.
    *   `hole_destroy_liquid="1"`: The explosion can destroy liquids.
    *   `hole_enabled="1"`: Creates a hole in surfaces.
    *   `damage = "0.1"`: Minor damage from the explosion itself.
    *   `sparks_enabled="1"`: Sparks are generated.
    *   `spark_material="plasma_fading_pink"`: The material of the sparks.
    *   `light_r="225"`, `light_g="25"`, `light_b="180"`: Emits a pinkish light.

### Visuals (`SpriteComponent`)

Defines the projectile's appearance.

*   `image_file="data/projectiles_gfx/orb_pink.xml"`: The primary sprite for the projectile.
*   `rect_animation="fireball"`: Uses a "fireball" animation.
*   `emissive="1"`, `additive="1"`: The sprite is emissive and uses additive blending for a glowing effect.
*   `offset_x="5"`, `offset_y="5"`: Offsets the sprite's position.

### Lighting (`LightComponent`)

Adds a light source to the projectile.

*   `radius="150"`: The radius of the light.
*   `r="220"`, `g="18"`, `b="180"`: The color of the light (pinkish).

### Particle Emitters (`SpriteParticleEmitterComponent`)

Generates additional visual effects.

*   `sprite_file="data/particles/shine_03.xml"`: Uses a "shine" particle.
*   `lifetime="4"`: Particles last for 4 frames.
*   `gravity.y="30"`: Particles are affected by a slight downward gravity.
*   `randomize_rotation.min="-3.1415"`, `randomize_rotation.max="3.1415"`: Particles have random initial rotations.
*   `randomize_angular_velocity.min="-15"`, `randomize_angular_velocity.max="15"`: Particles have random angular velocities.
*   `randomize_velocity.min_x="-5"`, `randomize_velocity.max_x="5"`: Particles have random horizontal velocities.
*   `randomize_velocity.min_y="-5"`, `randomize_velocity.max_y="5"`: Particles have random vertical velocities.

### Audio (`AudioComponent`, `AudioLoopComponent`)

Handles sound effects for the projectile.

*   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
*   `event_root="projectiles/orb_poly"`: The root event for projectile sounds.
*   `event_name="projectiles/magic_orb/loop"`: The name of the looping sound event.
*   `auto_play="1"`: The loop sound starts automatically.

### Muzzle Flash (`SpriteComponent`)

A visual effect for when the projectile is fired.

*   `image_file="data/particles/explosion_032_pink.xml"`: Uses a pink explosion particle for the muzzle flash.
*   `rect_animation="explosion"`: Uses an "explosion" animation.
*   `emissive="1"`, `additive="1"`: Emissive and additive blending.
*   `offset_x="16"`, `offset_y="16"`: Offsets the muzzle flash position.

### Variable Storage (`VariableStorageComponent`)

Stores a variable related to the projectile.

*   `name="projectile_file"`: The name of the variable.
*   `value_string="data/entities/animals/boss_centipede/orb_polymorph.xml"`: The value, pointing to the projectile's own file path.