---
title: Thunderball Projectile
category: entities
---

---

# Thunderball Projectile

This document details the configuration of the "thunderball" projectile entity in Noita, focusing on its behavior, visual representation, and associated effects.

## Core Components

The `thunderball.xml` entity is built upon several core Noita components, defining its projectile nature, visual appearance, and interactive properties.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="-1"`: No air friction is applied, allowing for consistent velocity.
    *   `mass="0.9"`: Defines the projectile's mass.

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's behavior and interactions.

*   **Movement & Trajectory**:
    *   `lob_min="0.8"`, `lob_max="1.0"`: Controls the projectile's lobbing behavior, influencing its arc.
    *   `speed_min="100"`, `speed_max="120"`: Sets the range for the projectile's initial speed.
    *   `lifetime="100"`: The projectile exists for 100 frames before expiring.
*   **Death & Explosion**:
    *   `die_on_low_velocity="0"`: The projectile does not die when its velocity becomes low.
    *   `on_death_explode="1"`: The projectile explodes upon death.
    *   `on_lifetime_out_explode="1"`: The projectile explodes when its lifetime expires.
    *   `on_death_gfx_leave_sprite="0"`: The projectile's sprite is removed upon death.
    *   `explosion_dont_damage_shooter="0"`: The explosion can damage the entity that fired it.
*   **Damage & Effects**:
    *   `damage="0"`: Base damage of the projectile itself (before type-specific modifiers).
    *   `knockback_force="3.0"`: The force applied to knock back entities upon impact.
    *   `spawn_entity="data/entities/projectiles/thunderburst_thundermage.xml"`: An entity to spawn upon the projectile's death.
    *   `damage_by_type`:
        *   `electricity="1.5"`: Applies a 1.5x damage multiplier for electricity damage.
*   **Visuals & Lighting**:
    *   `shoot_light_flash_r="65"`, `shoot_light_flash_g="210"`, `shoot_light_flash_b="255"`, `shoot_light_flash_radius="160"`: Defines the color and radius of a light flash when the projectile is shot.
*   **Explosion Configuration (`config_explosion`)**:
    *   `never_cache="1"`: Ensures the explosion is not cached, allowing for dynamic effects.
    *   `camera_shake="30.5"`: The intensity of camera shake upon explosion.
    *   `explosion_radius="50"`: The radius of the explosion.
    *   `explosion_sprite="data/particles/explosion_032_electric.xml"`: The sprite used for the explosion effect.
    *   `load_this_entity`: A comma-separated list of entities to load upon explosion, including particle effects and loose ground.
    *   `explosion_sprite_lifetime="0.0"`: The explosion sprite has no independent lifetime.
    *   `create_cell_probability="4"`: Probability of creating a cell effect.
    *   `create_cell_material="plasma_fading"`: The material of the created cells.
    *   `explosion_sprite_emissive="1"`, `explosion_sprite_additive="1"`: Defines how the explosion sprite is rendered.
    *   `ray_energy="700000"`: The energy of any associated rays.
    *   `hole_destroy_liquid="1"`, `hole_enabled="1"`: Enables the creation of holes and destruction of liquids.
    *   `damage="1.8"`: Damage dealt by the explosion itself.
    *   `hole_image="data/temp/explosion_hole.png"`: The image used for the explosion hole.
    *   `particle_effect="0"`: No specific particle effect is directly tied to the explosion.
    *   `damage_mortals="1"`: The explosion damages mortal entities.
    *   `physics_explosion_power.min="1.5"`, `physics_explosion_power.max="2.6"`: The range of physics force applied by the explosion.
    *   `physics_throw_enabled="1"`: Entities affected by the explosion can be thrown.
    *   `shake_vegetation="1"`: The explosion shakes vegetation.
    *   `sparks_enabled="1"`, `sparks_count_min="30"`, `sparks_count_max="15"`: Enables and defines the count of sparks generated.
    *   `spark_material="spark_blue"`: The material of the sparks.
    *   `light_fade_time="1.2"`: The duration for the explosion's light to fade.
    *   `light_r="45"`, `light_g="120"`, `light_b="150"`: The color of the explosion's light.
    *   `stains_enabled="1"`, `stains_image="data/temp/explosion_stain.png"`: Enables and defines the image for explosion stains.
    *   `audio_event_name="explosions/electric"`: The audio event triggered by the explosion.

### Sprite Component (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   `image_file="data/projectiles_gfx/thunderball.xml"`: The file containing the projectile's sprite data.
*   `offset_x="8"`, `offset_y="8"`: Offsets for the sprite's position.
*   `rect_animation="fireball"`: Specifies the animation to use.
*   `emissive="1"`, `additive="1"`: Enables emissive and additive rendering for the sprite.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   `radius="150"`: The radius of the light.
*   `r="40"`, `g="140"`, `b="180"`: The color of the light.

### Sprite Particle Emitter (`SpriteParticleEmitterComponent`)

Generates particle effects around the projectile.

*   `sprite_file="data/particles/spark_electric.xml"`: The sprite file for the emitted particles.
*   `emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`: Controls the frequency of particle emission.
*   `count_min="1"`, `count_max="3"`: The number of particles emitted per interval.
*   `randomize_rotation.min="-3.1415"`, `randomize_rotation.max="3.1415"`: Randomizes particle rotation.
*   `randomize_position.min_x="-14"`, `randomize_position.max_x="14"`, `randomize_position.min_y="-14"`, `randomize_position.max_y="14"`: Randomizes particle spawn positions.

### Audio Components

*   **`AudioComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: The audio bank containing projectile sounds.
    *   `event_root="projectiles/electric"`: The root event for projectile sounds.
*   **`AudioLoopComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: The audio bank.
    *   `event_name="projectiles/electric/loop"`: The name of the looping audio event.
    *   `auto_play="1"`: The audio loop starts automatically.

### Variable Storage (`VariableStorageComponent`)

*   `name="projectile_file"`: Stores the path to this projectile's XML file.
*   `value_string="data/entities/projectiles/thunderball.xml"`: The actual value stored.