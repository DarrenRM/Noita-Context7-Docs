---
title: Laser Gate (Right) Entity
category: data
---

---

# Laser Gate (Right) Entity

This document describes the `lasergate_right.xml` entity, which represents a right-facing laser gate in Noita. This entity is a building that emits a continuous laser beam.

## Key Components

### SpriteComponent
Handles the visual representation of the laser gate.

*   `image_file`: Specifies the sprite sheet used for the gate's graphics.
*   `special_scale_x`, `has_special_scale`: Controls scaling of the sprite.
*   `offset_x`, `offset_y`: Adjusts the sprite's position.

### SpriteAnimatorComponent
Manages animations for the sprite. (No specific parameters shown, implies default behavior).

### CameraBoundComponent
Determines when the entity is relevant to the camera.

*   `max_count`: Maximum number of this entity type to be active.
*   `distance`: The maximum distance from the camera for the entity to be considered.

### LuaComponent
Attaches Lua scripting to the entity for its behavior.

*   `script_source_file`: The path to the Lua script that controls the entity's logic.
*   `execute_every_n_frame`: How often the script's logic is executed.

### LightComponent
Adds a light source to the entity.

*   `_enabled`: Whether the light is active.
*   `radius`: The range of the light.
*   `fade_out_time`: How long the light takes to fade.
*   `r`, `g`, `b`: The color of the light (RGB values).

### LaserEmitterComponent
Manages the laser beam emission.

*   `is_emitting`: Whether the laser is currently active.
*   `laser_angle_add_rad`: An offset to the laser's angle.

#### Laser Properties (within LaserEmitterComponent)
Defines the characteristics of the emitted laser beam.

*   `damage_to_entities`: Damage dealt to entities hit by the laser.
*   `max_cell_durability_to_destroy`: How much durability a cell must have to be destroyed by the laser.
*   `damage_to_cells`: Damage dealt to environmental cells.
*   `max_length`: The maximum range of the laser beam.
*   `beam_radius`: The thickness of the laser beam.
*   `hit_particle_chance`: Probability of spawning particles when the laser hits something.
*   `beam_particle_chance`: Probability of spawning particles along the beam.
*   `beam_particle_type`: The type of particle to spawn.
*   `audio_enabled`: Whether sound effects are played for the laser.