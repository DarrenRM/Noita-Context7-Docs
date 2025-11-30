---
title: Radioactive Conversion with Delay
category: entities
---

# Radioactive Conversion with Delay

This entity is a utility designed to trigger the conversion of radioactive materials after a specified delay. It acts as a timed mechanism to initiate a radioactive transformation process.

## Key Components

### LifetimeComponent

*   **lifetime**: `360`
    *   Defines the total duration this entity will exist in frames.

### LoadEntitiesComponent

*   **entity_file**: `data/entities/misc/convert_radioactive.xml`
    *   Specifies the entity file to be loaded and activated. In this case, it's the core radioactive conversion logic.
*   **count.min**: `1`
    *   Minimum number of instances of `convert_radioactive.xml` to load.
*   **count.max**: `1`
    *   Maximum number of instances of `convert_radioactive.xml` to load.
*   **timeout_frames**: `358`
    *   The delay in frames before the `entity_file` is loaded and activated. This is the primary delay mechanism for the radioactive conversion.

### ParticleEmitterComponent

This component adds visual feedback to the entity, emitting green sparks.

*   **emitted_material_name**: `spark_green_bright`
    *   The material used for the emitted particles.
*   **lifetime_min**: `0.3`
    *   Minimum lifetime of emitted particles in seconds.
*   **lifetime_max**: `0.9`
    *   Maximum lifetime of emitted particles in seconds.
*   **count_min**: `2`
    *   Minimum number of particles emitted per emission interval.
*   **count_max**: `4`
    *   Maximum number of particles emitted per emission interval.
*   **area_circle_radius.min**: `0`
    *   Minimum radius of the emission area.
*   **area_circle_radius.max**: `70`
    *   Maximum radius of the emission area.
*   **emission_interval_min_frames**: `1`
    *   Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `14`
    *   Maximum frames between particle emissions.
*   **is_emitting**: `1`
    *   Enables particle emission.