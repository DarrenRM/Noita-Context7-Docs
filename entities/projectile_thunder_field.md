---
title: Projectile Thunder Field
category: entities
---

# Projectile Thunder Field

This entity defines a player-controlled projectile that creates an electrical field. It utilizes a Lua script for its core logic and several ParticleEmitterComponents to generate visual effects.

## Key Components

### LuaComponent
This component links the projectile to its behavior script.

*   **`script_source_file`**: `data/scripts/projectiles/projectile_thunder.lua` - The primary script governing the projectile's actions.
*   **`execute_every_n_frame`**: `1` - The script logic executes every frame.

### ParticleEmitterComponent (Primary)
This component generates blue sparks around the projectile.

*   **`emitted_material_name`**: `spark_blue` - The material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - The duration particles exist.
*   **`count_min` / `count_max`**: `2` / `4` - The number of particles emitted per burst.
*   **`area_circle_radius.max`**: `48` - The maximum radius of the emission area.
*   **`velocity_always_away_from_center`**: `11` - Particles are always propelled away from the center.

### ParticleEmitterComponent (Secondary)
This component emits more sparks in a defined ring.

*   **`emitted_material_name`**: `spark_blue` - The material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - The duration particles exist.
*   **`count_min` / `count_max`**: `4` / `10` - The number of particles emitted per burst.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `48` / `48` - Particles are emitted in a ring with a radius of 48.

### Base File Inclusion
This projectile inherits properties from `data/entities/projectiles/deck/base_field.xml`.

#### SpriteComponent
Defines the visual representation of the field indicator.

*   **`image_file`**: `data/particles/area_indicator_096_blue.png` - The sprite used for the indicator.
*   **`z_index`**: `1.2` - Controls the rendering order.
*   **`offset_x` / `offset_y`**: `48` / `48` - Offsets the sprite's position.

#### SpriteParticleEmitterComponent
Emits arc particles to simulate electrical discharge.

*   **`sprite_file`**: `data/particles/arc.xml` - The sprite used for the arc particles.
*   **`lifetime`**: `0` - Arcs are short-lived.
*   **`color`**: `1, 1, 1, 1` - White color.
*   **`randomize_rotation`**: `-3.1415` to `3.1415` - Randomizes the rotation of arcs.
*   **`randomize_velocity`**: `-30` to `30` (x and y) - Randomizes the initial velocity of arcs.
*   **`randomize_position`**: `-48` to `48` (x and y) - Randomizes the emission position within a radius.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `12` / `20` - Controls the frequency of arc emissions.

#### ProjectileComponent
Defines the projectile's damage and explosion properties.

*   **`damage_game_effect_entities`**: `""` - No specific game effect entities are applied on hit.
*   **`config_explosion`**:
    *   **`explosion_sprite`**: `data/particles/blast_out.xml` - The sprite used for the explosion effect.

#### AudioLoopComponent
Handles the looping sound effect for the electrical field.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_name`**: `player_projectiles/field_electric/loop` - The specific sound event to play.
*   **`auto_play`**: `1` - The sound starts automatically when the entity is active.