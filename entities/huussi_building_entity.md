---
title: Huussi Building Entity
category: entities
---

# Huussi Building Entity

This document describes the `huussi.xml` entity, representing a "Huussi" building in Noita. This entity is primarily characterized by its ability to emit "poo" particles when certain conditions are met and its interaction with a specific material for activation.

## Key Components and Attributes

### ParticleEmitterComponent

This component governs the emission of particles from the Huussi.

*   **`_tags="enabled_by_liquid"`**: The particle emission is triggered by the presence of a liquid.
*   **`emitted_material_name="poo"`**: The material emitted is "poo".
*   **`gravity.y="0.0"`**: Particles have no vertical gravity.
*   **`lifetime_min="3"`, `lifetime_max="4"`**: Particles exist for 3 to 4 frames.
*   **`x_vel_min="-16"`, `x_vel_max="16"`**: Horizontal velocity ranges from -16 to 16.
*   **`y_vel_min="-32"`, `y_vel_max="4"`**: Vertical velocity ranges from -32 to 4.
*   **`count_min="1"`, `count_max="1"`**: One particle is emitted per emission event.
*   **`emission_interval_min_frames="12"`, `emission_interval_max_frames="12"`**: Particles are emitted every 12 frames.
*   **`area_circle_radius.min="0"`, `area_circle_radius.max="3"`**: Particles are emitted within a circular area with a radius between 0 and 3.
*   **`cosmetic_force_create="1"`**: Particles are created with a cosmetic effect.
*   **`collide_with_grid="1"`**: Particles can collide with the game grid.
*   **`airflow_force="0.051"`, `airflow_time="1.01"`, `airflow_scale="0.03"`**: These attributes influence how particles interact with airflow.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.

### MaterialAreaCheckerComponent

This component checks for the presence of a specific material within a defined area.

*   **`area_aabb.min_x="-2"`, `area_aabb.max_x="2"`**: Defines the horizontal bounds of the checking area.
*   **`area_aabb.min_y="20"`, `area_aabb.max_y="24"`**: Defines the vertical bounds of the checking area.
*   **`update_every_x_frame="60"`**: The check is performed every 60 frames.
*   **`material="wood_player_b2"`**: The component looks for the "wood\_player\_b2" material.
*   **`look_for_failure="1"`**: The component is designed to detect when the specified material is *not* present.
*   **`kill_after_message="1"`**: If the material is not found (failure detected), the entity will be killed.

### LuaComponent

This component links the `MaterialAreaCheckerComponent`'s failure state to a Lua script.

*   **`script_material_area_checker_failed="data/scripts/buildings/huussi.lua"`**: When the `MaterialAreaCheckerComponent` detects a failure (i.e., "wood\_player\_b2" is not found in the specified area), the script `data/scripts/buildings/huussi.lua` is executed. This script likely handles the consequence of the material being absent, which, based on `kill_after_message="1"`, is the destruction of the Huussi.

---

**Summary:** The Huussi building is a functional entity that emits "poo" particles. Its primary behavior is tied to the presence of "wood\_player\_b2" material within a specific vertical zone above it. If this material is absent, the Huussi is destroyed, as managed by a Lua script. The particle emission itself is enabled by the presence of liquid.