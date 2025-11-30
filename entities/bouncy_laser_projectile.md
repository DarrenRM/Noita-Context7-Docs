---
title: Bouncy Laser Projectile
category: entities
---

---

# Bouncy Laser Projectile

This document details the configuration of a bouncy laser projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag, inheriting base projectile properties.

```xml
<Entity name="$projectile_default">
  <Base file="data/entities/base_projectile.xml">
    <VelocityComponent
      air_friction="-10"
      gravity_y="0"
      mass="0.04"
    >
    </VelocityComponent>
  </Base>
  <!-- ... other components ... -->
</Entity>
```

## Projectile Component (`ProjectileComponent`)

This component governs the projectile's behavior, including its movement, interactions, and effects.

### Key Attributes:

| Attribute                 | Description                                                                                             | Example Value |
| :------------------------ | :------------------------------------------------------------------------------------------------------ | :------------ |
| `lob_min`, `lob_max`      | Controls the minimum and maximum lobbing angle of the projectile.                                       | `0.8`, `1.0`  |
| `speed_min`, `speed_max`  | Sets the minimum and maximum initial speed of the projectile.                                           | `130`, `150`  |
| `friction`                | The friction applied to the projectile, affecting its deceleration.                                     | `-15.0`       |
| `on_death_explode`        | If `1`, the projectile explodes upon death.                                                             | `1`           |
| `on_lifetime_out_explode` | If `1`, the projectile explodes when its lifetime expires.                                              | `1`           |
| `on_collision_die`        | If `1`, the projectile dies upon colliding with an entity.                                              | `1`           |
| `die_on_liquid_collision` | If `1`, the projectile dies upon colliding with a liquid.                                               | `1`           |
| `lifetime`                | The base lifetime of the projectile in frames.                                                          | `30`          |
| `lifetime_randomness`     | Adds randomness to the projectile's lifetime.                                                           | `7`           |
| `damage`                  | The base damage dealt by the projectile.                                                                | `0.35`        |
| `bounces_left`            | The number of bounces the projectile can perform before dying.                                          | `10`          |
| `bounce_always`           | If `1`, the projectile will always attempt to bounce, even off surfaces that might normally stop it.    | `1`           |
| `bounce_energy`           | The energy retained after a bounce (0.0 to 1.0). Higher values mean less energy loss.                  | `0.9`         |
| `knockback_force`         | The force applied to entities when the projectile hits them.                                            | `1.5`         |
| `camera_shake_when_shot`  | The amount of camera shake applied to the player when this projectile is shot.                          | `2.0`         |
| `shoot_light_flash_radius`| The radius of the light flash emitted when the projectile is shot.                                      | `180`         |
| `go_through_this_material`| Specifies a material that the projectile can pass through without colliding.                            | `gem_box2d`   |

### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion that occurs when the projectile dies or its lifetime expires.

| Attribute                 | Description                                                                                             | Example Value |
| :------------------------ | :------------------------------------------------------------------------------------------------------ | :------------ |
| `camera_shake`            | The intensity of camera shake caused by the explosion.                                                  | `4.5`         |
| `explosion_radius`        | The radius of the explosion's effect.                                                                   | `3`           |
| `explosion_sprite`        | The sprite file used for the explosion visual effect.                                                   | `data/particles/explosion_016_plasma.xml` |
| `create_cell_material`    | The material to create as cells within the explosion area.                                              | `plasma_fading` |
| `create_cell_probability` | The probability (0-100) of creating cells.                                                              | `15`          |
| `hole_enabled`            | If `1`, the explosion creates a hole in the environment.                                                | `1`           |
| `ray_energy`              | The energy of the explosion's damaging rays.                                                            | `10000`       |
| `damage`                  | The damage dealt by the explosion itself (note: this is separate from projectile damage).               | `0`           |
| `physics_explosion_power` | The minimum and maximum power of the physics-based explosion effect.                                    | `min="0.2"`, `max="0.7"` |
| `stains_enabled`          | If `1`, the explosion leaves stains on surfaces.                                                        | `1`           |
| `stains_radius`           | The radius of the stains left by the explosion.                                                         | `4`           |

## Sprite Component (`SpriteComponent`)

Defines the visual representation of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/laser.xml"
  offset_x="0"
  offset_y="0"
>
</SpriteComponent>
```

*   `image_file`: Specifies the sprite asset for the projectile.

## Light Component (`LightComponent`)

Adds a light source to the projectile, affecting the surrounding environment.

```xml
<LightComponent
  _enabled="1"
  radius="150"
  r="30"
  g="120"
  b="160">
</LightComponent>
```

*   `radius`: The range of the light.
*   `r`, `g`, `b`: The color components of the light.

## Particle Emitter Components

These components are responsible for generating visual particle effects associated with the projectile.

### `ParticleEmitterComponent` (Trail)

```xml
<ParticleEmitterComponent
  emitted_material_name="plasma_fading"
  is_trail="1"
  trail_gap="0.5"
  lifetime_min="0.2"
  lifetime_max="0.4"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  is_emitting="1"
>
</ParticleEmitterComponent>
```

*   `emitted_material_name`: The material of the particles emitted.
*   `is_trail`: If `1`, the particles form a trail.
*   `trail_gap`: The spacing between trail particles.

### `SpriteParticleEmitterComponent` (Sparks)

```xml
<SpriteParticleEmitterComponent
  sprite_file="data/particles/spark_electric.xml"
  emission_interval_min_frames="1"
  emission_interval_max_frames="3"
  count_min="1" count_max="1"
  randomize_rotation.min="-3.1415"
  randomize_rotation.max="3.1415"
  randomize_position.min_x="-2"
  randomize_position.max_x="2"
  randomize_position.min_y="-2"
  randomize_position.max_y="2"
>
</SpriteParticleEmitterComponent>
```

*   `sprite_file`: The sprite asset for the emitted sparks.
*   `randomize_position`: Controls the random spread of spark positions.

## Audio Component (`AudioComponent`)

Handles the sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="projectiles/laser">
</AudioComponent>
```

*   `file`: The audio bank containing the sound events.
*   `event_root`: The specific sound event to trigger.

## Variable Storage Component (`VariableStorageComponent`)

Stores custom variables for the entity.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/laser_bouncy.xml"
>
</VariableStorageComponent>
```

*   `name`: The name of the variable.
*   `value_string`: The string value of the variable, often used to reference the entity's own file.