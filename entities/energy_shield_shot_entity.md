---
title: Energy Shield Shot Entity
category: entities
---

# Energy Shield Shot Entity

This entity defines the behavior and appearance of the Energy Shield projectile in Noita. It primarily utilizes components for energy management, particle effects, lighting, and audio.

## Key Components and Attributes

### `EnergyShieldComponent`

Manages the shield's energy, recharge rate, and its physical properties like radius and sector.

*   **`recharge_speed`**: How quickly the shield regenerates energy.
*   **`max_energy`**: The maximum energy capacity of the shield.
*   **`energy`**: The current energy level of the shield.
*   **`radius`**: The effective radius of the shield.
*   **`sector_degrees`**: The angular coverage of the shield in degrees.

### `ParticleEmitterComponent`

This component is used multiple times to create various visual effects associated with the shield.

#### Primary Emission (Shield Aura)

*   **`_tags`**: `character,enabled_in_hand,item_identified__LEGACY`
*   **`emitted_material_name`**: `plasma_fading` - The material used for the particles.
*   **`area_circle_sector_degrees`**: `90` - Limits particle emission to a sector.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to particles.
*   **`lifetime_min` / `lifetime_max`**: Controls how long particles last.
*   **`count_min` / `count_max`**: The number of particles emitted per interval.
*   **`area_circle_radius.max`**: `8` - The maximum radius for particle emission.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the frequency of particle emission.
*   **`is_emitting`**: `1` - Indicates that this emitter is active.

#### Ring Emission (Shield Edge)

*   **`_tags`**: `character,enabled_in_hand,item_identified__LEGACY,shield_ring`
*   **`emitted_material_name`**: `plasma_fading`
*   **`area_circle_sector_degrees`**: `90`
*   **`lifetime_min` / `lifetime_max`**: `0.01` - Very short lifetime for ring particles.
*   **`count_min` / `count_max`**: `1` - Emits a single particle.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `8` - Particles are emitted precisely at the shield's radius.
*   **`airflow_scale`**: `0.05` - Subtle airflow effect.
*   **`is_emitting`**: `1` - Active emitter.

#### Hit Emission (Impact Effect)

*   **`_tags`**: `character,enabled_in_hand,item_identified__LEGACY,shield_hit`
*   **`emitted_material_name`**: `plasma_fading`
*   **`area_circle_sector_degrees`**: `90`
*   **`lifetime_min` / `lifetime_max`**: `0.3` to `1` - Longer lasting particles for impact.
*   **`count_min` / `count_max`**: `300` to `360` - A large burst of particles on impact.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `8` - Impact occurs at the shield's radius.
*   **`airflow_force`**: `2.8` - Strong airflow to disperse particles.
*   **`is_emitting`**: `0` - This emitter is typically triggered by an event, not continuously active.

### `LightComponent`

Adds a light source to the entity, illuminating the surroundings.

*   **`radius`**: `80` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: Color values for the light (a bluish hue).

### `AudioComponent`

Defines the sound effects associated with the shield.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/shield` - The specific sound event to play.

### `LifetimeComponent`

Determines how long the entity exists.

*   **`lifetime`**: `200` - Base duration in frames.
*   **`randomize_lifetime.min` / `randomize_lifetime.max`**: Adds variation to the entity's lifespan.