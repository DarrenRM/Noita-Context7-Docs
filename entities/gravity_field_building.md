---
title: Gravity Field Building
category: entities
---

# Gravity Field Building

This entity defines a building that creates a localized gravity field, attracting nearby particles.

## Core Components

### LuaComponent
This component links the building to its scripting logic.

*   **script_source_file**: `data/scripts/buildings/gravity_field.lua` - Specifies the Lua script that controls the building's behavior.
*   **execute_every_n_frame**: `1` - The script logic runs every frame.

### LightComponent
This component provides visual feedback for the gravity field.

*   **radius**: `96` - The radius of the light effect.
*   **r, g, b**: `200, 200, 200` - Sets the light color to white.
*   **fade_out_time**: `0.2` - How long the light takes to fade out.

### ParticleEmitterComponent (Attracted Particles)
This emitter is responsible for generating particles that are drawn towards the center of the gravity field.

*   **emitted_material_name**: `spark_white` - The material of the particles emitted.
*   **gravity.y**: `0.0` - Particles are not affected by global gravity.
*   **lifetime_min, lifetime_max**: `0.5` to `1.0` - Duration each particle exists.
*   **count_min, count_max**: `1` to `3` - Number of particles emitted per interval.
*   **area_circle_radius.max**: `48` - The maximum radius from the emitter center where particles can be generated.
*   **airflow_force**: `0.5` - Controls the strength of airflow effects on particles.
*   **attractor_force**: `12` - The strength of the gravity field's pull on these particles.

### ParticleEmitterComponent (Outer Ring)
This emitter creates a visual ring of particles around the gravity field.

*   **emitted_material_name**: `spark_white` - The material of the particles emitted.
*   **gravity.y**: `0.0` - Particles are not affected by global gravity.
*   **lifetime_min, lifetime_max**: `0.2` to `0.8` - Duration each particle exists.
*   **count_min, count_max**: `5` to `10` - Number of particles emitted per interval.
*   **area_circle_radius.min, area_circle_radius.max**: `48` - Particles are emitted specifically at a radius of 48 from the emitter center, forming a ring.
*   **airflow_force**: `0.3` - Controls the strength of airflow effects on particles.