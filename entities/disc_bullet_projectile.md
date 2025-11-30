---
title: Disc Bullet Projectile
category: entities
---

# Disc Bullet Projectile

This document details the `disc_bullet.xml` entity, which defines the behavior and appearance of the disc bullet projectile in Noita.

## Core Components

### Entity Definition

```xml
<Entity name="$projectile_default" tags="projectile_player,disc_bullet" >
```

*   **`name`**: `$projectile_default` - A placeholder name, indicating this entity inherits default projectile properties.
*   **`tags`**: `projectile_player,disc_bullet` - Identifies this as a player projectile and specifically a disc bullet.

### Base Projectile (`BaseComponent`)

This component inherits fundamental projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="250"
        air_friction="0.6"
        mass="0.05"
        >
    </VelocityComponent>
</Base>
```

*   **`VelocityComponent`**:
    *   `gravity_y`: `250` - Applies downward gravitational pull.
    *   `air_friction`: `0.6` - Resistance to movement in the air.
    *   `mass`: `0.05` - The projectile's mass, affecting its interaction with physics.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the disc bullet's unique characteristics.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.5"
    lob_max="0.7"
    speed_min="350"
    speed_max="450"
    friction="1"
    direction_random_rad="0.01"
    on_death_explode="0"
    on_death_gfx_leave_sprite="1"
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
    on_collision_remove_projectile="0"
    lifetime="750"
    damage="0"
    damage_scaled_by_speed="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0"
    hit_particle_force_multiplier="0.1"
    create_shell_casing="0"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_medium.xml"
    shoot_light_flash_r="255"
    shoot_light_flash_g="240"
    shoot_light_flash_b="30"
    shoot_light_flash_radius="64"
    die_on_low_velocity="1"
    die_on_low_velocity_limit="5"
    bounces_left="2"
    bounce_at_any_angle="1"
    collide_with_shooter_frames="6"
    friendly_fire="1"
    velocity_sets_rotation="1"
    velocity_updates_animation="1"
    velocity_sets_scale="0"
    ragdoll_fx_on_collision="BLOOD_EXPLOSION"
    knockback_force="1.3"
    physics_impulse_coeff="1500"
    >
    <damage_by_type
        slice="0.8"
        >
    </damage_by_type>
    <config_explosion>
    </config_explosion>
</ProjectileComponent>
```

*   **`lob_min`, `lob_max`**: `0.5`, `0.7` - Controls the arc of the projectile.
*   **`speed_min`, `speed_max`**: `350`, `450` - Defines the projectile's initial speed range.
*   **`direction_random_rad`**: `0.01` - Small random deviation in projectile direction.
*   **`on_death_explode`**: `0` - Does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `1` - Leaves a sprite graphic when it dies.
*   **`on_collision_die`**: `1` - The projectile dies upon collision.
*   **`lifetime`**: `750` - Duration in frames before the projectile is removed.
*   **`damage`**: `0` - Base damage value.
*   **`damage_scaled_by_speed`**: `1` - Damage increases with projectile speed.
*   **`bounces_left`**: `2` - The projectile can bounce a maximum of 2 times.
*   **`bounce_at_any_angle`**: `1` - Can bounce off surfaces regardless of the impact angle.
*   **`collide_with_shooter_frames`**: `6` - The projectile will not collide with the shooter for the first 6 frames.
*   **`friendly_fire`**: `1` - Can damage friendly entities.
*   **`velocity_sets_rotation`**: `1` - The projectile's rotation is determined by its velocity.
*   **`velocity_updates_animation`**: `1` - The projectile's animation updates based on its velocity.
*   **`knockback_force`**: `1.3` - The force applied to knock back entities upon collision.
*   **`physics_impulse_coeff`**: `1500` - Coefficient for physics impulse calculations.
*   **`damage_by_type`**:
    *   `slice`: `0.8` - Modifies damage dealt to specific entity types (e.g., slice damage).

### Visual Representation (`SpriteComponent`)

Defines the visual appearance of the disc bullet.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/disc_bullet.xml"
    >
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/disc_bullet.xml` - Specifies the sprite graphic file.

### Trail Effect (`SpriteParticleEmitterComponent`)

Creates a visual trail behind the projectile.

```xml
<SpriteParticleEmitterComponent
    sprite_file="data/particles/discbullet_trail.xml"
    delay="0"
    lifetime="1"
    additive="1"
    color.r="1" color.g="1" color.b="1" color.a="1"
    color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-4"
    gravity.y="10"
    emission_interval_min_frames="5"
    emission_interval_max_frames="5"
    count_min="1" count_max="1"
    is_emitting="1"
    render_back="1"
    >
</SpriteParticleEmitterComponent>
```

*   **`sprite_file`**: `data/particles/discbullet_trail.xml` - The particle sprite used for the trail.
*   **`lifetime`**: `1` - Short lifetime for each emitted particle.
*   **`color_change.a`**: `-4` - The alpha (transparency) of the particles decreases over time.
*   **`gravity.y`**: `10` - Particles are affected by a slight downward gravity.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `5` - Particles are emitted every 5 frames.
*   **`is_emitting`**: `1` - The emitter is active.

### Audio (`AudioComponent`, `AudioLoopComponent`)

Handles the sound effects associated with the disc bullet.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_disc">
</AudioComponent>

<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="player_projectiles/bullet_disc/loop"
    set_speed_parameter="1"
    auto_play="1">
</AudioLoopComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
*   **`event_root`**: `player_projectiles/bullet_disc` - The base event for the projectile's sound.
*   **`event_name`**: `player_projectiles/bullet_disc/loop` - The specific event for the looping sound.
*   **`auto_play`**: `1` - The sound loop starts automatically.

### Variable Storage (`VariableStorageComponent`)

Stores a reference to the projectile's own entity file.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/disc_bullet.xml"
    >
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/disc_bullet.xml` - The path to this entity's XML file.