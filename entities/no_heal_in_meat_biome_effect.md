---
title: No Heal in Meat Biome Effect
category: entities
---

# No Heal in Meat Biome Effect

This entity defines a special effect that prevents healing within a specific biome, likely the "Meat Biome". It utilizes several components to achieve this functionality.

## Key Components

### GameEffectComponent

This component applies the core game effect.

*   **`_tags`**: `effect_no_heal_in_meat_biome` - Identifies this specific effect.
*   **`effect`**: `NO_HEAL` - The primary effect applied, which is to disable healing.
*   **`frames`**: `-1` - Indicates the effect is persistent as long as the entity is active.

### ParticleEmitterComponent

This component is responsible for visual feedback, emitting particles when the effect is active.

*   **`_tags`**: `effect_no_heal_in_meat_biome` - Links particles to this effect.
*   **`emitted_material_name`**: `spark_red` - The material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `0.1` / `0.5` - Controls the duration of individual particles.
*   **`count_min` / `count_max`**: `30` / `40` - The number of particles emitted per burst.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `2` / `2` - Defines the emission area.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `60` / `60` - The frequency of particle emissions.
*   **`velocity_always_away_from_center`**: `11` - Particles are pushed outwards from the emission center.

### BiomeTrackerComponent

This component is likely used in conjunction with the `LuaComponent` to detect when the player enters or leaves the target biome.

### LuaComponent

This component executes a Lua script to manage the biome-specific logic.

*   **`script_biome_entered`**: `data/scripts/misc/no_heal_in_meat_biome.lua` - The path to the Lua script that handles the biome entry and effect application.
*   **`execute_every_n_frame`**: `-1` - Suggests the script is triggered by specific events rather than running continuously.

## Entity Structure

The entity is structured with the following components:

*   **`InheritTransformComponent`**: Standard component for transform inheritance.
*   **`GameEffectComponent`**: Applies the `NO_HEAL` effect.
*   **`ParticleEmitterComponent`**: Provides visual cues.
*   **`BiomeTrackerComponent`**: Detects biome changes.
*   **`LuaComponent`**: Executes the script for biome logic.

This setup allows for a dynamic effect that is only active when the player is within the designated "Meat Biome".