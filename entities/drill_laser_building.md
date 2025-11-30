---
title: Drill Laser Building
category: entities
---

# Drill Laser Building

This document describes the `drill_laser.xml` entity, which defines a building that uses multiple laser emitters to drill through terrain.

## Core Components

The Drill Laser building is composed of several key components that manage its functionality:

### ElectricityReceiverComponent

*   **`offset_x`, `offset_y`**: Defines the position of the electricity receiver relative to the building's origin.
*   **`radius`**: The detection radius for receiving electricity.
*   **`active_time_frames`**: The duration (in frames) the building remains active after receiving a sufficient electrical charge.

### MaterialAreaCheckerComponent

This component is used twice to detect specific materials in its vicinity.

*   **`update_every_x_frame`**: How often the component checks for materials.
*   **`area_aabb.min_x`, `area_aabb.max_x`, `area_aabb.min_y`, `area_aabb.max_y`**: Defines the bounding box for the material detection area.
*   **`material`**: The primary material to look for (e.g., "oil").
*   **`material2`**: A secondary material to look for (e.g., "liquid_fire_weak").
*   **`look_for_failure`**:
    *   `1`: Triggers a "failure" event if the specified materials are *not* found.
    *   `0`: Triggers a "success" event if the specified materials *are* found.
*   **`kill_after_message`**: If set to `1`, the entity is destroyed after a failure message is triggered.

### VariableStorageComponent

*   **`name="is_fueled"`**: A boolean variable indicating if the drill laser is currently fueled.
*   **`value_bool="1"`**: Sets the initial state of `is_fueled` to true.

### LuaComponent

*   **`script_electricity_receiver_switched`**: Path to the Lua script executed when the electricity receiver's state changes.
*   **`script_material_area_checker_failed`**: Path to the Lua script executed when the `MaterialAreaCheckerComponent` detects a failure condition.
*   **`script_material_area_checker_success`**: Path to the Lua script executed when the `MaterialAreaCheckerComponent` detects a success condition.

### ParticleEmitterComponent

This component is responsible for emitting cosmetic particles, likely for visual feedback.

*   **`_tags="igniter"`**: Tags the emitted particles as igniters.
*   **`_enabled="0"`**: The particle emitter is initially disabled.
*   **`emitted_material_name="liquid_fire_weak"`**: The type of material particles to emit.
*   **`gravity.y="20.0"`**: The gravitational pull on the emitted particles.
*   **`lifetime_min`, `lifetime_max`**: The minimum and maximum lifespan of emitted particles.
*   **`x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`**: Offsets for particle emission position.
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: Velocity ranges for emitted particles.
*   **`count_min`, `count_max`**: The number of particles emitted per emission cycle.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="0"`**: Particles do not fade based on their remaining lifetime.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The minimum and maximum frames between particle emissions.
*   **`create_real_particles="1"`**: Creates actual game particles.
*   **`emit_cosmetic_particles="0"`**: Does not emit purely cosmetic particles.
*   **`is_emitting="1"`**: The particle emitter is set to emit.

## Laser Emitters (x7)

The building contains seven identical `Entity` blocks, each representing a single laser emitter.

### InheritTransformComponent

*   **`Transform position.x`, `position.y`**: Defines the specific position of each laser emitter relative to the main building entity. These values are offset to create a spread of lasers.

### LaserEmitterComponent

*   **`is_emitting="0"`**: Each laser emitter is initially set to not emit. This is likely controlled by the Lua scripts.
*   **`laser_angle_add_rad="1.57079632"`**: Adds a fixed angle (90 degrees in radians) to the laser's direction.

#### Laser Properties

*   **`max_cell_durability_to_destroy`**: The maximum durability a cell must have to be destroyed by the laser.
*   **`max_length`**: The maximum range of the laser beam.
*   **`beam_radius`**: The width of the laser beam.
*   **`damage_to_cells`**: The amount of damage the laser inflicts on terrain cells.
*   **`damage_to_entities`**: The amount of damage the laser inflicts on other entities.

### SpriteComponent

*   **`_tags="laser_fx"`**: Tags the sprite for laser effects.
*   **`_enabled="0"`**: The laser sprite is initially disabled.
*   **`image_file`**: Specifies the graphical asset for the laser effect.
*   **`additive="1"`**: Enables additive blending for the sprite.
*   **`emissive="1"`**: Makes the sprite emissive, contributing to lighting.

---