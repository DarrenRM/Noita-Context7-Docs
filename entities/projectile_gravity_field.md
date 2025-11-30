---
title: Projectile Gravity Field
category: entities
---

# Projectile Gravity Field

This entity defines a projectile that creates a gravity field. It utilizes Lua scripting for its behavior and Particle Emitters to visualize the field and its effects.

## Core Components

### LuaComponent

*   **script_source_file**: `data/scripts/projectiles/projectile_gravity.lua`
    *   This specifies the Lua script responsible for the projectile's logic and gravity field mechanics.
*   **execute_every_n_frame**: `1`
    *   Indicates the script logic runs every frame, allowing for dynamic and responsive behavior.

### ParticleEmitterComponent (Primary)

This component is responsible for emitting visual particles that represent the gravity field.

*   **emitted_material_name**: `spark_purple_bright`
    *   The material used for the emitted particles.
*   **gravity.y**: `0.0`
    *   Particles are not affected by gravity in the Y-axis, keeping them within the field.
*   **lifetime_min/max**: `0.5` / `1.5`
    *   The duration each particle exists.
*   **count_min/max**: `2` / `4`
    *   The number of particles emitted per emission cycle.
*   **render_on_grid**: `1`
    *   Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1`
    *   Particles fade out as their lifetime decreases.
*   **area_circle_radius.max**: `96`
    *   Defines the maximum radius of the particle emission area.
*   **airflow_force/time/scale**: `0.5` / `0.01` / `0.05`
    *   These attributes control how airflow affects the emitted particles, creating a swirling or dynamic effect.
*   **emission_interval_min/max_frames**: `1` / `1`
    *   Particles are emitted every frame.
*   **emit_cosmetic_particles**: `1`
    *   Emits particles that are purely visual.
*   **is_emitting**: `1`
    *   The particle emitter is active.
*   **draw_as_long**: `1`
    *   Particles are drawn for their full duration.
*   **attractor_force**: `16`
    *   This is a key attribute, indicating the strength of the gravity field's pull on entities.

### ParticleEmitterComponent (Secondary)

This component adds a denser ring of particles around the edge of the field.

*   **emitted_material_name**: `spark_purple_bright`
*   **gravity.y**: `0.0`
*   **lifetime_min/max**: `0.5` / `1.5`
*   **count_min/max**: `10` / `20`
    *   Emits a larger number of particles compared to the primary emitter.
*   **render_on_grid**: `1`
*   **fade_based_on_lifetime**: `1`
*   **area_circle_radius.min/max**: `96` / `96`
    *   Particles are emitted specifically at a radius of 96.
*   **airflow_force/time/scale**: `0.3` / `0.01` / `0.05`
    *   Slightly less airflow force than the primary emitter.
*   **emission_interval_min/max_frames**: `1` / `1`
*   **emit_cosmetic_particles**: `1`
*   **is_emitting**: `1`

### Base Entity Inclusion

*   **Base file**: `data/entities/projectiles/deck/base_field.xml`
    *   Inherits common properties and components from a base field projectile.

#### SpriteComponent (from Base)

*   **image_file**: `data/particles/area_indicator_096_purple_dark.png`
    *   The visual sprite used to represent the area of effect.
*   **z_index**: `1.2`
    *   Determines the rendering order of the sprite.
*   **offset_x/y**: `48` / `48`
    *   Offsets the sprite's position.

#### ProjectileComponent (from Base)

*   **damage_game_effect_entities**: `""`
    *   This field is empty, suggesting the gravity field itself does not directly deal damage but might apply effects through its Lua script.
*   **config_explosion**:
    *   **explosion_sprite**: `data/particles/blast_out.xml`
        *   Defines the visual effect when the projectile is destroyed or its effect ends.

#### AudioLoopComponent (from Base)

*   **file**: `data/audio/Desktop/projectiles.bank`
*   **event_name**: `player_projectiles/field_gravity/loop`
    *   The sound event played continuously while the gravity field is active.
*   **auto_play**: `1`

### AudioLoopComponent (Top Level)

*   **file**: `data/audio/Desktop/projectiles.bank`
*   **event_name**: `player_projectiles/field_gravity/vortex_loop`
    *   A secondary sound event, likely for a more intense or specific part of the gravity field's effect.
*   **auto_play**: `1`

## Key Attributes for Modding

*   **`attractor_force`** in `ParticleEmitterComponent`: Directly controls the strength of the gravity pull.
*   **`area_circle_radius.max`** and **`area_circle_radius.min`** in `ParticleEmitterComponent`: Defines the size of the gravity field.
*   **`script_source_file`** in `LuaComponent`: The primary point of modification for custom gravity field behaviors.
*   **`emitted_material_name`** and particle emitter properties: Allows for customization of the visual appearance of the field.
*   **`event_name`** in `AudioLoopComponent`: For changing or adding sound effects.