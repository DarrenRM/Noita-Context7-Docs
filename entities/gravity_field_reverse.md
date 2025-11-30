---
title: Gravity Field Reverse
category: entities
---

# Gravity Field Reverse

This entity defines a biome modifier that creates a reverse gravity field, pushing objects and particles upwards.

## Core Components

### LuaComponent
This component links the entity to the `gravity_field.lua` script, which handles the logic for the gravity effect.

*   **script_source_file**: `data/scripts/buildings/gravity_field.lua` - The script responsible for the gravity field's behavior.
*   **execute_every_n_frame**: `1` - The script logic is executed every frame.

### LightComponent
This component provides a visual indicator for the gravity field.

*   **radius**: `96` - The radius of the light effect.
*   **r, g, b**: `255, 20, 20` - Sets the light color to a reddish hue.
*   **fade_out_time**: `0.2` - How long the light takes to fade out.

### ParticleEmitterComponent (Attracted Particles)
This emitter generates particles that are affected by the reverse gravity.

*   **emitted_material_name**: `spark_red` - The material of the particles being emitted.
*   **gravity.y**: `0.0` - Particles have no inherent vertical gravity.
*   **lifetime_min/max**: `0.5` to `1.0` - Duration of particle existence.
*   **count_min/max**: `1` to `3` - Number of particles emitted per interval.
*   **area_circle_radius.max**: `12` - The maximum radius of the emission area.
*   **velocity_always_away_from_center**: `30` - Particles are strongly pushed away from the center.
*   **friction**: `-2` - Negative friction to simulate upward acceleration.
*   **airflow_force/time/scale**: Controls how particles are affected by air currents.
*   **emission_interval_min/max_frames**: `1` - Particles are emitted continuously.
*   **is_emitting**: `1` - The emitter is active.

### ParticleEmitterComponent (Outer Ring)
This emitter creates a ring of particles around the gravity field's edge.

*   **emitted_material_name**: `spark_red` - The material of the particles being emitted.
*   **gravity.y**: `0.0` - Particles have no inherent vertical gravity.
*   **lifetime_min/max**: `0.2` to `0.8` - Duration of particle existence.
*   **count_min/max**: `5` to `10` - Number of particles emitted per interval.
*   **area_circle_radius.min/max**: `48` - Particles are emitted in a ring at this radius.
*   **airflow_force/time/scale**: Controls how particles are affected by air currents.
*   **emission_interval_min/max_frames**: `1` - Particles are emitted continuously.
*   **is_emitting**: `1` - The emitter is active.

## Key Attributes Summary

| Attribute                       | Value                               | Description                                                                 |
| :------------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `tags`                          | `gravity_field_reverse`             | Identifies the entity as a reverse gravity field.                           |
| `LuaComponent.script_source_file` | `data/scripts/buildings/gravity_field.lua` | Links to the core logic script.                                             |
| `LightComponent.radius`         | `96`                                | Visual range of the gravity field's light.                                  |
| `LightComponent.r, g, b`        | `255, 20, 20`                       | Reddish color for the light.                                                |
| `ParticleEmitterComponent.velocity_always_away_from_center` | `30` | Strong outward force on emitted particles.                                  |
| `ParticleEmitterComponent.friction` | `-2` | Negative friction to simulate upward acceleration.                          |
| `ParticleEmitterComponent.area_circle_radius.max` (inner) | `12` | Emission area for particles near the center.                                |
| `ParticleEmitterComponent.area_circle_radius.min/max` (outer) | `48` | Emission radius for the outer ring of particles.                            |
| `ParticleEmitterComponent.is_emitting` | `1` | Ensures particles are continuously generated.                               |