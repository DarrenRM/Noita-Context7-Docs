---
title: Orb Green Accelerating Projectile
category: entities
---

# Orb Green Accelerating Projectile

This document details the configuration for the "Orb Green Accelerating" projectile entity in Noita, designed for AI-assisted modding.

## Core Components

### Base Projectile Configuration

This section inherits fundamental projectile properties from a base entity.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="-2"`: High air friction, suggesting it maintains velocity well.
    *   `terminal_velocity="250"`: Maximum speed the projectile can reach due to air friction.
    *   `mass="0.05"`: Low mass, indicating it's lightweight.

### Projectile Behavior (`ProjectileComponent`)

This component defines the projectile's unique characteristics and interactions.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile. Values close to 1 suggest a relatively straight trajectory.
*   **`speed_min="350"`, `speed_max="350"`**: The projectile travels at a constant speed of 350.
*   **`die_on_low_velocity="0"`**: The projectile does not disappear if its speed drops too low.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not harm the entity that fired it.
*   **`damage="0.8"`**: The projectile deals 0.8 damage.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`dont_collide_with_tag="monk_hand"`**: The projectile will not collide with entities tagged as "monk\_hand".
*   **`lifetime="150"`**: The projectile exists for 150 frames before expiring.
*   **`knockback_force="1.0"`**: Applies a knockback force of 1.0 upon impact.
*   **`velocity_sets_scale="1"`, `velocity_sets_scale_coeff="3"`**: Indicates that the projectile's velocity influences its scale, with a coefficient of 3.

#### `config_explosion`

Defines the properties of the explosion that occurs when the projectile dies.

*   **`never_cache="1"`**: The explosion effect will not be cached, ensuring it's always generated fresh.
*   **`camera_shake="0"`**: No camera shake is applied by the explosion.
*   **`explosion_radius="10"`**: The explosion affects an area with a radius of 10 units.
*   **`explosion_sprite="data/particles/explosion_016_plasma_green.xml"`**: Specifies the visual sprite for the explosion.
*   **`ray_energy="5000"`**: The explosion has a ray energy of 5000.
*   **`hole_destroy_liquid="1"`**: The explosion can destroy liquids.
*   **`hole_enabled="1"`**: The explosion creates a hole in surfaces.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the explosion hole.
*   **`physics_explosion_power.min="0.24"`, `physics_explosion_power.max="0.34"`**: The minimum and maximum power of the physics-based explosion.
*   **`physics_throw_enabled="1"`**: The explosion can throw nearby physics objects.
*   **`shake_vegetation="1"`**: The explosion shakes vegetation.
*   **`light_fade_time="0.8"`**: The light emitted by the explosion fades over 0.8 seconds.
*   **`light_r="10"`, `light_g="60"`, `light_b="10"`**: The RGB values for the light emitted by the explosion (a greenish hue).

### Visuals (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/orb_green.xml"`**: The primary sprite for the projectile.
*   **`emissive="1"`, `additive="1"`**: The sprite is emissive and uses additive blending for a glowing effect.
*   A second `SpriteComponent` uses `data/particles/explosion_016_plasma_green.xml` for its visual, suggesting it might contribute to the projectile's appearance even before exploding.

### Particle Emitters

#### Trail Emitter

*   **`emitted_material_name="spark_green"`**: Emits particles of type "spark\_green".
*   **`lifetime_min="0.3"`, `lifetime_max="2.9"`**: Particles have a lifetime between 0.3 and 2.9 seconds.
*   **`emission_interval_min_frames="2"`, `emission_interval_max_frames="5"`**: Particles are emitted every 2 to 5 frames.
*   **`is_emitting="1"`**: The trail emitter is active.

#### Burst Emitter

*   **`emitted_material_name="spark_green"`**: Emits particles of type "spark\_green".
*   **`count_min="30"`, `count_max="60"`**: Emits 30 to 60 particles per burst.
*   **`velocity_always_away_from_center="80"`**: Particles are always propelled away from the center at 80 units/second.
*   **`lifetime_min="0.9"`, `lifetime_max="3.2"`**: Particles have a lifetime between 0.9 and 3.2 seconds.
*   **`emitter_lifetime_frames="2"`**: The burst emitter is active for 2 frames.
*   **`is_emitting="1"`**: The burst emitter is active.

### Lighting (`LightComponent`)

*   **`radius="150"`**: The light source has a radius of 150 units.
*   **`r="30"`, `g="90"`, `b="30"`**: The light color is a dark green.

### Audio (`AudioComponent`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank.
*   **`event_root="projectiles/orb_a"`**: The root event for projectile sounds.

### Variable Storage (`VariableStorageComponent`)

*   **`name="projectile_file"`**: Stores the path to this projectile's XML file.
*   **`value_string="data/entities/projectiles/orb_green_accelerating.xml"`**: The actual file path.