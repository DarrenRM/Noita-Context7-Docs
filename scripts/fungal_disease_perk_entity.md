---
title: Fungal Disease Perk Entity
category: data/entities
---

# Fungal Disease Perk Entity

This entity defines the Fungal Disease perk in Noita. It primarily uses Lua scripts to manage its effects and particle emitters for visual feedback.

## Core Components

### LuaComponent (Main Logic)

This component executes the primary script for the Fungal Disease perk.

| Attribute           | Value                                 | Description                                                                 |
| :------------------ | :------------------------------------ | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/perks/fungal_disease.lua` | The main Lua script responsible for the perk's logic and behavior.          |
| `execute_every_n_frame` | `2`                                   | The script is executed every 2 frames, allowing for frequent updates.       |

### LuaComponent (Effect Logic)

This component handles the visual and gameplay effects associated with the disease. It's initially disabled (`_enabled="0"`) and likely activated by the main script.

| Attribute           | Value                                 | Description                                                                 |
| :------------------ | :------------------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`          | `0`                                   | The effect is disabled by default.                                          |
| `_tags`             | `fungal_disease`                      | A tag used for identifying and potentially targeting this effect.           |
| `script_source_file`| `data/scripts/perks/fungal_disease_effect.lua` | The Lua script responsible for the visual and gameplay effects.             |
| `execute_every_n_frame` | `15`                                  | The effect script is executed every 15 frames.                              |

### ParticleEmitterComponent (Cosmetic Sparks)

This component emits cosmetic purple sparks, likely to indicate the presence or activation of the disease. It's also initially disabled.

| Attribute           | Value                                 | Description                                                                 |
| :------------------ | :------------------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`          | `0`                                   | The particle emitter is disabled by default.                                |
| `_tags`             | `fungal_disease`                      | A tag for identifying this specific particle emitter.                       |
| `emitted_material_name` | `spark_purple`                        | The material used for the emitted particles.                                |
| `count_min`/`count_max` | `1`/`3`                               | Emits between 1 and 3 particles per emission.                               |
| `lifetime_min`/`lifetime_max` | `0.8`/`2.0`                           | Particles last between 0.8 and 2.0 seconds.                                 |
| `emission_interval_min_frames`/`emission_interval_max_frames` | `4`/`5`                               | Particles are emitted every 4 to 5 frames.                                  |
| `is_emitting`       | `1`                                   | The emitter is set to emit particles.                                       |

### ParticleEmitterComponent (Fungi Particles)

This component emits "fungi" particles, likely representing the spread or manifestation of the disease. It's also initially disabled.

| Attribute           | Value                                 | Description                                                                 |
| :------------------ | :------------------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`          | `0`                                   | The particle emitter is disabled by default.                                |
| `_tags`             | `fungal_disease`                      | A tag for identifying this specific particle emitter.                       |
| `emitted_material_name` | `fungi`                               | The material used for the emitted particles.                                |
| `count_min`/`count_max` | `1`/`2`                               | Emits between 1 and 2 particles per emission.                               |
| `lifetime_min`/`lifetime_max` | `0.6`/`1.8`                           | Particles last between 0.6 and 1.8 seconds.                                 |
| `create_real_particles` | `1`                                   | These are actual game entities, not just cosmetic effects.                  |
| `emission_interval_min_frames`/`emission_interval_max_frames` | `10`/`35`                               | Particles are emitted every 10 to 35 frames.                                |
| `is_emitting`       | `1`                                   | The emitter is set to emit particles.                                       |

## Key Attributes for Modding

*   **`script_source_file`**: Crucial for understanding and modifying the perk's core logic and effects.
*   **`execute_every_n_frame`**: Determines the frequency of script execution, impacting performance and responsiveness.
*   **`_enabled`**: Controls whether components are active. Modders can toggle these to enable/disable specific effects.
*   **`_tags`**: Useful for targeting specific entities or components within scripts.
*   **`emitted_material_name`**: Defines the visual appearance of particles. Modders can change this to use different materials.
*   **Particle Emitter Parameters**: Attributes like `count`, `lifetime`, `vel_min/max`, and `emission_interval` offer fine-grained control over particle behavior and appearance.