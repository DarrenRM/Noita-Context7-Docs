---
title: Physics Laser Trap
category: entities
---

# Physics Laser Trap

This document details the configuration of a physics-based laser trap entity in Noita, designed to activate and emit a damaging laser when receiving electricity.

## Core Components

### PhysicsBody2Component
Manages the physical properties of the trap.

| Attribute       | Description                                   |
| --------------- | --------------------------------------------- |
| `allow_sleep`   | Whether the body can enter a sleep state.     |
| `angular_damping` | Resistance to rotational movement.            |
| `linear_damping`  | Resistance to linear movement.                |

### PhysicsImageShapeComponent
Defines the visual representation and collision shape of the trap.

| Attribute   | Description                                   |
| ----------- | --------------------------------------------- |
| `is_root`   | Indicates if this is the root shape.          |
| `centered`  | Centers the image on the entity's origin.     |
| `image_file`| Path to the sprite for the trap.              |
| `material`  | The material type for physics interactions.   |

### ElectricityReceiverComponent
Enables the entity to react to electrical input.

| Attribute         | Description                                   |
| ----------------- | --------------------------------------------- |
| `radius`          | The radius within which electricity is detected. |
| `active_time_frames` | Duration (in frames) the trap remains active after receiving electricity. |

## Laser Emitter Configuration

The `Entity name="laser"` block defines the laser projectile itself.

### LaserEmitterComponent
Controls the emission of the laser beam.

| Attribute     | Description                                   |
| ------------- | --------------------------------------------- |
| `is_emitting` | Whether the laser is currently active.        |

### VariableStorageComponent
Stores variables for the laser's behavior.

| Attribute   | Description                                   |
| ----------- | --------------------------------------------- |
| `name`      | Name of the variable.                         |
| `value_int` | Integer value for the variable (e.g., duration). |

### InheritTransformComponent
Allows the laser to inherit the transform of its parent.

| Attribute   | Description                                   |
| ----------- | --------------------------------------------- |
| `position.x`| X-axis offset from the parent entity.         |

## Scripting and Behavior

### LuaComponent
Links the entity to Lua scripts for custom logic.

| Attribute                        | Description                                   |
| -------------------------------- | --------------------------------------------- |
| `script_electricity_receiver_switched` | Script executed when electricity is received and the trap switches state. |
| `script_damage_received`         | Script executed when the trap takes damage.   |

## Particle Effects

The trap utilizes two `ParticleEmitterComponent`s for visual feedback during activation and damage.

### SpriteParticleEmitterComponent (`particles_a`)
Emits cosmetic particles, likely sparks.

| Attribute              | Description                                   |
| ---------------------- | --------------------------------------------- |
| `sprite_file`          | Path to the particle sprite.                  |
| `emission_interval_min_frames` | Minimum frames between particle emissions.    |
| `emission_interval_max_frames` | Maximum frames between particle emissions.    |
| `count_min`            | Minimum number of particles per emission.     |
| `count_max`            | Maximum number of particles per emission.     |
| `randomize_rotation`   | Random rotation range for particles.          |
| `randomize_position`   | Random position offset for particles.         |

### ParticleEmitterComponent (`particles_b`)
Emits more substantial particles, possibly related to the laser's impact or activation.

| Attribute              | Description                                   |
| ---------------------- | --------------------------------------------- |
| `emitted_material_name`| The material of the emitted particles.        |
| `x_vel_min`, `x_vel_max` | Minimum and maximum X velocity of particles.  |
| `y_vel_min`, `y_vel_max` | Minimum and maximum Y velocity of particles.  |
| `lifetime_min`, `lifetime_max` | Minimum and maximum particle lifetime.        |
| `create_real_particles`| Whether to create actual physics particles.   |
| `emit_cosmetic_particles`| Whether to emit cosmetic particles.           |
| `draw_as_long`         | Whether particles are drawn as lines.         |

## Damage and Destruction

### DamageModelComponent
Defines how the trap takes damage and its properties.

| Attribute                 | Description                                   |
| ------------------------- | --------------------------------------------- |
| `hp`                      | Hit points of the trap.                       |
| `materials_that_damage`   | Materials that inflict damage to the trap.    |
| `materials_how_much_damage`| How much damage each material inflicts.       |
| `damage_multipliers`      | Modifiers for different damage types.         |

### ExplodeOnDamageComponent
Configures the trap's explosion behavior upon taking damage or dying.

| Attribute                   | Description                                   |
| --------------------------- | --------------------------------------------- |
| `explode_on_death_percent`  | Probability of exploding upon death.          |
| `explode_on_damage_percent` | Probability of exploding when damaged.        |
| `physics_body_destruction_required` | Threshold for physics body destruction to trigger explosion. |
| `config_explosion`          | Nested configuration for the explosion effect. |

#### `config_explosion` Details:
*   `damage`: Damage dealt by the explosion.
*   `camera_shake`: Intensity of camera shake.
*   `explosion_radius`: Radius of the explosion.
*   `explosion_sprite`: Visual effect for the explosion.
*   `load_this_entity`: Entity to spawn upon explosion (e.g., a projectile).
*   `ray_energy`: Energy of any electrical rays emitted.
*   `physics_explosion_power`: Force of the physics-based explosion.
*   `audio_event_name`: Sound effect for the explosion.