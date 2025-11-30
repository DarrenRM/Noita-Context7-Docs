---
title: Teleportitis Dodge Perk Visuals and Logic
category: entities
---

# Teleportitis Dodge Perk Visuals and Logic

This entity defines the visual effects and underlying logic for the "Teleportitis Dodge" perk in Noita. It primarily consists of particle emitters for visual flair and a Lua script to handle the perk's functionality.

## Core Components

### InheritTransformComponent

This component is used to inherit the transform properties from its parent entity.

*   **`use_root_parent="1"`**: Indicates that the transform should be inherited from the root parent.
*   **`Transform`**: Defines the relative position of this component.
    *   **`position.x="0"`**: No horizontal offset.
    *   **`position.y="-4"`**: A slight vertical offset upwards.

### ParticleEmitterComponent (x2)

These components are responsible for generating the visual effects associated with the Teleportitis Dodge perk. Both emitters use the same material and have similar properties, differing mainly in their emission count and radius.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_tags`                   | `teleportitis_dodge_vfx` - Identifies these as visual effects for the perk. |
| `emitted_material_name`   | `spark_purple` - The material used for the emitted particles.               |
| `gravity.y`               | `0.0` - Particles are not affected by gravity.                              |
| `lifetime_min`            | `0.06` - Minimum particle lifetime in seconds.                              |
| `lifetime_max`            | `0.12` - Maximum particle lifetime in seconds.                              |
| `count_min`               | Minimum number of particles emitted per burst.                              |
| `count_max`               | Maximum number of particles emitted per burst.                              |
| `render_on_grid`          | `1` - Particles are rendered on the game grid.                              |
| `fade_based_on_lifetime`  | `1` - Particles fade out as their lifetime decreases.                       |
| `area_circle_radius.min`  | Minimum radius of the emission area.                                        |
| `area_circle_radius.max`  | Maximum radius of the emission area.                                        |
| `cosmetic_force_create`   | `0` - Not a forced cosmetic particle.                                       |
| `airflow_force`           | `0.3` - Force applied to particles by airflow.                              |
| `airflow_time`            | `0.01` - Duration of airflow effect.                                        |
| `airflow_scale`           | `0.05` - Scale of the airflow effect.                                       |
| `emission_interval_min_frames` | `0` - No delay between emissions.                                           |
| `emission_interval_max_frames` | `0` - No delay between emissions.                                           |
| `emit_cosmetic_particles` | `1` - Emits cosmetic particles.                                             |
| `is_emitting`             | `1` - The emitter is active.                                                |

**Emitter 1:**
*   `count_min`: `30`
*   `count_max`: `50`
*   `area_circle_radius.min`: `20`
*   `area_circle_radius.max`: `20`

**Emitter 2:**
*   `count_min`: `15`
*   `count_max`: `25`
*   `area_circle_radius.min`: `17`
*   `area_circle_radius.max`: `17`

### LuaComponent

This component links the entity to its functional script.

*   **`script_source_file`**: `data/scripts/perks/teleportitis_dodge.lua` - The path to the Lua script that handles the perk's logic.
*   **`execute_every_n_frame`**: `1` - The script will execute every frame.