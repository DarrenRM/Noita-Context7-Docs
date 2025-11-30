---
title: Invisible Shot Projectile
category: entities
---

# Invisible Shot Projectile

This document details the configuration of the `invisshot.xml` entity, representing an invisible projectile in Noita.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`gravity_y="0"`**: The projectile is unaffected by gravity.
*   **`air_friction="-2.0"`**: A slight air friction is applied.
*   **`mass="0.04"`**: Defines the projectile's mass.

### Homing Component (`HomingComponent`)

This projectile has homing capabilities.

*   **`target_tag="homing_target"`**: Specifies the tag for entities that can be targeted.
*   **`homing_targeting_coeff="30.0"`**: Controls the strength of the homing behavior.
*   **`homing_velocity_multiplier="1.99"`**: Adjusts the projectile's velocity when homing.
*   **`detect_distance="300"`**: The range within which the projectile can detect targets.

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's behavior and effects.

*   **`_enabled="1"`**: Enables the component.
*   **`lob_min="0.8"`, `lob_max="1.1"`**: Defines the minimum and maximum lobbing behavior.
*   **`speed_min="200"`, `speed_max="250"`**: Sets the projectile's speed range.
*   **`friendly_fire="1"`**: Allows the projectile to damage the shooter.
*   **`direction_random_rad="0.1"`**: Introduces a small amount of randomness to the projectile's initial direction.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not damage the shooter.
*   **`on_collision_die="1"`**: The projectile dies upon collision.
*   **`lifetime="50"`**: The projectile's lifespan in frames.
*   **`velocity_sets_scale="1"`**: Velocity influences the projectile's scale.
*   **`damage_game_effect_entities="data/entities/misc/effect_invisibility_short.xml,"`**: Upon dealing damage, applies a short invisibility effect.
*   **`damage="0"`**: The projectile itself deals no direct damage.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_large.xml"`**: Specifies the muzzle flash particle effect.

#### Explosion Configuration (`config_explosion`)

*   **`damage="0"`**: The explosion deals no damage.
*   **`explosion_radius="1"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_016_plasma.xml"`**: The visual sprite for the explosion.
*   **`ray_energy="10000"`**: High energy for potential environmental interactions.
*   **`physics_throw_enabled="1"`**: The explosion can throw objects.
*   **`shake_vegetation="1"`**: The explosion shakes vegetation.

### Sprite Component (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/grenade_blue.xml"`**: The sprite image used.
*   **`emissive="1"`, `additive="1"`**: The sprite is emissive and uses additive blending.

### Particle Emitter Component (`ParticleEmitterComponent`)

Generates cosmetic particles, likely for a trail effect.

*   **`emitted_material_name="spark_blue"`**: The material of the emitted particles.
*   **`is_trail="1"`**: Indicates this is a trail emitter.
*   **`emit_cosmetic_particles="1"`**: Only cosmetic particles are emitted.

### Audio Component (`AudioComponent`)

Handles the sound effects for the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank file.
*   **`event_root="projectiles/bullet_invis"`**: The root event for projectile sounds.

### Variable Storage Component (`VariableStorageComponent`)

Stores a variable related to the projectile's file path.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/invisshot.xml"`**: The value of the variable, pointing to its own file.