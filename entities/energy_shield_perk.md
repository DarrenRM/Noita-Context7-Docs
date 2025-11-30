---
title: Energy Shield Perk
category: entities
---

# Energy Shield Perk

This document details the configuration for the Energy Shield perk in Noita, focusing on its entity definition and key components.

## Entity Definition

The core entity for the Energy Shield perk.

```xml
<Entity tags="energy_shield">
    <!-- Components defining the shield's behavior and appearance -->
</Entity>
```

## Key Components

### HitboxComponent

Defines the physical collision area of the shield.

```xml
<HitboxComponent
    _tags="enabled_in_world"
    aabb_min_x="-4"
    aabb_max_x="4"
    aabb_min_y="-3"
    aabb_max_y="3">
</HitboxComponent>
```

*   **aabb_min_x, aabb_max_x, aabb_min_y, aabb_max_y**: Define the bounding box of the hitbox.

### InheritTransformComponent

Manages the shield's position relative to the player when held.

```xml
<InheritTransformComponent
    _tags="enabled_in_hand"
    use_root_parent="1">
  <Transform
    position.x="0"
    position.y="-4">
  </Transform>
</InheritTransformComponent>
```

*   **use_root_parent**: Ensures the shield's transform is inherited from its parent entity (the player).
*   **Transform**: Specifies an offset from the parent's origin.

### EnergyShieldComponent

The primary component responsible for the shield's functionality.

```xml
<EnergyShieldComponent
    _tags="enabled_in_hand,item_identified__LEGACY"
    recharge_speed="0.22"
    radius="10.0">
</EnergyShieldComponent>
```

*   **recharge_speed**: Determines how quickly the shield regenerates.
*   **radius**: Sets the effective radius of the shield.

### ParticleEmitterComponent (Multiple Instances)

These components control the visual effects of the shield, including its idle state, activation ring, and impact effects.

#### Idle/Active Particles

Emits fading plasma particles around the shield.

```xml
<ParticleEmitterComponent
    _tags="character,enabled_in_hand,item_identified__LEGACY"
    emitted_material_name="plasma_fading"
    gravity.y="0.0"
    lifetime_min="0.1"
    lifetime_max="0.5"
    count_min="2"
    count_max="4"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.max="10"
    cosmetic_force_create="0"
    airflow_force="0.5"
    airflow_time="0.1"
    airflow_scale="0.5"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    emit_cosmetic_particles="1"
    is_emitting="1">
</ParticleEmitterComponent>
```

*   **emitted_material_name**: The material used for the particles.
*   **area_circle_radius.max**: The maximum radius for particle emission.
*   **is_emitting**: Controls whether particles are actively emitted.

#### Shield Ring Particles

Creates a distinct ring effect, likely on activation or when the shield is active.

```xml
<ParticleEmitterComponent
    _tags="character,enabled_in_hand,item_identified__LEGACY,shield_ring"
    emitted_material_name="plasma_fading"
    gravity.y="0.0"
    lifetime_min="0.02"
    lifetime_max="0.05"
    count_min="90"
    count_max="100"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.min="10"
    area_circle_radius.max="10"
    cosmetic_force_create="0"
    airflow_force="0.3"
    airflow_time="0.01"
    airflow_scale="0.05"
    emission_interval_min_frames="0"
    emission_interval_max_frames="0"
    emit_cosmetic_particles="1"
    is_emitting="1">
</ParticleEmitterComponent>
```

*   **area_circle_radius.min/max**: Defines a precise ring shape for emission.
*   **emission_interval_min/max_frames**: Set to 0 for a continuous burst.

#### Shield Hit Particles

Generates particles upon impact or when the shield is damaged.

```xml
<ParticleEmitterComponent
    _tags="character,enabled_in_hand,item_identified__LEGACY,shield_hit"
    emitted_material_name="plasma_fading"
    gravity.y="0.0"
    lifetime_min="0.3"
    lifetime_max="1"
    count_min="300"
    count_max="360"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.min="10"
    area_circle_radius.max="10"
    cosmetic_force_create="0"
    airflow_force="2.8"
    airflow_time="0.03"
    airflow_scale="0.8"
    emission_interval_min_frames="0"
    emission_interval_max_frames="0"
    emit_cosmetic_particles="1"
    is_emitting="0">
</ParticleEmitterComponent>
```

*   **is_emitting**: Set to `0` by default, indicating it's triggered by an event.
*   **airflow_force/time/scale**: Higher values suggest a more impactful visual effect.

### LightComponent

Adds a light source to the shield, illuminating the surroundings.

```xml
<LightComponent
    _tags="enabled_in_hand,item_identified"
    _enabled="1"
    radius="60"
    fade_out_time="1.5"
    r="150"
    g="190"
    b="230">
</LightComponent>
```

*   **radius**: The range of the light.
*   **fade_out_time**: How long the light takes to fade.
*   **r, g, b**: Color values for the light.

### AudioComponent

Manages the sound effects associated with the shield.

```xml
<AudioComponent
    _tags="enabled_in_hand,item_identified"
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/shield"
    set_latest_event_position="1">
</AudioComponent>
```

*   **file**: Path to the audio bank.
*   **event_root**: The base event name for shield sounds.
*   **set_latest_event_position**: Ensures the sound originates from the shield's position.