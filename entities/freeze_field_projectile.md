---
title: Freeze Field Projectile
category: entities
---

# Freeze Field Projectile

This document details the `freeze_field.xml` entity, which defines a projectile that creates a freezing area and converts various liquids into ice.

## Core Components

### GameAreaEffectComponent
This component defines the area of effect for the projectile.

*   **radius**: `28` - The radius of the area affected by the projectile.
*   **frame_length**: `70` - The duration of the effect in frames.

### ParticleEmitterComponent (x2)
These components are responsible for emitting cosmetic particles around the projectile.

*   **emitted_material_name**: `spark_white` - The material used for the emitted particles.
*   **gravity.y**: `0.0` - No vertical gravity applied to these particles.
*   **lifetime_min/max**: `0.5` / `1.5` - The minimum and maximum lifetime of the particles.
*   **count_min/max**: Varies between `2-4` and `4-4` - The number of particles emitted.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime ends.
*   **area_circle_radius.max**: `28` - Maximum radius for particle emission.
*   **cosmetic_force_create**: `0` - Not forced cosmetic particles.
*   **airflow_force/time/scale**: Controls airflow effects on particles.
*   **emission_interval_min/max_frames**: `1` / `1` - Particles are emitted every frame.
*   **emit_cosmetic_particles**: `1` - Emits cosmetic particles.
*   **is_emitting**: `1` - The emitter is active.

### Base File Inclusion
The projectile inherits properties from `data/entities/projectiles/deck/base_field.xml`.

#### SpriteComponent
Defines the visual appearance of the projectile.

*   **image_file**: `data/projectiles_gfx/blast_frozen.xml` - The sprite file used for the projectile's visual.

#### SpriteParticleEmitterComponent
Emits snowflake particles.

*   **sprite_file**: `data/particles/snowflake_$[1-2].xml` - Uses snowflake particle sprites.
*   **lifetime**: `10` - The lifetime of the snowflake particles.
*   **color**: `1, 1, 1, 1` - White color.
*   **color_change**: `0, 0, 0, -0.5` - Alpha decreases over time.
*   **gravity.y**: `10` - Downward gravity for snowflakes.
*   **velocity_slowdown**: `0.5` - Particles slow down over time.
*   **count_min/max**: `1` / `2` - Number of snowflakes emitted.
*   **randomize_rotation.min/max**: `-3.1415` / `3.1415` - Random rotation applied.

#### ProjectileComponent
Defines projectile behavior and effects.

*   **damage_game_effect_entities**: `data/entities/misc/effect_frozen.xml,` - Applies a "frozen" effect.
*   **friendly_fire**: `0` - Does not affect friendly entities.
*   **config_explosion**:
    *   **explosion_sprite**: `data/particles/blast_out_frozen.xml` - Sprite used for the explosion effect.

### MagicConvertMaterialComponent (x2)
These components handle the conversion of materials within the projectile's area.

#### First MagicConvertMaterialComponent
Converts various liquids to different types of ice.

*   **from_material_array**: `water,water_ice,water_salt,water_fading,water_static,fire,lava,water_swamp,radioactive_liquid,acid,blood_cold,blood,poison,slime` - The list of materials to be converted.
*   **to_material_array**: `ice_static,ice_static,ice_static,ice_static,ice_static,air,rock_static,ice_static,ice_radioactive_static,ice_acid_static,ice_cold_static,ice_blood_static,ice_poison_static,ice_slime_static` - The materials they are converted into.
*   **kill_when_finished**: `0` - The component does not disappear after completion.
*   **steps_per_frame**: `5` - Number of conversion steps per frame.
*   **is_circle**: `1` - The conversion area is circular.
*   **radius**: `72` - The radius of the material conversion.

#### Second MagicConvertMaterialComponent
Extinguishes fire.

*   **kill_when_finished**: `0` - The component does not disappear after completion.
*   **extinguish_fire**: `1` - Extinguishes fire.
*   **is_circle**: `1` - The effect area is circular.
*   **radius**: `72` - The radius of the effect.