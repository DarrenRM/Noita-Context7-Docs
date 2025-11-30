---
title: Neutralizer Shot Projectile
category: entities
---

# Neutralizer Shot Projectile

This document details the configuration of the `neutralizershot.xml` entity, which defines a special projectile in Noita. This projectile is designed to track targets and apply a unique "neutralizer" effect upon impact.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="-2"`: A slight negative air friction, suggesting it might slightly accelerate or maintain velocity in air.
    *   `mass="0.05"`: A very low mass, contributing to its speed and responsiveness.

### Projectile Behavior (`<ProjectileComponent>`)

This is the primary component defining the projectile's in-game mechanics.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile. Values close to 1 suggest a relatively straight trajectory.
*   **`speed_min="350"`, `speed_max="350"`**: The projectile travels at a constant speed of 350 units.
*   **`damage="0"`**: This projectile does not inflict direct damage.
*   **`on_collision_die="1"`**: The projectile is destroyed upon colliding with anything.
*   **`lifetime="100"`**: The projectile will disappear after 100 frames if it doesn't collide.
*   **`knockback_force="1.0"`**: Applies a small knockback effect on collision.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher_blue.xml"`**: Specifies the visual effect at the point of origin.
*   **`shoot_light_flash_r="50"`, `shoot_light_flash_g="125"`, `shoot_light_flash_b="235"`, `shoot_light_flash_radius="100"`**: Defines a blue light flash effect when the projectile is fired.
*   **`config_explosion`**:
    *   `damage="0"`: No damage from any potential explosion.
    *   `audio_enabled="0"`: No sound associated with the explosion.

### Target Tracking (`<HomingComponent>`)

This component enables the projectile to seek out targets.

*   **`homing_targeting_coeff="20.0"`**: A high coefficient indicates strong homing capabilities.
*   **`homing_velocity_multiplier="0.99"`**: The projectile's velocity is slightly reduced as it homes in.
*   **`detect_distance="60"`**: The projectile can detect targets within a 60-unit radius.

## Visuals and Effects

### Sprite (`<SpriteComponent>`)

Defines the projectile's visual appearance.

*   **`image_file="data/projectiles_gfx/target2.xml"`**: Uses a specific sprite definition for its appearance.
*   **`rect_animation="fireball"`**: Suggests an animation named "fireball" is applied.
*   **`additive="1"`, `emissive="1"`**: These flags indicate the sprite uses additive blending and is emissive, likely making it glow.

### Particles (`<ParticleEmitterComponent>`)

Two particle emitters are used to create visual effects.

1.  **Purple Sparks**:
    *   `emitted_material_name="spark_purple_bright"`: Emits bright purple sparks.
    *   `is_trail="1"`: Creates a trail effect.
    *   `lifetime_min="0.1"`, `lifetime_max="0.2"`: Short lifespan for the sparks.
    *   `create_real_particles="0"`, `emit_cosmetic_particles="1"`: These are cosmetic particles, not affecting gameplay physics.

2.  **Pink Plasma**:
    *   `emitted_material_name="plasma_fading_pink"`: Emits fading pink plasma particles.
    *   `is_trail="1"`: Creates a trail effect.
    *   `lifetime_min="0.2"`, `lifetime_max="0.6"`: Longer lifespan for these particles.
    *   `x_vel_min="20"`, `x_vel_max="80"`: Particles are emitted with significant horizontal velocity.

### Light (`<LightComponent>`)

Adds a light source to the projectile.

*   **`radius="150"`**: The light extends to a radius of 150 units.
*   **`r="30"`, `g="90"`, `b="30"`**: The light color is a greenish-blue.

## Special Functionality

### Hit Effect (`<HitEffectComponent>`)

This component defines what happens when the projectile successfully hits a target.

*   **`effect_hit="LOAD_CHILD_ENTITY"`**: Triggers the loading of another entity upon impact.
*   **`value_string="data/entities/misc/neutralizer_target.xml"`**: The entity loaded upon impact is `neutralizer_target.xml`, which presumably contains the logic for the "neutralizer" effect.

### Variable Storage (`<VariableStorageComponent>`)

Stores a reference to the projectile's own file.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/neutralizershot.xml"`**: The value is the path to this entity's XML file. This is often used for self-referential logic or debugging.

## Audio (`<AudioComponent>`)

Defines the sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sounds.
*   **`event_root="projectiles/laser"`**: Indicates the root event for projectile sounds, suggesting a laser-like audio profile.