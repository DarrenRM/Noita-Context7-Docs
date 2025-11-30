---
title: Heal Shot Projectile
category: entities
---

# Heal Shot Projectile

This document details the configuration for a slow-moving healing projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag.

```xml
<Entity name="$projectile_default" tags="projectile_heal">
  <!-- ... components ... -->
</Entity>
```

*   **`name="$projectile_default"`**: A placeholder name, often overridden by specific projectile definitions.
*   **`tags="projectile_heal"`**: Crucial tag indicating this projectile's healing properties.

## Base Projectile Configuration

Inherits fundamental projectile behaviors from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
    gravity_y="0"
    mass="0.04">
  </VelocityComponent>
</Base>
```

*   **`gravity_y="0"`**: The projectile is not affected by gravity, allowing for straight trajectories.
*   **`mass="0.04"`**: Defines the projectile's mass.

## Projectile Component - Key Attributes

This component governs the projectile's behavior, trajectory, and effects.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.8"
  lob_max="1.1"
  friendly_fire="1"
  speed_min="250"
  speed_max="300"
  direction_random_rad="0.003"
  on_death_explode="1"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  lifetime="100"
  velocity_sets_scale="1"
  hit_particle_force_multiplier="0"
  go_through_this_material="aluminium_robot"
  damage="0"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_large.xml">
  <!-- ... damage_by_type, config_explosion ... -->
</ProjectileComponent>
```

*   **`_enabled="1"`**: Enables this component.
*   **`lob_min`, `lob_max`**: Controls the arc of the projectile. Values close to 1 suggest a relatively straight path.
*   **`friendly_fire="1"`**: Allows the projectile to affect allies.
*   **`speed_min`, `speed_max`**: Sets the projectile's speed range.
*   **`direction_random_rad="0.003"`**: Introduces a very small amount of randomness to the projectile's direction.
*   **`on_death_explode="1"`**: The projectile explodes upon death (e.g., hitting a target or expiring).
*   **`on_lifetime_out_explode="1"`**: Explodes when its `lifetime` expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion will not harm the entity that fired it.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`lifetime="100"`**: The duration in frames before the projectile expires.
*   **`velocity_sets_scale="1"`**: The projectile's scale is influenced by its velocity.
*   **`hit_particle_force_multiplier="0"`**: No force is applied to particles upon impact.
*   **`go_through_this_material="aluminium_robot"`**: The projectile can pass through entities tagged with "aluminium\_robot".
*   **`damage="0"`**: Base damage is zero, as healing is handled by `damage_by_type`.
*   **`muzzle_flash_file`**: Specifies the visual effect for the muzzle flash when shot.

### Damage by Type

Defines how damage is applied, specifically for healing.

```xml
<damage_by_type
  healing="-0.2">
</damage_by_type>
```

*   **`healing="-0.2"`**: This is the key attribute for healing. A negative value indicates healing. The magnitude determines the amount of healing applied.

### Explosion Configuration

Details the explosion effect when the projectile is destroyed.

```xml
<config_explosion
  never_cache="1"
  damage="0"
  camera_shake="0"
  explosion_radius="1"
  explosion_sprite="data/particles/explosion_016_plasma_green.xml"
  explosion_sprite_lifetime="1"
  explosion_sprite_emissive="1"
  explosion_sprite_additive="1"
  create_cell_probability="0"
  hole_destroy_liquid="0"
  hole_enabled="0"
  ray_energy="10000"
  particle_effect="0"
  physics_explosion_power.min="0"
  physics_explosion_power.max="0"
  physics_throw_enabled="1"
  shake_vegetation="1"
  sparks_enabled="0"
  light_enabled="0"
  stains_enabled="0">
</config_explosion>
```

*   **`damage="0"`**: The explosion itself does not deal damage.
*   **`explosion_radius="1"`**: The radius of the explosion effect.
*   **`explosion_sprite`**: The visual sprite used for the explosion.
*   **`explosion_sprite_emissive`, `explosion_sprite_additive`**: Control visual rendering properties of the explosion sprite.
*   **`physics_explosion_power.min/max="0"`**: No physics-based force is applied by the explosion.
*   **`physics_throw_enabled="1"`**: Allows for physics-based interaction with the environment.
*   **`shake_vegetation="1"`**: Causes vegetation to shake upon explosion.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/grenade_green.xml"
  emissive="1"
  additive="1">
</SpriteComponent>
```

*   **`image_file`**: Specifies the graphical asset for the projectile.
*   **`emissive="1"`, `additive="1"`**: Rendering properties for the sprite.

## Sprite Particle Emitter Component

Generates particles associated with the projectile, likely for visual feedback.

```xml
<SpriteParticleEmitterComponent
  sprite_file="data/particles/heal.xml"
  delay="0"
  lifetime="0"
  color.r="1" color.g="1" color.b="1" color.a="1"
  gravity.y="10"
  emission_interval_min_frames="6"
  emission_interval_max_frames="10"
  count_min="1" count_max="1"
  randomize_rotation.min="-0.3415"
  randomize_rotation.max="0.3415"
  randomize_angular_velocity.min="-1.3415"
  randomize_angular_velocity.max="1.3415"
  randomize_position.min_x="-2"
  randomize_position.max_x="2"
  randomize_position.min_y="-2"
  randomize_position.max_y="2"
  randomize_velocity.min_x="-10"
  randomize_velocity.max_x="10"
  randomize_velocity.min_y="-10"
  randomize_velocity.max_y="10">
</SpriteParticleEmitterComponent>
```

*   **`sprite_file="data/particles/heal.xml"`**: The particle effect used, likely a healing visual.
*   **`gravity.y="10"`**: Particles are affected by gravity.
*   **`emission_interval_min/max_frames`**: Controls the timing of particle emissions.
*   **`count_min/max`**: Number of particles emitted per interval.
*   **`randomize_*`**: Various parameters for randomizing particle properties like rotation, velocity, and position.

## Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="projectiles/bullet_heal">
</AudioComponent>
```

*   **`file`**: The audio bank containing the sound events.
*   **`event_root`**: The specific sound event to play for this projectile.

## Variable Storage Component

Stores custom variables for the entity.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/healshot_slow.xml">
</VariableStorageComponent>
```

*   **`name="projectile_file"`**: Stores the path to this projectile's entity file, useful for referencing.