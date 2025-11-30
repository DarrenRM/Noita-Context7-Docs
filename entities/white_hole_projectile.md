---
title: White Hole Projectile
category: entities
---

# White Hole Projectile

This document details the configuration of the "White Hole" projectile in Noita, focusing on its attributes and behaviors relevant to AI-assisted modding.

## Core Entity Configuration

The `White Hole` projectile is defined as an `Entity` with specific tags and a base projectile configuration.

```xml
<Entity name="$projectile_default" tags="projectile_player,black_hole">
    <Base file="data/entities/base_projectile.xml" />
    <!-- ... other components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Standard identifier for projectiles.
*   **`tags`**: `projectile_player`, `black_hole` - Identifies it as a player projectile and a black hole type.

## Projectile Component

This is the primary component defining the projectile's behavior, including its movement, collision, and death effects.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.8"
    lob_max="1.0"
    speed_min="40"
    speed_max="40"
    collide_with_world="0"
    direction_random_rad="0.00"
    on_death_explode="1"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="0"
    lifetime="120"
    damage="0"
    knockback_force="0.1"
    penetrate_entities="1"
    lifetime_randomness="7"
    camera_shake_when_shot="0.4"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_small_pink.xml"
    collide_with_shooter_frames="10"
    collide_with_entities="0"
    friendly_fire="1"
    shoot_light_flash_radius="100"
    shoot_light_flash_r="255"
    shoot_light_flash_g="180"
    shoot_light_flash_b="230"
>
    <config_explosion
        never_cache="1"
        damage="0"
        camera_shake="0"
        explosion_radius="1"
        explosion_sprite="data/particles/black_hole_out.xml"
        explosion_sprite_emissive="1"
        explosion_sprite_additive="1"
        create_cell_probability="0"
        hole_destroy_liquid="0"
        hole_enabled="1"
        physics_explosion_power.min="0"
        physics_explosion_power.max="0"
        shake_vegetation="1"
        sparks_count_max="1"
        sparks_count_min="4"
        sparks_enabled="1"
        spark_material="spark_white"
    >
    </config_explosion>
</ProjectileComponent>
```

### Key Projectile Attributes:

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile.
*   **`speed_min`, `speed_max`**: Sets the projectile's initial velocity.
*   **`collide_with_world="0"`**: The projectile does not collide with the environment.
*   **`on_death_explode="1"`, `on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime ends or it dies.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not harm the entity that fired it.
*   **`lifetime`**: Duration in frames before the projectile explodes.
*   **`damage="0"`**: The projectile itself deals no direct damage.
*   **`knockback_force`**: The force applied to entities upon collision (though `on_collision_die="0"` means it doesn't die on collision).
*   **`penetrate_entities="1"`**: The projectile can pass through multiple entities.
*   **`camera_shake_when_shot`**: Amount of camera shake when the projectile is fired.
*   **`muzzle_flash_file`**: Specifies the particle effect for the muzzle flash.
*   **`collide_with_entities="0"`**: The projectile does not collide with other entities.
*   **`friendly_fire="1"`**: Can affect friendly entities.
*   **`shoot_light_flash_*`**: Defines the color and radius of the light flash when shot.

### `config_explosion` Attributes:

*   **`explosion_radius`**: The radius of the explosion effect.
*   **`explosion_sprite`**: The visual sprite for the explosion.
*   **`hole_enabled="1"`**: Enables a "hole" effect as part of the explosion.
*   **`sparks_enabled="1"`**: Enables sparks during the explosion.
*   **`spark_material`**: The material used for the sparks.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/white_hole.xml"
    emissive="1"
    additive="1"
    rect_animation="fireball"
>
</SpriteComponent>
```

*   **`image_file`**: Path to the sprite's image data.
*   **`emissive="1"`, `additive="1"`**: Affects how the sprite is rendered, often for glowing effects.
*   **`rect_animation`**: Specifies the animation to use.

## Particle Emitter Component

Responsible for generating visual particles around the projectile.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark_white"
    x_pos_offset_min="-12"
    x_pos_offset_max="12"
    y_pos_offset_min="-12"
    y_pos_offset_max="12"
    x_vel_min="-8"
    x_vel_max="8"
    y_vel_min="-8"
    y_vel_max="8"
    count_min="1"
    count_max="4"
    lifetime_min="0.1"
    lifetime_max="1.5"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: The material of the particles being emitted.
*   **`x_pos_offset_min/max`, `y_pos_offset_min/max`**: Defines the area where particles are spawned relative to the projectile.
*   **`x_vel_min/max`, `y_vel_min/max`**: Sets the velocity range for emitted particles.
*   **`count_min/max`**: Number of particles emitted per burst.
*   **`lifetime_min/max`**: Duration of each particle.
*   **`emit_cosmetic_particles="1"`**: Particles are purely visual.

## Cell Eater Component

This component allows the projectile to consume certain materials or physics bodies.

```xml
<CellEaterComponent
    radius="12"
    eat_dynamic_physics_bodies="1"
    ignored_material_tag="[indestructible]"
>
</CellEaterComponent>
```

*   **`radius`**: The area of effect for eating.
*   **`eat_dynamic_physics_bodies="1"`**: Can consume physics objects.
*   **`ignored_material_tag`**: Materials with this tag will not be eaten.

## Audio Components

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/black_hole"
    set_latest_event_position="1" >
</AudioComponent>

<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="player_projectiles/black_hole/loop"
    auto_play="1">
</AudioLoopComponent>
```

*   **`file`**: Path to the audio bank.
*   **`event_root`**: Base event for the projectile's sounds.
*   **`event_name`**: Specific event for looping sounds.
*   **`auto_play="1"`**: The loop sound starts automatically.

## Lua Component

Links a Lua script to control custom behavior, such as gravity manipulation.

```xml
<LuaComponent
    script_source_file="data/scripts/projectiles/white_hole_gravity.lua"
    execute_every_n_frame="1"
>
</LuaComponent>
```

*   **`script_source_file`**: The path to the Lua script.
*   **`execute_every_n_frame`**: How often the script's logic is executed.

## Variable Storage Component

Stores custom variables for the entity.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/white_hole.xml"
>
</VariableStorageComponent>
```

*   **`name`**: `projectile_file`
*   **`value_string`**: The path to this entity's XML file, useful for referencing itself.