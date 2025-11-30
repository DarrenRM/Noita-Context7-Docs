---
title: Dark Orb Projectile
category: entities
---

# Dark Orb Projectile

This document details the configuration of the "orb_dark" projectile entity in Noita, focusing on its behavior, visual representation, and effects.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="-0.1"`: Minimal air resistance.
    *   `mass="0.055"`: Defines the projectile's mass.

### Projectile Behavior (`<ProjectileComponent>`)

This is the primary component defining the projectile's actions and interactions.

*   **`_enabled="1"`**: Enables the component.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior, influencing its trajectory arc.
*   **`speed_min="100"`, `speed_max="120"`**: Sets the initial speed range of the projectile.
*   **`die_on_low_velocity="0"`**: The projectile does not die if its velocity drops too low.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not damage the entity that fired it.
*   **`damage="0.3"`**: Base damage dealt by the projectile.
*   **`damage_game_effect_entities="data/entities/misc/effect_blindness.xml,"`**: Applies a blindness effect upon hitting a target.
*   **`on_collision_die="1"`**: The projectile dies upon collision with an entity.
*   **`lifetime="150"`**: The projectile's lifespan in frames.
*   **`knockback_force="2.0"`**: The force applied to knock back entities upon impact.

#### Explosion Configuration (`<config_explosion>`)

Defines the properties of the explosion that occurs upon the projectile's death.

*   **`never_cache="1"`**: Prevents caching of the explosion effect.
*   **`camera_shake="0.5"`**: Amount of camera shake caused by the explosion.
*   **`explosion_radius="1"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_016_plasma_pink.xml"`**: The visual sprite used for the explosion.
*   **`create_cell_probability="1"`**: Guarantees the creation of cells upon explosion.
*   **`create_cell_material="plasma_fading"`**: The material of the cells created.
*   **`ray_energy="10000"`**: Energy value for any associated ray effects.
*   **`hole_destroy_liquid="1"`**: The explosion can destroy liquids.
*   **`hole_enabled="1"`**: Enables the creation of holes by the explosion.
*   **`damage="0.1"`**: Damage dealt by the explosion itself.
*   **`sparks_enabled="1"`**: Enables sparks to be emitted from the explosion.
*   **`spark_material="plasma_fading_pink"`**: The material of the sparks.
*   **`sparks_count_min="12"`, `sparks_count_max="16"`**: The range for the number of sparks emitted.
*   **`light_r="155"`, `light_g="15"`, `light_b="140"`**: RGB values for the explosion's light emission.

### Homing Behavior (`<HomingComponent>`)

Enables the projectile to track and home in on targets.

*   **`target_tag="prey"`**: The projectile targets entities with the "prey" tag.
*   **`homing_targeting_coeff="7"`**: The strength of the homing targeting.
*   **`detect_distance="350"`**: The maximum distance at which the projectile can detect targets.
*   **`homing_velocity_multiplier="1.0"`**: Multiplier for the velocity when homing.

### Visuals (`<SpriteComponent>`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/orb_dark.xml"`**: The sprite sheet or animation file for the projectile.
*   **`rect_animation="fireball"`**: Specifies the animation to use.
*   **`emissive="1"`, `additive="1"`**: Enables emissive and additive rendering for a glowing effect.
*   **`offset_x="5"`, `offset_y="5"`**: Adjusts the sprite's position.

### Lighting (`<LightComponent>`)

Adds a light source to the projectile.

*   **`radius="150"`**: The radius of the light emitted.
*   **`r="250"`, `g="35"`, `b="220"`**: RGB values for the light color (a purplish hue).

### Particle Emitter (`<SpriteParticleEmitterComponent>`)

Generates particles around the projectile.

*   **`sprite_file="data/particles/spark_electric.xml"`**: The sprite used for the emitted particles.
*   **`color.r="1"`, `color.g="0"`, `color.b="1"`, `color.a="1"`**: Initial color of the particles (purple).
*   **`gravity.y="10"`**: Particles are affected by gravity.
*   **`emission_interval_min_frames="3"`, `emission_interval_max_frames="4"`**: Controls the frequency of particle emission.
*   **`count_min="1"`, `count_max="2"`**: The number of particles emitted per interval.
*   **`randomize_rotation.min="-3.1415"`, `randomize_rotation.max="3.1415"`**: Randomizes particle rotation.
*   **`randomize_position.min_x="-8"`, `randomize_position.max_x="8"`**, etc.: Randomizes particle spawn position around the projectile.

### Audio (`<AudioComponent>`, `<AudioLoopComponent>`)

Manages the sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sounds.
*   **`event_root="projectiles/orb_dark"`**: The root event for the projectile's sounds.
*   **`event_name="projectiles/magic_orb/loop"`**: The name of the looping sound event.
*   **`auto_play="1"`**: The loop sound plays automatically.

### Variable Storage (`<VariableStorageComponent>`)

Stores variables for potential use by other game systems.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/orb_dark.xml"`**: The value, pointing to the projectile's own XML file.