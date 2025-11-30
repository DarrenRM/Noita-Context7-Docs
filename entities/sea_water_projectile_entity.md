---
title: Sea Water Projectile Entity
category: entities
---

# Sea Water Projectile Entity

This document describes the `sea_water.xml` entity, which defines the behavior and appearance of the "sea water" projectile in Noita. This entity is primarily used for visual effects and material spawning.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
    <!-- Components go here -->
</Entity>
```

*   **`name`**: `$projectile_default` - This is a placeholder name, indicating it's a default projectile type.
*   **`tags`**: `projectile_player` - This tag signifies that this projectile is associated with the player.

## Key Components

This entity utilizes several components to achieve its functionality.

### MaterialSeaSpawnerComponent

This component is responsible for spawning the "sea water" material.

```xml
<MaterialSeaSpawnerComponent
    size.x="300"
    size.y="256"
    offset.x="0"
    offset.y="158"
    speed="10"
    noise_threshold="0.0"
    material="water" >
</MaterialSeaSpawnerComponent>
```

*   **`size.x`**: `300` - The width of the area where the material can spawn.
*   **`size.y`**: `256` - The height of the area where the material can spawn.
*   **`offset.x`**: `0` - Horizontal offset for the spawning area.
*   **`offset.y`**: `158` - Vertical offset for the spawning area.
*   **`speed`**: `10` - The speed at which the spawned material moves or behaves.
*   **`noise_threshold`**: `0.0` - Controls the influence of noise on spawning.
*   **`material`**: `water` - Specifies the material to be spawned.

### LifetimeComponent

Determines how long the entity persists.

```xml
<LifetimeComponent
    lifetime="300">
</LifetimeComponent>
```

*   **`lifetime`**: `300` - The entity will exist for 300 frames.

### ParticleEmitterComponent

This component handles the visual particle effects associated with the sea water.

```xml
<ParticleEmitterComponent
    emitted_material_name="water"
    gravity.y="0.0"
    lifetime_min="6"
    lifetime_max="8"
    count_min="8"
    count_max="8"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.min="0"
    area_circle_radius.max="0"
    cosmetic_force_create="0"
    airflow_force="0.51"
    airflow_time="1.01"
    airflow_scale="0.05"
    x_pos_offset_min="0"
    x_pos_offset_max="0"
    y_pos_offset_min="0"
    y_pos_offset_max="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    emit_cosmetic_particles="1"
    image_animation_file="data/particles/image_emitters/sea_water.png"
    image_animation_speed="5"
    image_animation_loop="0"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `water` - The material of the particles being emitted.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to the particles.
*   **`lifetime_min`**: `6` - Minimum lifetime of emitted particles in frames.
*   **`lifetime_max`**: `8` - Maximum lifetime of emitted particles in frames.
*   **`count_min`**: `8` - Minimum number of particles emitted per emission.
*   **`count_max`**: `8` - Maximum number of particles emitted per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`airflow_force`**: `0.51` - Controls the force of airflow on particles.
*   **`image_animation_file`**: `data/particles/image_emitters/sea_water.png` - Specifies the sprite sheet for particle animation.
*   **`image_animation_speed`**: `5` - Speed of the particle image animation.
*   **`is_emitting`**: `1` - The particle emitter is active.

### MusicEnergyAffectorComponent

This component influences some form of "music energy" related to the entity.

```xml
<MusicEnergyAffectorComponent
    energy_target="1.0">
</MusicEnergyAffectorComponent>
```

*   **`energy_target`**: `1.0` - The target value for the music energy.

### AudioComponent

Defines the sound effects associated with the entity.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/sea_of_water"
    set_latest_event_position="1" >
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/sea_of_water` - The specific sound event to trigger.
*   **`set_latest_event_position`**: `1` - Ensures the sound event is positioned correctly in the game world.