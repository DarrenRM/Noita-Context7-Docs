---
title: Physics Fungus Entity
category: entities
---

# Physics Fungus Entity

This document details the `physics_fungus.xml` entity, which represents a physics-enabled, destructible fungus prop in Noita. It's designed to interact with the game's physics engine, break apart, and potentially explode.

## Key Components and Attributes

The `physics_fungus.xml` entity is composed of several key components that define its behavior and appearance.

### `PhysicsBody2Component`

This component defines the fundamental physics properties of the fungus.

*   **`is_static`**: `0` - Indicates the body is not static and can be moved by physics forces.
*   **`allow_sleep`**: `1` - Allows the physics body to enter a sleep state when not in motion, optimizing performance.
*   **`angular_damping`**: `0.01` - Controls the rate at which angular velocity decreases.
*   **`linear_damping`**: `0.5` - Controls the rate at which linear velocity decreases.
*   **`init_offset_y`**: `40` - An initial vertical offset applied to the physics body.

### `PhysicsImageShapeComponent`

Multiple instances of this component define the visual and physical shape of the fungus, broken down into distinct parts (cap, stalk, foot).

*   **`body_id`**: Unique identifier for each shape component.
*   **`is_root`**: `1` for the main cap component, indicating it's the primary part.
*   **`centered`**: `1` - Centers the image around its origin.
*   **`offset_x`, `offset_y`**: Position offsets for each part relative to the entity's origin.
*   **`image_file`**: Path to the sprite used for the shape.
*   **`material`**: `fungus_loose` - The material assigned to the shape, influencing its physical properties.

**Summary of `PhysicsImageShapeComponent` parts:**

| `body_id` | `offset_y` | `image_file`                       | `material`    | Notes                               |
| :-------- | :--------- | :--------------------------------- | :------------ | :---------------------------------- |
| `100`     | `2`        | `data/props_gfx/physics_fungus_cap_01.png` | `fungus_loose`  | Fungus cap                          |
| `101`     | `5`        | `data/props_gfx/physics_fungus_stalk.png`  | `fungus_loose`  | Stalk segment                       |
| `102`     | `11`       | `data/props_gfx/physics_fungus_stalk.png`  | `fungus_loose`  | Stalk segment                       |
| `103`     | `17`       | `data/props_gfx/physics_fungus_stalk.png`  | `fungus_loose`  | Stalk segment                       |
| `104`     | `23`       | `data/props_gfx/physics_fungus_stalk.png`  | `fungus_loose`  | Stalk segment                       |
| `105`     | `29`       | `data/props_gfx/physics_fungus_foot.png`   | `fungus_loose`  | Fungus foot/base                    |

### `PhysicsJoint2Component` and `PhysicsJoint2MutatorComponent`

These components define the connections (joints) between the different parts of the fungus, allowing them to move and break apart realistically.

*   **`PhysicsJoint2MutatorComponent`**: These components appear to control motor-like behavior for the joints, though their `motor_speed` is often set to `0` or `-0`, suggesting they might be for fine-tuning or specific states.
    *   **`joint_id`**: Links to a specific `PhysicsJoint2Component`.
    *   **`motor_speed`**: The target speed for the joint motor.
    *   **`motor_max_torque`**: The maximum torque the motor can apply.

*   **`PhysicsJoint2Component`**: These define the actual physical joints.
    *   **`type`**: `REVOLUTE_JOINT` for segments, `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` for the base attachment.
    *   **`joint_id`**: Identifies the joint.
    *   **`offset_x`, `offset_y`**: Position of the joint relative to the connected bodies.
    *   **`body1_id`, `body2_id`**: The IDs of the physics bodies being connected.
    *   **`break_force`**: The force required to break the joint.
    *   **`break_distance`**: The distance at which the joint breaks.
    *   **`ray_x`, `ray_y`**: Used for surface attachment joints to define the raycast direction.

**Summary of Stalk Joints:**

| `joint_id` | `type`           | `body1_id` | `body2_id` | `break_force` | `break_distance` |
| :--------- | :--------------- | :--------- | :--------- | :------------ | :--------------- |
| `1`        | `REVOLUTE_JOINT` | `100`      | `101`      | `10`          | `5`              |
| `2`        | `REVOLUTE_JOINT` | `101`      | `102`      | `10`          | `5`              |
| `3`        | `REVOLUTE_JOINT` | `102`      | `103`      | `10`          | `5`              |
| `4`        | `REVOLUTE_JOINT` | `103`      | `104`      | `10`          | `5`              |
| `5`        | `REVOLUTE_JOINT` | `104`      | `105`      | `10`          | `5`              |

**Ground Attachment Joint:**

| `joint_id` | `type`                           | `body1_id` | `break_force` | `break_distance` | `ray_x` | `ray_y` |
| :--------- | :------------------------------- | :--------- | :------------ | :--------------- | :------ | :------ |
| N/A        | `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` | `105`      | `35`          | `8`              | `0`     | `30`    |

### `MaterialInventoryComponent`

This component manages the internal material (fungus blood) of the fungus.

*   **`drop_as_item`**: `0` - The fungus does not drop as an item when destroyed.
*   **`on_death_spill`**: `1` - Spills its internal material upon death.
*   **`leak_on_damage_percent`**: `1` - Leaks material when damaged.
*   **`leak_pressure_min`, `leak_pressure_max`**: Defines the pressure range for material leakage.
*   **`b2_force_on_leak`**: The force applied when material leaks.
*   **`kill_when_empty`**: `1` - The entity is destroyed when its internal material is depleted.
*   **`count_per_material_type`**:
    *   **`Material material="blood_fungi" count="900"`**: The fungus contains 900 units of `blood_fungi` material.

### `DamageModelComponent`

Defines how the fungus takes damage and its associated effects.

*   **`hp`**: `0.6` - The fungus has very low health.
*   **`air_needed`**: `0` - Does not require air.
*   **`fire_probability_of_ignition`**: `100` - Highly susceptible to ignition.
*   **`ragdoll_material`**: `fungus_loose_trippy` - Material used for ragdoll effects.
*   **`blood_material`, `blood_spray_material`**: `blood_fungi` - The material that spills and sprays.
*   **`blood_sprite_directional`, `blood_sprite_large`**: Paths to particle effects for blood splatters.
*   **`minimum_knockback_force`**: `100000` - A high value, suggesting it's resistant to being knocked back by small forces.
*   **`damage_multipliers`**:
    *   **`fire="40.0"`**: Takes 40 times more damage from fire.

### `ExplodeOnDamageComponent`

This component enables the fungus to explode under certain conditions.

*   **`explode_on_death_percent`**: `1` - Explodes when it dies.
*   **`explode_on_damage_percent`**: `0.0` - Does not explode solely from taking damage (unless it leads to death).
*   **`physics_body_modified_death_probability`**: `0.9` - High probability of exploding if its physics body is modified upon death.
*   **`physics_body_destruction_required`**: `0.25` - A portion of its physics body needs to be destroyed for explosion chance.
*   **`config_explosion`**: Contains detailed parameters for the explosion effect.
    *   **`camera_shake`**: `40` - Intensity of camera shake.
    *   **`explosion_radius`**: `30` - The radius of the explosion.
    *   **`explosion_sprite`**: Path to the explosion visual effect.
    *   **`load_this_entity`**: The entity to spawn at the explosion's center.
    *   **`create_cell_material`**: `fire` - Creates fire cells.
    *   **`physics_explosion_power`**: `min="0.8" max="1.8"` - The force of the physics-based explosion.
    *   **`spark_material`**: `plasma_fading_pink` - The material for sparks.
    *   **`audio_event_name`**: `explosions/slime` - The sound event for the explosion.

### `LightComponent`

Adds a light source to the entity.

*   **`radius`**: `80` - The radius of the light.
*   **`r`, `g`, `b`**: `32`, `255`, `250` - Defines the light color (a bright greenish-blue).

### `PhysicsBodyCollisionDamageComponent`

Applies damage to the entity when it collides with other objects at a certain speed.

*   **`speed_threshold`**: `75.0` - The speed at which collision damage is applied.

### `LuaComponent`

Links a Lua script to the entity for custom behavior.

*   **`script_source_file`**: `data/scripts/props/physics_fungus.lua` - The path to the associated Lua script.
*   **`execute_every_n_frame`**: `1` - The script executes every frame.

### `VariableStorageComponent`

Stores custom variables for the entity.

*   **`name`**: `lift`
*   **`value_int`**: `-25` - Likely used by the Lua script for some form of lift or buoyancy effect.

### `AudioLoopComponent`

Adds a looping sound effect to the entity.

*   **`file`**: `data/audio/Desktop/materials.bank` - The audio bank containing the sound.
*   **`event_name`**: `materials/spray_fungus` - The specific sound event.
*   **`volume_autofade_speed`**: `0.25` - Controls how quickly the volume fades automatically.