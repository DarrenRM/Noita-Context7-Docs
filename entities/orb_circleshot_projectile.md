---
title: Orb Circleshot Projectile
category: entities
---

# Orb Circleshot Projectile

This document describes the `orb_circleshot.xml` entity, which defines a projectile used by the boss centipede. It's a projectile that explodes on impact or when its lifetime ends, creating a visual effect and a small physics explosion.

## Key Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="0"`**: The projectile does not lose speed due to air resistance.

### Projectile Behavior (`ProjectileComponent`)

This is the core component defining the projectile's actions and properties.

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile. Values closer to 1 indicate a straighter trajectory.
*   **`speed_min="150"`, `speed_max="150"`**: Sets the projectile's constant speed.
*   **`die_on_low_velocity="0"`**: The projectile will not die if its velocity drops too low.
*   **`on_death_explode="1"`**: The projectile explodes when it dies (e.g., on collision or lifetime out).
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion from this projectile will not harm the entity that fired it.
*   **`damage="0"`**: The projectile itself deals no direct damage. Damage is handled by the explosion.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
*   **`collide_with_world="0"`**: The projectile does not collide with the game world geometry.
*   **`lifetime="250"`**: The projectile exists for 250 frames before expiring.

#### Damage by Type

*   **`holy="0.7"`**: The explosion deals 0.7 damage of the "holy" type.

#### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion that occurs when the projectile dies.

*   **`never_cache="1"`**: Ensures the explosion effect is always generated fresh.
*   **`camera_shake="0"`**: The explosion does not cause camera shake.
*   **`explosion_radius="9"`**: The radius of the explosion effect.
*   **`explosion_sprite="data/particles/explosion_016_plasma.xml"`**: Specifies the visual sprite for the explosion.
*   **`ray_energy="5000"`**: The energy of any rays emitted by the explosion.
*   **`hole_enabled="1"`**: The explosion creates a hole in the environment.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the explosion hole.
*   **`damage_mortals="0"`**: The explosion does not directly damage living entities.
*   **`physics_explosion_power.max="0.3"`**: The maximum force of the physics-based explosion.
*   **`shake_vegetation="1"`**: The explosion will shake vegetation.
*   **`light_r="10"`, `light_g="60"`, `light_b="10"`**: Defines the color of the light emitted by the explosion (a greenish-blue hue).

### Visuals (`SpriteComponent`)

This entity uses two `SpriteComponent`s to render its visual appearance, likely for a glowing effect.

*   **First Sprite:**
    *   **`image_file="data/projectiles_gfx/orb_pink_glowy.xml"`**: The primary sprite file.
    *   **`offset_x="8"`, `offset_y="8"`**: Offsets the sprite's position.
    *   **`rect_animation="spawn"`**: Uses a "spawn" animation.
*   **Second Sprite:**
    *   **`alpha="0.5"`**: This sprite is semi-transparent.
    *   **`image_file="data/projectiles_gfx/orb_pink_glowy.xml"`**: Uses the same sprite file.
    *   **`emissive="1"`, `additive="1"`**: These flags contribute to a glowing, additive blending effect.

### Particle Emitters (`ParticleEmitterComponent`, `SpriteParticleEmitterComponent`)

These components add visual flair and particle effects.

*   **`ParticleEmitterComponent`**:
    *   **`emitted_material_name="spark_purple_bright"`**: Emits bright purple sparks.
    *   **`lifetime_min="2"`, `lifetime_max="6"`**: Particles last between 2 and 6 frames.
    *   **`emission_interval_min_frames="4"`, `emission_interval_max_frames="12"`**: Sparks are emitted periodically.
*   **`SpriteParticleEmitterComponent`**:
    *   **`sprite_file="data/particles/spark_glitter.xml"`**: Emits glittery sparks.
    *   **`randomize_lifetime.min="0.5"`, `randomize_lifetime.max="2.0"`**: Glitter particles have a randomized lifespan.
    *   **`entity_velocity_multiplier="0.75"`**: Glitter particles inherit some of the projectile's velocity.
    *   **`randomize_velocity`**: Glitter particles have randomized velocity in X and Y directions.
    *   **`randomize_position`**: Glitter particles spawn with a slight random offset from the projectile's center.

### Variable Storage (`VariableStorageComponent`)

*   **`name="projectile_file"`**: Stores the path to this entity's XML file, useful for referencing it elsewhere.
*   **`value_string="data/entities/animals/boss_centipede/orb_circleshot.xml"`**: The actual path.