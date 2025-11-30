---
title: Gravity Field Enemy
category: entities
---

# Gravity Field Enemy

This entity defines a gravity field effect, likely used by enemies or environmental hazards. It primarily utilizes particle emitters to create a visual and potentially functional gravity-altering zone.

## Core Components

### LuaComponent

This component links the entity to a Lua script that likely handles the logic and behavior of the gravity field.

*   **`script_source_file`**: `data/scripts/projectiles/projectile_gravity_small.lua` - Specifies the Lua script responsible for the field's functionality.
*   **`execute_every_n_frame`**: `1` - Indicates the script's logic is executed every frame, suggesting real-time updates.

### ParticleEmitterComponent (x2)

Two `ParticleEmitterComponent` instances are used to generate visual effects.

**Emitter 1 (Inner Field):**

*   **`emitted_material_name`**: `spark_purple_bright` - The material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity in the Y-axis.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - Particle lifespan in seconds.
*   **`count_min` / `count_max`**: `2` / `4` - Number of particles emitted per interval.
*   **`area_circle_radius.max`**: `72` - The maximum radius of the emission area.
*   **`airflow_force`**: `0.5` - Controls the force of airflow on particles.
*   **`attractor_force`**: `16` - Particles are attracted towards a central point with this force.

**Emitter 2 (Outer Field):**

*   **`emitted_material_name`**: `spark_purple_bright` - Same material as the inner emitter.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity in the Y-axis.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - Particle lifespan in seconds.
*   **`count_min` / `count_max`**: `10` / `20` - A higher density of particles compared to the inner emitter.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `72` / `72` - The emission area is a precise circle with a radius of 72.
*   **`airflow_force`**: `0.3` - Slightly less airflow force than the inner emitter.

### Base Component (`base_field.xml`)

This entity inherits from `base_field.xml`, suggesting a common structure for field-like entities.

*   **`SpriteComponent`**:
    *   **`image_file`**: `data/particles/area_indicator_072_purple_dark.png` - The visual sprite used to represent the field's area.
    *   **`z_index`**: `1.2` - Controls the rendering order.
    *   **`offset_x` / `offset_y`**: `36` / `36` - Offsets the sprite's position.
*   **`ProjectileComponent`**:
    *   **`config_explosion`**: Defines explosion properties, though likely not directly used by the field itself but inherited.

## Key Attributes Summary

| Component                 | Attribute                 | Value                                     | Description                                                              |
| :------------------------ | :------------------------ | :---------------------------------------- | :----------------------------------------------------------------------- |
| `LuaComponent`            | `script_source_file`      | `data/scripts/projectiles/projectile_gravity_small.lua` | The script governing the gravity field's behavior.                       |
| `ParticleEmitterComponent`| `emitted_material_name`   | `spark_purple_bright`                     | The visual material of the emitted particles.                            |
| `ParticleEmitterComponent`| `area_circle_radius.max`  | `72`                                      | The maximum radius of the particle emission area.                        |
| `ParticleEmitterComponent`| `attractor_force`         | `16`                                      | The force with which particles are attracted towards the field's center. |
| `Base`                    | `SpriteComponent.image_file` | `data/particles/area_indicator_072_purple_dark.png` | The visual representation of the gravity field's area.                   |