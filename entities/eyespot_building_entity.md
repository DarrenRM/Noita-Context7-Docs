---
title: Eyespot Building Entity
category: entities
---

---

# Eyespot Building Entity

This document describes the `eyespot_e.xml` entity, which represents an "Eyespot" building in Noita. This entity is primarily responsible for emitting cosmetic particles and executing Lua scripts for game logic.

## Key Components

### ParticleEmitterComponent

This component handles the visual effects of the Eyespot, emitting cosmetic particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_tags`                   | `magic_eye` - Identifies this as a magic eye entity.                        |
| `emitted_material_name`   | `material_rainbow` - Specifies the material of the emitted particles.       |
| `gravity.y`               | `0.0` - Particles are not affected by gravity.                              |
| `lifetime_min`/`max`      | `0.5` / `1` - Duration of emitted particles in seconds.                     |
| `count_min`/`max`         | `1` / `1` - Number of particles emitted per emission.                       |
| `render_on_grid`          | `1` - Particles are rendered on the game grid.                              |
| `fade_based_on_lifetime`  | `1` - Particles fade out as their lifetime decreases.                       |
| `cosmetic_force_create`   | `1` - Ensures particles are created even if other conditions aren't met.    |
| `emission_interval_min_frames`/`max_frames` | `1` / `1` - Particles are emitted every frame. |
| `emit_cosmetic_particles` | `1` - Explicitly states that cosmetic particles are emitted.                |
| `image_animation_file`    | `data/particles/image_emitters/shroom.png` - Texture file for particle animation. |
| `image_animation_speed`   | `5` - Speed of the particle image animation.                                |
| `image_animation_loop`    | `1` - The particle animation will loop.                                     |
| `is_emitting`             | `1` - The particle emitter is active.                                       |
| `render_back`             | `1` - Particles are rendered behind other game elements.                    |

### VariableStorageComponent

This component stores a string variable associated with the Eyespot.

| Attribute      | Description                                     |
| :------------- | :---------------------------------------------- |
| `_tags`        | `eyespot_object` - Tag for this variable storage. |
| `name`         | `eyespot_object` - The name of the variable.    |
| `value_string` | `book_s_e` - The string value stored.           |

### LuaComponent (Multiple)

These components execute Lua scripts to implement the building's logic.

#### Script 1

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`   | `data/scripts/buildings/eye_check.lua` - The Lua script to execute.         |
| `execute_every_n_frame`| `5` - The script will execute every 5 frames.                               |

#### Script 2

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`   | `data/scripts/buildings/eye_check.lua` - The Lua script to execute.         |
| `execute_on_added`     | `1` - The script will execute once when the entity is added to the game.    |
| `remove_after_executed`| `1` - The Lua component will be removed after its `execute_on_added` script runs. |

#### Script 3

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `_tags`                | `magic_eye` - Tag for this Lua component.                                   |
| `script_source_file`   | `data/scripts/buildings/eyespot_check.lua` - The Lua script to execute.     |
| `execute_every_n_frame`| `5` - The script will execute every 5 frames.                               |