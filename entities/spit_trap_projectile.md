---
title: Spit Trap Projectile
category: entities
---

# Spit Trap Projectile

This document details the configuration of the "Spit Trap" projectile entity in Noita, primarily focusing on its physical properties, behavior, and particle effects.

## Entity Configuration

The projectile is based on `base_projectile.xml`, inheriting its fundamental structure.

```xml
<Entity
  name="$projectile_default"
>
  <Base file="data/entities/base_projectile.xml">
    <VelocityComponent
      gravity_y="0"
      mass="0.02"
    >
    </VelocityComponent>
  </Base>
  </Entity>
```

### Key Attributes:

*   **`gravity_y="0"`**: The projectile is not affected by gravity, allowing for consistent trajectory.
*   **`mass="0.02"`**: A very low mass, contributing to its projectile behavior.

## Projectile Component

This component defines the core mechanics of the projectile.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.8"
  lob_max="1.0"
  speed_min="360"
  speed_max="360"
  friction="0.0"
  on_death_explode="0"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="0"
  explosion_dont_damage_shooter="1"
  die_on_low_velocity="0"
  on_collision_die="0"
  lifetime="20"
  damage="0.2"
  penetrate_entities="1"
  penetrate_world="1"
  velocity_sets_scale="0"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.01"
  hit_particle_force_multiplier="0.25"
  camera_shake_when_shot="0.0"
>
</ProjectileComponent>
```

### Key Attributes:

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile. Values close to 1 suggest a relatively straight trajectory.
*   **`speed_min="360"`, `speed_max="360"`**: The projectile travels at a constant speed of 360 units.
*   **`friction="0.0"`**: No friction is applied, meaning its speed is not reduced over time due to air resistance.
*   **`lifetime="20"`**: The projectile exists for a maximum of 20 frames.
*   **`lifetime_randomness="7"`**: Adds up to 7 frames of randomness to the projectile's lifetime.
*   **`damage="0.2"`**: Deals a small amount of damage.
*   **`penetrate_entities="1"`, `penetrate_world="1"`**: The projectile can pass through both entities and the environment.
*   **`on_death_explode="0"`, `on_lifetime_out_explode="0"`, `on_collision_die="0"`**: The projectile does not explode upon death, reaching the end of its lifetime, or colliding.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion were to occur (which it doesn't by default), it wouldn't damage the shooter.
*   **`die_on_low_velocity="0"`**: The projectile will not die if its velocity drops too low.
*   **`ragdoll_force_multiplier="0.01"`**: A very small multiplier for ragdoll force upon impact.
*   **`hit_particle_force_multiplier="0.25"`**: Controls the force applied to particles when the projectile hits something.
*   **`camera_shake_when_shot="0.0"`**: No camera shake is triggered when this projectile is fired.

## Particle Emitter Component

This component defines the visual particles emitted by the projectile.

```xml
<ParticleEmitterComponent
  emitted_material_name="acid"
  count_min="7"
  count_max="15"
  offset.x="0"
  offset.y="1"
  x_pos_offset_min="-4"
  y_pos_offset_min="-4"
  x_pos_offset_max="4"
  y_pos_offset_max="4"
  x_vel_min="-10"
  x_vel_max="10"
  y_vel_min="-10"
  y_vel_max="10"
  count_min="1"
  count_max="2"
  lifetime_min="1.1"
  lifetime_max="2.8"
  create_real_particles="1"
  emit_cosmetic_particles="0"
  emission_interval_min_frames="1"
  emission_interval_max_frames="2"
  is_emitting="1"
>
</ParticleEmitterComponent>
```

### Key Attributes:

*   **`emitted_material_name="acid"`**: The particles emitted are of the "acid" material type.
*   **`count_min="7"`, `count_max="15"`**: A burst of 7 to 15 particles is emitted initially.
*   **`x_pos_offset_min="-4"`, `y_pos_offset_min="-4"`, `x_pos_offset_max="4"`, `y_pos_offset_max="4"`**: Particles are emitted within a small square area around the projectile's origin.
*   **`x_vel_min="-10"`, `x_vel_max="10"`, `y_vel_min="-10"`, `y_vel_max="10"`**: Particles are given a random velocity within this range.
*   **`lifetime_min="1.1"`, `lifetime_max="2.8"`**: Individual particles last between 1.1 and 2.8 frames.
*   **`create_real_particles="1"`**: These are actual game particles, not just cosmetic effects.
*   **`emit_cosmetic_particles="0"`**: No cosmetic particles are emitted.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`**: Particles are emitted in rapid succession, with intervals of 1-2 frames.
*   **`is_emitting="1"`**: The particle emitter is active.

## Audio Component

This component defines the sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="projectiles/acid"
>
</AudioComponent>
```

### Key Attributes:

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound events.
*   **`event_root="projectiles/acid"`**: Indicates the specific sound event to play, likely related to acid projectiles.

## Variable Storage Component

This component stores a variable related to the projectile's behavior.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/acidburst.xml"
>
</VariableStorageComponent>
```

### Key Attributes:

*   **`name="projectile_file"`**: The name of the variable being stored.
*   **`value_string="data/entities/projectiles/acidburst.xml"`**: The value of the variable, pointing to another projectile entity file. This suggests that upon certain conditions (not explicitly defined here, but implied by the variable name), this projectile might trigger or transform into an `acidburst.xml` projectile.