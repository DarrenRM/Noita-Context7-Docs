---
title: Base Laser Particle Emitter Configuration
category: entities
---

# Base Laser Particle Emitter Configuration

This document details the particle emitter components used in the `base_laser.xml` entity, focusing on their configuration for AI-assisted modding.

## Entity Overview

The `base_laser.xml` entity primarily defines visual effects associated with a laser, likely a wand or spell component. It utilizes two distinct particle emitters to achieve its visual appearance.

## Key Components

### SpriteParticleEmitterComponent

This component is responsible for emitting sprite-based particles, contributing to a "shine" effect.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Indicates the emitter is active when the item is held or identified.
*   **`sprite_file`**: `data/particles/shine_green.xml` - Specifies the sprite to be used for the emitted particles.
*   **`delay`**: `0` - No initial delay before emission starts.
*   **`lifetime`**: `0` - Particles have no inherent lifetime from this component.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 1` - Sets the initial color to white with full opacity.
*   **`angular_velocity`**: `4` - Particles rotate at a constant rate.
*   **`scale.x`, `scale.y`**: `1, 1` - Initial scale of the particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `24`, `34` - Controls the frame rate at which particles are emitted.
*   **`count_min`, `count_max`**: `1`, `1` - Emits a single particle per emission cycle.
*   **`randomize_rotation.min`, `randomize_rotation.max`**: `-3.1415`, `3.1415` - Particles are emitted with a random rotation between -π and +π radians.
*   **`randomize_position.min_x`, `randomize_position.max_x`**: `-2`, `2` - Particles are emitted within a horizontal range of -2 to 2 units from the emitter's origin.
*   **`randomize_position.min_y`, `randomize_position.max_y`**: `-2`, `2` - Particles are emitted within a vertical range of -2 to 2 units from the emitter's origin.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`**: `-24`, `24` - Particles are emitted with a random horizontal velocity between -24 and 24 units/second.
*   **`randomize_velocity.min_y`, `randomize_velocity.max_y`**: `-24`, `24` - Particles are emitted with a random vertical velocity between -24 and 24 units/second.

### ParticleEmitterComponent

This component emits material-based particles, likely representing sparks or energy.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Indicates the emitter is active when the item is held or identified.
*   **`emitted_material_name`**: `spark_green` - Specifies the material of the emitted particles.
*   **`offset.x`, `offset.y`**: `0`, `0` - The emitter is centered at the entity's origin.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-3`, `3` - Particles are emitted within a horizontal offset range of -3 to 3 units.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `1`, `-1` - Particles are emitted within a vertical offset range of 1 to -1 units.
*   **`x_vel_min`, `x_vel_max`**: `-10`, `10` - Particles have a random horizontal velocity between -10 and 10 units/second.
*   **`y_vel_min`, `y_vel_max`**: `-20`, `-10` - Particles have a random vertical velocity between -20 and -10 units/second (suggesting an upward or slightly downward trajectory).
*   **`count_min`, `count_max`**: `1`, `1` - Emits a single particle per emission cycle.
*   **`lifetime_min`, `lifetime_max`**: `0.4`, `0.5` - Particles exist for a duration between 0.4 and 0.5 seconds.
*   **`create_real_particles`**: `0` - These are cosmetic particles, not physical entities.
*   **`emit_cosmetic_particles`**: `1` - Explicitly enables cosmetic particle emission.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `30`, `42` - Controls the frame rate at which particles are emitted.
*   **`is_emitting`**: `1` - The emitter is active.