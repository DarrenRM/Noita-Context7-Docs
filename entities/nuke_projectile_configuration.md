---
title: Nuke Projectile Configuration
category: entities
---

# Nuke Projectile Configuration

This document details the configuration for the "Nuke" projectile entity in Noita, focusing on its explosive properties and behavior.

## Entity Definition

The core of the Nuke projectile is defined by the `<Entity>` tag.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name="$projectile_default"`**: This indicates it uses a default projectile name, likely overridden by specific spawning logic.
*   **`tags="projectile_player"`**: This tag signifies that the projectile originates from the player.

## Base Projectile Properties

The `<Base>` component inherits common projectile attributes.

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
      gravity_y="120"
      air_friction="0.00001"
      mass="0.2"
  >
  </VelocityComponent>
</Base>
```

*   **`gravity_y="120"`**: Applies a moderate downward gravitational pull.
*   **`air_friction="0.00001"`**: Minimal air resistance, allowing the projectile to travel with less deceleration.
*   **`mass="0.2"`**: A relatively low mass for the projectile.

## Projectile Component - Behavior and Effects

The `<ProjectileComponent>` defines the specific behaviors and effects of the Nuke projectile.

```xml
<ProjectileComponent
  _enabled="1"
  speed_min="0"
  speed_max="0"
  direction_random_rad="0.01"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  lifetime="1"
  damage="0"
  velocity_sets_scale="0"
  lifetime_randomness="0"
  ragdoll_force_multiplier="0"
  hit_particle_force_multiplier="0"
  camera_shake_when_shot="0.0"
  muzzle_flash_file=""
  knockback_force="0"
>
  <!-- ... config_explosion ... -->
</ProjectileComponent>
```

**Key Attributes:**

*   **`on_death_explode="1"`**: The projectile will explode when it dies (e.g., on collision or when its lifetime ends).
*   **`on_lifetime_out_explode="1"`**: The projectile will explode when its `lifetime` expires.
*   **`explosion_dont_damage_shooter="1"`**: Prevents the explosion from harming the player who fired it.
*   **`on_collision_die="1"`**: The projectile will die and explode upon colliding with something.
*   **`lifetime="1"`**: The projectile exists for a very short duration (1 second) before expiring and exploding.
*   **`damage="0"`**: The projectile itself deals no direct damage; all damage comes from the explosion.
*   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial velocity upon spawning, suggesting it's likely affected by other forces or is intended to detonate immediately.
*   **`direction_random_rad="0.01"`**: A very slight random deviation in direction.

### Explosion Configuration

The `<config_explosion>` block defines the parameters of the explosion itself.

```xml
<config_explosion
  never_cache="1"
  camera_shake="60"
  explosion_radius="250"
  explosion_sprite="data/particles/explosion_032.xml"
  load_this_entity="data/entities/particles/particle_explosion/main_large.xml"
  explosion_sprite_lifetime="0"
  create_cell_probability="0"
  hole_destroy_liquid="0"
  hole_enabled="1"
  ray_energy="6700000"
  damage="10"
  particle_effect="1"
  damage_mortals="1"
  physics_explosion_power.min="4.5"
  physics_explosion_power.max="9"
  shake_vegetation="1"
  sparks_count_max="1500"
  sparks_count_min="1600"
  sparks_enabled="1"
  stains_enabled="1"
  stains_radius="35"
  background_lightning_count="5"
  max_durability_to_destroy="12"
  audio_event_name="explosions/nuke"
>
</config_explosion>
```

**Key Explosion Attributes:**

*   **`camera_shake="60"`**: Causes significant camera shake upon explosion.
*   **`explosion_radius="250"`**: Defines a very large area of effect for the explosion.
*   **`explosion_sprite="data/particles/explosion_032.xml"`**: Specifies the visual sprite for the explosion effect.
*   **`load_this_entity="data/entities/particles/particle_explosion/main_large.xml"`**: Loads a specific entity for the main explosion particle effect.
*   **`hole_enabled="1"`**: Creates holes in the environment upon explosion.
*   **`ray_energy="6700000"`**: A very high energy value, indicating a powerful destructive force.
*   **`damage="10"`**: The explosion deals 10 damage to entities within its radius.
*   **`damage_mortals="1"`**: The explosion is capable of damaging living entities.
*   **`physics_explosion_power.min="4.5"`, `physics_explosion_power.max="9"`**: The explosion has a strong physical impact, capable of pushing objects.
*   **`sparks_count_max="1500"`, `sparks_count_min="1600"`**: Generates a large number of sparks.
*   **`stains_radius="35"`**: Creates large stains on surfaces.
*   **`background_lightning_count="5"`**: Triggers background lightning effects.
*   **`max_durability_to_destroy="12"`**: The explosion can destroy objects with up to this durability.
*   **`audio_event_name="explosions/nuke"`**: Triggers a specific sound effect for the explosion.