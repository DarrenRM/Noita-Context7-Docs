---
title: Projectile - Heal/Hurt
category: entities
---

# Projectile - Heal/Hurt

This document details the configuration for a projectile entity in Noita, specifically designed to inflict damage or heal based on context.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="200"`: Applies a moderate downward gravitational pull.
    *   `air_friction="1.2"`: Medium air resistance.
    *   `mass="0.07"`: Low mass, contributing to its speed and responsiveness.

### Projectile (`<ProjectileComponent>`)

This is the primary component defining the projectile's behavior.

*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the arc of the projectile.
*   **`speed_min="600"`, `speed_max="650"`**: Defines the initial velocity range.
*   **`friction="1"`**: Standard friction.
*   **`direction_random_rad="0.01"`**: Slight randomness in projectile direction.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion will not harm the entity that fired it.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`lifetime="40"`**: The projectile exists for 40 frames before expiring.
*   **`damage="1.20"`**: The base damage dealt by the projectile.
*   **`lifetime_randomness="7"`**: Adds variability to the projectile's lifetime.
*   **`knockback_force="1.8"`**: The force applied to knock back targets.
*   **`physics_impulse_coeff="1500"`**: Coefficient for physics impulse calculations.

#### `config_explosion` (Nested within `ProjectileComponent`)

Defines the properties of the explosion triggered by the projectile.

*   **`damage="0"`**: The explosion itself does not deal direct damage (damage is handled by the projectile's `damage` attribute).
*   **`camera_shake="0.5"`**: Moderate camera shake upon explosion.
*   **`explosion_radius="2"`**: The radius of the explosion effect.
*   **`explosion_sprite="data/particles/explosion_016_plasma.xml"`**: The visual sprite for the explosion.
*   **`hole_enabled="1"`**: Creates holes in terrain.
*   **`ray_energy="400000"`**: High energy for potential terrain destruction.
*   **`physics_explosion_power.min="0.02"`, `physics_explosion_power.max="0.1"`**: Controls the physics force of the explosion.
*   **`shake_vegetation="1"`**: Causes vegetation to shake.
*   **`light_enabled="1"`**: Enables a light source upon explosion.
    *   `light_r="40"`, `light_g="10"`, `light_b="90"`: Sets the color of the explosion light (a purplish hue).
*   **`stains_enabled="1"`**: Creates stains on surfaces.

### Sprite (`<SpriteComponent>`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/light_arrow.xml"`**: Specifies the sprite image.
*   **`additive="1"`**: Uses additive blending for a brighter, more luminous effect.

### Particle Emitter (`<ParticleEmitterComponent>`)

Generates cosmetic particles.

*   **`emitted_material_name="spark_blue"`**: The type of particle emitted.
*   **`is_trail="1"`**: The particles form a trail behind the projectile.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime decreases.

### Audio (`<AudioComponent>`)

Handles sound effects for the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
*   **`event_root="player_projectiles/bullet"`**: The specific sound event to play.

### Light (`<LightComponent>`)

Adds a persistent light source to the projectile.

*   **`radius="40"`**: The radius of the light.
*   **`r="10"`, `g="40"`, `b="120"`**: Sets the light color (a bluish hue).

### Variable Storage (`<VariableStorageComponent>`)

Stores custom variables for the entity.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/deck/healhurt.xml"`**: The value, pointing to the projectile's own file.

### Hit Effect (`<HitEffectComponent>`)

Determines the effect that occurs when the projectile hits something.

*   **`effect_hit="LOAD_CHILD_ENTITY_LIMIT_TO_X"`**: Specifies the type of hit effect.
*   **`value="6"`**: A numerical value associated with the effect.
*   **`value_string="data/entities/misc/effect_healhurt.xml"`**: The path to the entity that defines the hit effect. This is crucial for the "heal/hurt" functionality, as this external entity likely contains the logic to determine whether to heal or damage.