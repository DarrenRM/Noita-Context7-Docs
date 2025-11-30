---
title: Transmutation Field Projectile
category: entities
---

# Transmutation Field Projectile

This entity defines a player projectile that creates a transmutation field. It utilizes a Lua script for its core functionality and features particle emitters for visual effects.

## Key Components

### LuaComponent
This component links the projectile to its behavior script.

*   **`script_source_file`**: `data/scripts/projectiles/projectile_transmutation.lua` - The primary script governing the projectile's actions, including its transmutation effects.
*   **`execute_every_n_frame`**: `1` - The script logic runs every frame, allowing for real-time updates and effects.

### ParticleEmitterComponent (x2)
These components are responsible for generating visual particle effects around the projectile.

*   **`emitted_material_name`**: `spark_purple_bright` - The type of particle material to emit.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - The duration particles exist in seconds.
*   **`count_min` / `count_max`**: Varies between the two emitters (`2-4` and `4-4`) - Controls the number of particles spawned per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime ends.
*   **`area_circle_radius.max`**: `48` - The maximum radius of the emission area. The second emitter has a fixed radius of `48`.
*   **`cosmetic_force_create`**: `0` - Particles are not forced to be created.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: These attributes control how particles are affected by airflow, creating subtle movement.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame.
*   **`emit_cosmetic_particles`**: `1` - Cosmetic particles are emitted.
*   **`is_emitting`**: `1` - The particle emitter is active.

### Base Component
This entity inherits properties from `base_field.xml`, providing common attributes for field-like projectiles.

*   **`SpriteComponent`**:
    *   **`image_file`**: `data/particles/area_indicator_096_purple.png` - The visual sprite used for the field indicator.
    *   **`z_index`**: `1.2` - Controls the rendering layer of the sprite.
    *   **`offset_x` / `offset_y`**: `48` / `48` - Offsets the sprite's position.

*   **`ProjectileComponent`**:
    *   **`damage_game_effect_entities`**: `""` - This projectile does not directly apply damage game effects. Its primary function is transmutation.
    *   **`config_explosion`**:
        *   **`explosion_sprite`**: `data/particles/blast_out.xml` - Specifies the visual effect when the projectile's effect ends or is triggered.

*   **`AudioLoopComponent`**:
    *   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound event.
    *   **`event_name`**: `player_projectiles/field_transmutation/loop` - The specific audio event for the transmutation field's loop.
    *   **`auto_play`**: `1` - The sound starts playing automatically when the entity is active.