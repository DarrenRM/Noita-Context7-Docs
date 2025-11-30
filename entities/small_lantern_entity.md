---
title: Small Lantern Entity
category: entities
---

# Small Lantern Entity

This document details the configuration of a small lantern entity in Noita, focusing on its physical properties, visual representation, and interactive behaviors for AI-assisted modding.

## Core Components

The lantern is defined by several key components that dictate its behavior and appearance.

### PhysicsBody2Component
Manages the physical properties of the lantern.

| Attribute        | Description                                     |
| :--------------- | :---------------------------------------------- |
| `allow_sleep`    | Allows the body to enter a sleep state.         |
| `angular_damping`| Resistance to rotational movement.              |
| `linear_damping` | Resistance to linear movement.                  |
| `init_offset_x`  | Initial offset from the entity's origin (X).    |
| `init_offset_y`  | Initial offset from the entity's origin (Y).    |
| `root_offset_x`  | Offset for the root of the physics body (X).    |
| `root_offset_y`  | Offset for the root of the physics body (Y).    |

### PhysicsImageShapeComponent
Defines the visual shape and material of the lantern.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `body_id`   | The ID of the physics body this shape belongs to. |
| `image_file`| Path to the sprite image for the lantern.       |
| `material`  | The physics material (e.g., `glass_box2d`).     |
| `is_root`   | Indicates if this is the root shape.            |

### PhysicsJoint2Component
Attaches the lantern to nearby surfaces.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `type`              | Joint type: `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`. |
| `break_force`       | The force at which the joint breaks.            |
| `break_on_body_modified` | Whether the joint breaks if the body is modified. |
| `offset_x`          | Offset for the joint attachment point (X).      |
| `offset_y`          | Offset for the joint attachment point (Y).      |
| `body1_id`          | The ID of the physics body to attach.           |

### LightComponent
Provides illumination.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `radius`  | The radius of the light emitted.                |

### MaterialInventoryComponent
Manages the materials contained within the lantern.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `drop_as_item`          | Whether the contents drop as items on death.    |
| `on_death_spill`        | Whether contents spill out on death.            |
| `leak_on_damage_percent`| Percentage of damage at which leaks occur.      |

#### `count_per_material_type`
Specifies the materials and their quantities.

| Material | Count |
| :------- | :---- |
| `oil`    | 4     |

### DamageModelComponent
Handles damage and health.

| Attribute                   | Description                                     |
| :-------------------------- | :---------------------------------------------- |
| `air_needed`                | Whether air is required for this entity.        |
| `blood_material`            | Material spilled when damaged (e.g., `oil`).    |
| `falling_damage_damage_max` | Maximum damage from falling.                    |
| `falling_damage_height_max` | Maximum height for falling damage.              |
| `fire_damage_amount`        | Amount of damage from fire.                     |
| `hp`                        | Health points of the lantern.                   |
| `critical_damage_resistance`| Resistance to critical damage.                  |

### ExplodeOnDamageComponent
Enables the lantern to explode under certain conditions.

| Attribute                       | Description                                     |
| :------------------------------ | :---------------------------------------------- |
| `explode_on_death_percent`      | Percentage of health to trigger explosion on death. |
| `explode_on_damage_percent`     | Percentage of damage to trigger explosion.      |
| `physics_body_modified_death_probability` | Probability of explosion if physics body is modified. |
| `physics_body_destruction_required` | Threshold for physics body destruction to trigger explosion. |

#### `config_explosion`
Configuration for the explosion effect.

| Attribute               | Description                                     |
| :---------------------- | :---------------------------------------------- |
| `damage`                | Damage dealt by the explosion.                  |
| `camera_shake`          | Intensity of camera shake.                      |
| `explosion_radius`      | Radius of the explosion.                        |
| `explosion_sprite`      | Path to the explosion particle effect sprite.   |
| `create_cell_probability`| Probability of creating new cells.              |
| `hole_enabled`          | Whether the explosion creates holes.            |
| `ray_energy`            | Energy of the explosion rays.                   |
| `damage_mortals`        | Whether the explosion damages mortals.          |
| `physics_explosion_power.min` | Minimum physics force of the explosion.         |
| `physics_explosion_power.max` | Maximum physics force of the explosion.         |
| `sparks_enabled`        | Whether sparks are generated.                   |
| `stains_enabled`        | Whether stains are left by the explosion.       |

### PhysicsBodyCollisionDamageComponent
Applies damage based on collision speed.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `speed_threshold` | The speed at which collision damage is applied. |

### SpriteComponent
Defines the visual sprite for the lantern's flame.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `image_file`| Path to the sprite image for the flame.         |
| `offset_x`  | Offset for the sprite (X).                      |
| `offset_y`  | Offset for the sprite (Y).                      |
| `z_index`   | Rendering layer for the sprite.                 |

### TorchComponent
Enables torch-like behavior.

This component simply marks the entity as a torch.

### LuaComponent
Attaches custom Lua scripts for advanced behavior.

| Attribute                   | Description                                     |
| :-------------------------- | :---------------------------------------------- |
| `script_physics_body_modified` | Script executed when the physics body is modified. |
| `script_death`              | Script executed when the entity dies.           |

### AudioComponent
Manages sound effects.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `file`      | Path to the audio bank file.                    |
| `event_root`| The root event name for sounds.                 |