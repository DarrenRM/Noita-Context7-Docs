---
title: Big Firebug Projectile
category: entities
---

# Big Firebug Projectile

This document details the configuration for the "Big Firebug" projectile in Noita, focusing on its core attributes for AI-assisted modding.

## Entity Definition

The projectile is defined as an `Entity` with a base projectile configuration.

```xml
<Entity
  name="$projectile_default"
>
  <Base file="data/entities/base_projectile.xml">
    <VelocityComponent
      air_friction="-0.1"
      gravity_y="0"
      mass="0.04"
    >
    </VelocityComponent>
  </Base>
  <!-- ... other components ... -->
</Entity>
```

## Projectile Component

This is the primary component defining the projectile's behavior.

### Key Attributes:

*   **`lob_min`, `lob_max`**: Controls the projectile's arc.
    *   `lob_min="0.9"`
    *   `lob_max="1.0"` (Indicates a very straight trajectory)
*   **`speed_min`, `speed_max`**: Defines the projectile's velocity range.
    *   `speed_min="160"`
    *   `speed_max="200"`
*   **`friction`**: How much the projectile slows down.
    *   `friction="0.6"`
*   **`direction_random_rad`**: Adds slight randomness to the projectile's direction.
    *   `direction_random_rad="0.05"`
*   **`on_death_explode`**: If the projectile explodes upon death.
    *   `on_death_explode="1"`
*   **`on_lifetime_out_explode`**: If the projectile explodes when its lifetime expires.
    *   `on_lifetime_out_explode="1"`
*   **`on_collision_die`**: If the projectile dies on collision.
    *   `on_collision_die="1"`
*   **`die_on_liquid_collision`**: If the projectile dies upon hitting liquids.
    *   `die_on_liquid_collision="1"`
*   **`lifetime`**: Base duration before expiring.
    *   `lifetime="70"`
*   **`lifetime_randomness`**: Adds variability to the lifetime.
    *   `lifetime_randomness="7"`
*   **`damage`**: Base damage dealt by the projectile.
    *   `damage="0.2"`
*   **`knockback_force`**: The force applied to knock back entities on hit.
    *   `knockback_force="0.6"`
*   **`camera_shake_when_shot`**: Intensity of camera shake when the projectile is fired.
    *   `camera_shake_when_shot="1.0"`

### Damage by Type:

Defines how much damage this projectile deals to specific damage types.

```xml
<damage_by_type
  fire="0.3"
>
</damage_by_type>
```

### Config Explosion:

Details the explosion effect when `on_death_explode` or `on_lifetime_out_explode` is true.

*   **`camera_shake`**: Intensity of camera shake during the explosion.
    *   `camera_shake="4"`
*   **`explosion_radius`**: The area of effect for the explosion.
    *   `explosion_radius="10"`
*   **`explosion_sprite`**: The visual effect used for the explosion.
    *   `explosion_sprite="data/particles/explosion_016.xml"`
*   **`hole_enabled`**: Whether the explosion creates holes in terrain.
    *   `hole_enabled="1"`
*   **`ray_energy`**: The energy value for raycasting effects from the explosion.
    *   `ray_energy="15000"`
*   **`damage`**: Damage dealt by the explosion itself (distinct from projectile damage).
    *   `damage="0"` (In this case, the explosion itself doesn't deal direct damage, relying on other effects or the projectile's damage).
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: Controls the force of the physics-based explosion.
    *   `physics_explosion_power.min="0.18"`
    *   `physics_explosion_power.max="0.2"`
*   **`sparks_enabled`**: Whether sparks are generated.
    *   `sparks_enabled="1"`
*   **`stains_enabled`**: Whether ground stains are created.
    *   `stains_enabled="1"`
    *   `stains_radius="12"`

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.9"
  lob_max="1.0"
  speed_min="160"
  speed_max="200"
  friction="0.6"
  direction_random_rad="0.05"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="0"
  on_collision_die="1"
  die_on_liquid_collision="1"
  lifetime="70"
  damage="0.2"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.04"
  hit_particle_force_multiplier="5.5"
  camera_shake_when_shot="1.0"
  shoot_light_flash_radius="80"
  knockback_force="0.6"
>
  <damage_by_type
    fire="0.3"
  >
  </damage_by_type>
  <config_explosion
    never_cache="0"
    camera_shake="4"
    explosion_radius="10"
    explosion_sprite="data/particles/explosion_016.xml"
    explosion_sprite_lifetime="0"
    create_cell_probability="100"
    hole_destroy_liquid="0"
    explosion_sprite_emissive="1"
    explosion_sprite_additive="1"
    hole_enabled="1"
    ray_energy="15000"
    damage="0"
    particle_effect="0"
    damage_mortals="1"
    physics_explosion_power.min="0.18"
    physics_explosion_power.max="0.2"
    physics_throw_enabled="1"
    shake_vegetation="1"
    sparks_count_min="4"
    sparks_count_max="10"
    sparks_enabled="1"
    stains_enabled="1"
    stains_radius="12"
  >
  </config_explosion>
</ProjectileComponent>
```

## Sprite Component

Defines the visual appearance of the projectile.

*   **`image_file`**: Path to the sprite's XML definition.
    *   `image_file="data/projectiles_gfx/grenade_scavenger_small.xml"`
*   **`additive`, `emissive`**: Rendering properties for glow effects.
    *   `additive="1"`
    *   `emissive="1"`

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/grenade_scavenger_small.xml"
  offset_x="0"
  offset_y="0"
  additive="1"
  emissive="1"
>
</SpriteComponent>
```

## Particle Emitter Component

Controls the emission of particles from the projectile.

*   **`emitted_material_name`**: The material of the particles to emit.
    *   `emitted_material_name="fire"`
*   **`count_min`, `count_max`**: Number of particles emitted per emission.
    *   `count_min="1"`
    *   `count_max="1"`
*   **`lifetime_min`, `lifetime_max`**: Duration of emitted particles.
    *   `lifetime_min="0.1"`
    *   `lifetime_max="0.3"`
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: How often particles are emitted.
    *   `emission_interval_min_frames="1"`
    *   `emission_interval_max_frames="2"`

```xml
<ParticleEmitterComponent
  emitted_material_name="fire"
  offset.x="0"
  offset.y="0"
  x_pos_offset_min="-1"
  y_pos_offset_min="-1"
  x_pos_offset_max="1"
  y_pos_offset_max="1"
  x_vel_min="-10"
  x_vel_max="10"
  y_vel_min="-10"
  y_vel_max="10"
  count_min="1"
  count_max="1"
  lifetime_min="0.1"
  lifetime_max="0.3"
  create_real_particles="1"
  emit_cosmetic_particles="0"
  emission_interval_min_frames="1"
  emission_interval_max_frames="2"
  is_emitting="1"
>
</ParticleEmitterComponent>
```

## Light Component

Adds a light source to the projectile.

*   **`radius`**: The radius of the light.
    *   `radius="40"`

```xml
<LightComponent
  _enabled="1"
  radius="40"
>
</LightComponent>
```

## Audio Component

Defines the sound effects associated with the projectile.

*   **`file`**: Path to the audio bank.
    *   `file="data/audio/Desktop/projectiles.bank"`
*   **`event_root`**: The specific sound event to play.
    *   `event_root="projectiles/bullet_fire_small"`

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="projectiles/bullet_fire_small"
>
</AudioComponent>
```

## Variable Storage Component

Stores variables associated with the entity.

*   **`name`**: The name of the variable.
    *   `name="projectile_file"`
*   **`value_string`**: The string value of the variable.
    *   `value_string="data/entities/projectiles/fireball_bigfirebug.xml"`

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/fireball_bigfirebug.xml"
>
</VariableStorageComponent>
```