---
title: Rocket Roll Projectile
category: entities
---

---

# Rocket Roll Projectile

This document details the `rocket_roll.xml` entity, which defines a specific type of projectile used by the boss robot in Noita. It's designed to be a rolling projectile with unique behaviors upon collision and expiration.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag, specifying its name and associated tags.

```xml
<Entity name="$projectile_default" tags="projectile_player,disc_bullet" >
  <!-- ... other components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - This indicates it's a default projectile type, likely with specific overrides.
*   **`tags`**: `projectile_player,disc_bullet` - These tags help categorize the projectile for game logic and interactions.

## Base Projectile Configuration

The `<Base>` component inherits properties from `data/entities/base_projectile.xml`.

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
    *   `gravity_y="250"`: Applies a moderate downward gravitational pull.
    *   `air_friction="0.6"`: The projectile experiences significant air resistance.
    *   `mass="0.05"`: A very light projectile.

## Projectile Component - Key Attributes

The `<ProjectileComponent>` defines the core behavior and properties of the projectile.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.5"
    lob_max="0.7"
    speed_min="350"
    speed_max="450"
    friction="1"
    direction_random_rad="0.41"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1"
    on_collision_die="0"
    lifetime="90"
    damage="0"
    damage_scaled_by_speed="0"
    lifetime_randomness="0"
    ragdoll_force_multiplier="0"
    hit_particle_force_multiplier="0.1"
    create_shell_casing="0"
    shoot_light_flash_radius="64"
    bounces_left="2"
    bounce_at_any_angle="1"
    collide_with_shooter_frames="6"
    friendly_fire="1"
    velocity_sets_rotation="1"
    velocity_updates_animation="0"
    velocity_sets_scale="0"
    knockback_force="1.3"
    physics_impulse_coeff="10"
    collide_with_entities="0"
    >
    <config_explosion>
    </config_explosion>
</ProjectileComponent>
```

*   **`lob_min`, `lob_max`**: Controls the projectile's arc, suggesting a slightly lobbing trajectory.
*   **`speed_min`, `speed_max`**: Defines a range for the projectile's initial speed.
*   **`direction_random_rad`**: Introduces a slight random deviation in the projectile's initial direction.
*   **`on_death_explode`, `on_lifetime_out_explode`**: Set to `0`, meaning the projectile does not explode upon death or when its lifetime expires.
*   **`on_collision_die`**: Set to `0`, indicating the projectile does not die immediately upon collision.
*   **`lifetime`**: `90` frames.
*   **`damage`**: `0`. This projectile itself does not deal direct damage.
*   **`bounces_left`**: `2`. The projectile can bounce twice.
*   **`bounce_at_any_angle`**: `1`. Allows bouncing regardless of the angle of impact.
*   **`collide_with_shooter_frames`**: `6`. The projectile will ignore collisions with its shooter for the first 6 frames.
*   **`friendly_fire`**: `1`. This projectile can damage friendly entities.
*   **`velocity_sets_rotation`**: `1`. The projectile's rotation will be updated based on its velocity.
*   **`knockback_force`**: `1.3`. Applies a moderate knockback effect.
*   **`collide_with_entities`**: `0`. This is a crucial setting; the projectile *does not* collide with other entities by default. Its behavior is likely managed by other components or scripts.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/rocket_roll.xml"
    next_rect_animation=""
    rect_animation=""
     >
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/rocket_roll.xml` - Specifies the graphical asset used for the projectile.

## Audio Component

Handles the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_disc">
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
*   **`event_root`**: `player_projectiles/bullet_disc` - The specific sound event to trigger.

## Lua Component - Scripting Logic

This component attaches a Lua script to the projectile, enabling custom behavior.

```xml
<LuaComponent
    script_source_file="data/entities/animals/boss_robot/rocket_roll_end.lua"
    execute_every_n_frame="85"
    remove_after_executed="1"
    >
</LuaComponent>
```

*   **`script_source_file`**: `data/entities/animals/boss_robot/rocket_roll_end.lua` - The script responsible for custom logic, likely executed near the end of the projectile's life or upon specific events.
*   **`execute_every_n_frame`**: `85` - The script will execute every 85 frames.
*   **`remove_after_executed`**: `1` - The entity will be removed after the script has executed.

## Variable Storage Component

Stores custom variables associated with the entity.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/rocket_tank.xml"
    >
</VariableStorageComponent>
```

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/rocket_tank.xml` - This suggests that when this projectile is "used" or "dies" in a specific way, it might spawn or transform into a `rocket_tank.xml` projectile. This is a common pattern for projectile chaining or transformations.