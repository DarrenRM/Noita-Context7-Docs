---
title: Base Music Machine
category: entities
---

# Base Music Machine

This document details the `base_music_machine.xml` entity, which serves as a foundational component for various music-playing machines in Noita. It defines the core properties, physics, damage handling, and particle effects associated with these entities.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the music machine.

| Attribute         | Description                                      |
| :---------------- | :----------------------------------------------- |
| `allow_sleep`     | Whether the entity can enter a sleep state.      |
| `angular_damping` | Resistance to rotational movement.               |
| `linear_damping`  | Resistance to linear movement.                   |
| `kill_entity_after_initialized` | If the entity should be removed after initialization. |

### PhysicsImageShapeComponent
Defines the visual representation and collision shape.

| Attribute   | Description                                      |
| :---------- | :----------------------------------------------- |
| `is_root`   | Marks this as the root visual element.           |
| `centered`  | Centers the image on its origin.                 |
| `image_file`| Path to the sprite image for the machine.        |
| `material`  | The physics material defining its interaction.   |

### DamageModelComponent
Handles how the entity takes damage and its health.

| Attribute                   | Description                                                              |
| :-------------------------- | :----------------------------------------------------------------------- |
| `hp`                        | The entity's hit points.                                                 |
| `fire_damage_amount`        | The amount of damage taken from fire per tick.                           |
| `materials_that_damage`     | List of materials that inflict damage upon contact.                      |
| `materials_how_much_damage` | Corresponding damage values for each material in `materials_that_damage`. |
| `critical_damage_resistance`| Multiplier for critical damage taken.                                    |

#### Damage Multipliers
Specific multipliers for different damage types.

| Attribute   | Description                                      |
| :---------- | :----------------------------------------------- |
| `melee`     | Multiplier for melee damage.                     |
| `electricity`| Multiplier for electricity damage.               |

### ExplodeOnDamageComponent
Determines if and how the entity explodes when damaged or destroyed.

| Attribute                       | Description                                                              |
| :------------------------------ | :----------------------------------------------------------------------- |
| `explode_on_death_percent`      | Probability of exploding upon death (1.0 = always).                      |
| `physics_body_destruction_required` | The percentage of physics body destruction required to trigger an explosion. |

#### Config Explosion
Detailed configuration for the explosion effect.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `damage`              | The damage dealt by the explosion.                                       |
| `camera_shake`        | Intensity of camera shake caused by the explosion.                       |
| `explosion_radius`    | The radius of the explosion's effect.                                    |
| `explosion_sprite`    | Path to the sprite used for the explosion visual.                        |
| `hole_enabled`        | Whether the explosion creates holes in the environment.                  |
| `ray_energy`          | Energy value for physics-based explosion forces.                         |
| `physics_explosion_power.min` | Minimum physics force applied to entities by the explosion.              |
| `physics_explosion_power.max` | Maximum physics force applied to entities by the explosion.              |
| `stains_radius`       | Radius of stains left by the explosion.                                  |
| `delay.min`           | Minimum delay before the explosion occurs.                               |
| `delay.max`           | Maximum delay before the explosion occurs.                               |

### ParticleEmitterComponent
Defines a particle emitter for general effects.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `emitted_material_name` | The material of the particles being emitted.                             |
| `x_pos_offset_min`    | Minimum X offset for particle emission.                                  |
| `y_pos_offset_max`    | Maximum Y offset for particle emission.                                  |
| `x_vel_min`           | Minimum X velocity for emitted particles.                                |
| `y_vel_max`           | Maximum Y velocity for emitted particles.                                |
| `gravity.y`           | The Y-axis gravity applied to particles.                                 |
| `count_min`           | Minimum number of particles emitted per burst.                           |
| `lifetime_min`        | Minimum lifetime of emitted particles.                                   |
| `airflow_force`       | Force applied by airflow to particles.                                   |

### SpriteParticleEmitterComponent
Defines a particle emitter using sprites for more complex visual effects.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `sprite_file`         | Path to the sprite file for the particles.                               |
| `lifetime`            | Lifetime of the emitted sprite particles.                                |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of the particles.                          |
| `color_change.a`      | Rate of alpha change for the particles.                                  |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                           |
| `randomize_rotation.min` | Minimum random rotation applied to particles.                            |
| `randomize_position.min_x` | Minimum random X position offset for particles.                          |
| `randomize_velocity.min_y` | Minimum random Y velocity for particles.                                 |
| `entity_velocity_multiplier` | Multiplier for the entity's velocity applied to particle velocity.       |

### LuaComponent
Attaches Lua scripts to the entity for custom behavior.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `script_kick`       | Script executed for a "kick" event (e.g., starting music).               |
| `script_source_file`| Path to the Lua script file.                                             |
| `script_audio_event_dead` | Script executed when the entity's audio event is considered "dead".      |
| `execute_on_added`  | If the script should execute immediately when the entity is added.       |
| `execute_every_n_frame` | If the script should execute every N frames.                             |

### AudioComponent
Manages the audio playback for the entity.

| Attribute                     | Description                                                              |
| :---------------------------- | :----------------------------------------------------------------------- |
| `file`                        | Path to the audio bank file.                                             |
| `event_root`                  | The root event name within the audio bank.                               |
| `set_latest_event_position`   | If the latest event's position should be set to this entity's position.  |
| `remove_latest_event_on_destroyed` | If the latest event should be removed when the entity is destroyed.      |
| `send_message_on_event_dead`  | If a message should be sent when the audio event finishes or is stopped. |