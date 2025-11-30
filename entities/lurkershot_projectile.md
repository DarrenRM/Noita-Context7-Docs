---
title: Lurkershot Projectile
category: entities
---

# Lurkershot Projectile

This document details the `lurkershot.xml` entity, which defines the behavior and properties of the Lurkershot projectile in Noita.

## Core Components

The Lurkershot projectile is built upon several core Noita entity components, each contributing to its unique functionality.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0.6"`: A moderate amount of air resistance is applied.
    *   `mass="0.07"`: Defines the projectile's mass.

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's behavior.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the arc of the projectile, with a slight randomness.
*   **`speed_min="150"`, `speed_max="150"`**: The projectile travels at a constant speed of 150 units.
*   **`friction="1"`**: High friction, suggesting it slows down if it hits something.
*   **`direction_random_rad="0.01"`**: A very small amount of randomness in its initial direction.
*   **`on_death_explode="0"`**: Does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: Does not leave a sprite upon death.
*   **`on_lifetime_out_explode="0"`**: Does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: If it were to explode, it wouldn't damage the entity that fired it.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with an entity.
*   **`on_collision_remove_projectile="0"`**: The projectile is not removed from the game world upon collision (it dies instead).
*   **`lifetime="60"`**: The projectile exists for a maximum of 60 frames.
*   **`damage="0.5"`**: Deals 0.5 base damage.
*   **`damage_scaled_by_speed="1"`**: Damage increases with projectile speed.
*   **`lifetime_randomness="7"`**: The projectile's lifetime can vary by up to 7 frames.
*   **`knockback_force="1.0"`**: Applies a knockback force of 1.0 to entities it hits.
*   **`penetrate_entities="1"`**: The projectile can pass through multiple entities.

### Lua Component (`LuaComponent`)

This component enables custom scripting for the projectile.

*   **`script_source_file="data/scripts/animals/lurkershot_end.lua"`**: Links to a Lua script that executes when the projectile is removed. This script likely handles the "end" behavior of the lurkershot.
*   **`execute_on_removed="1"`**: The script runs when the projectile is removed from the game.

### Variable Storage Components (`VariableStorageComponent`)

These components store custom variables associated with the entity.

*   **`_tags="lurkershot_id"`, `name="lurkershot_id"`, `value_int="0"`**: Stores an integer tag named `lurkershot_id` with an initial value of 0. This might be used for internal tracking or identification.
*   **`name="projectile_file"`, `value_string="data/entities/projectiles/lurkershot.xml"`**: Stores the path to this entity's XML file, likely for referencing by other systems.

### Audio Component (`AudioComponent`)

Handles sound effects for the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound.
*   **`event_root="projectiles/bullet_burst_of_air"`**: The specific sound event to play.

### Sprite Particle Emitter Component (`SpriteParticleEmitterComponent`)

This component generates visual particle effects.

*   **`sprite_file="data/particles/lurkershot.xml"`**: Defines the particle sprites to be used.
*   **`emission_interval_min_frames="2"`, `emission_interval_max_frames="5"`**: Particles are emitted every 2 to 5 frames.
*   **`count_min="1"`, `count_max="1"`**: Emits one particle at a time.
*   **`randomize_position.min_x="-8"`, `randomize_position.max_x="8"`, etc.**: Particles are emitted within a small randomized area around the projectile.
*   **`randomize_velocity.min_y="-8"`, `randomize_velocity.max_y="8"`, etc.**: Particles have a slight randomized velocity.

### Area Damage Component (`AreaDamageComponent`)

This component allows the projectile to deal damage over an area.

*   **`aabb_min.x="-10"`, `aabb_min.y="-10"`, `aabb_max.x="10"`, `aabb_max.y="10"`**: Defines a circular area of effect with a radius of 10 units around the projectile.
*   **`damage_per_frame="0.10"`**: Deals 0.10 damage per frame to entities within the area.
*   **`update_every_n_frame="6"`**: The damage is applied every 6 frames.
*   **`entities_with_tag="prey"`**: Only applies damage to entities tagged as "prey".
*   **`damage_type="DAMAGE_CURSE"`**: The damage dealt is of the "curse" type.