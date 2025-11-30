---
title: Parallel Tentacles Entity
category: entities
---

---

# Parallel Tentacles Entity

This document details the configuration for the "Parallel Tentacles" entity in Noita, primarily focusing on its AI, physics, and damage properties for modding purposes.

## Core Attributes

*   **`name`**: `$animal_parallel_tentacles` - The internal identifier for this entity.
*   **`tags`**: `enemy, mortal, human, hittable, homing_target, teleportable_NOT, touchmagic_immunity, polymorphable_NOT, glue_NOT` - Defines its behavior and interactions within the game. Notably, it's immune to teleportation, touch magic, polymorphing, and glue.

## Visuals and Lighting

### LightComponent
*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `256` - The radius of the light emitted.
*   **`r`, `g`, `b`**: `100`, `255`, `130` - Defines a greenish-blue light color.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.

### SpriteComponent
*   **`image_file`**: `data/entities/animals/parallel/tentacles/sprite.xml` - Specifies the sprite definition for the entity.

## AI and Behavior

### LimbBossComponent
*   **`state`**: `1` - Indicates the current state of the boss limb.

### VariableStorageComponent
*   **`name="state"`**: `value_int="0"` - Stores the entity's state as an integer.
*   **`name="memory"`**: `value_string="data/entities/projectiles/enlightened_laser_darkbeam.xml"` - Stores a string related to its memory, likely referencing a projectile.

### LuaComponent
These components delegate complex AI logic to external Lua scripts:
*   **`script_source_file="data/entities/animals/boss_pit/boss_pit_logic.lua"`**: Executes general boss logic every 40 frames.
*   **`script_source_file="data/entities/animals/boss_pit/boss_pit_memory.lua"`**: Executes memory-related logic every frame.
*   **`script_damage_received="data/entities/animals/boss_pit/boss_pit_damage.lua"`**: Handles damage reception logic.

### PathFindingComponent
This component governs the entity's movement and pathfinding capabilities:
*   **`can_dive`**: `1` - Can move underwater.
*   **`can_fly`**: `1` - Can fly.
*   **`can_walk`**: `0` - Cannot walk.
*   **`cost_of_flying`**: `500` - High cost associated with flying, suggesting it's not the primary mode of movement.
*   **`initial_jump_max_distance_x`**: `100` - Maximum horizontal jump distance.
*   **`jump_speed`**: `200` - Speed of jumps.
*   **`max_jump_distance_from_camera`**: `400` - Maximum jump distance relative to the camera.

### PathFindingGridMarkerComponent
*   **`marker_offset_y`**: `-6` - Adjusts the marker's vertical position.
*   **`marker_work_flag`**: `16` - A flag used for pathfinding grid operations.

### ParticleEmitterComponent
Two emitters are present, both configured to emit `spark_blue` particles. They differ in lifetime, count, and emission intervals, suggesting different visual effects during gameplay.

## Physics

### PhysicsAIComponent
Controls the physics-based AI of the entity:
*   **`target_vec_max_len`**: `15.0` - Maximum length of the target vector.
*   **`force_coeff`**: `10.0` - Coefficient for applying force.
*   **`torque_coeff`**: `50` - Coefficient for applying torque.
*   **`damage_deactivation_probability`**: `0` - The entity will not deactivate upon taking damage.

### PhysicsBodyComponent
Defines the physical properties of the entity's body:
*   **`angular_damping`**: `0.02` - Slows down rotational movement.
*   **`fixed_rotation`**: `1` - Prevents the entity from rotating freely.

### PhysicsShapeComponent
Defines the collision shape:
*   **`is_circle`**: `1` - The shape is a circle.
*   **`radius_x`, `radius_y`**: `19` - The radius of the circular collision shape.
*   **`restitution`**: `0.3` - Controls how much energy is retained after a collision.

## Damage and Health

### DamageModelComponent
Manages the entity's health and damage interactions:
*   **`hp`**: `32` - The entity's hit points.
*   **`blood_material`**: `slime_green` - The material that appears when the entity is damaged.
*   **`ragdoll_material`**: `rock_static_glow` - The material used for its ragdoll effect.
*   **`ragdollify_child_entity_sprites`**: `1` - Ensures child entities also ragdoll.
*   **`damage_multipliers`**:
    *   `melee`: `1.0`
    *   `projectile`: `0.3` - Takes significantly less damage from projectiles.
    *   `explosion`: `0.3`
    *   `electricity`: `0.3`
    *   `fire`: `0.3`
    *   `ice`: `0.3`
    *   `drill`: `0` - Immune to drill damage.

### GenomeDataComponent
*   **`food_chain_rank`**: `5` - Its position in the game's food chain.
*   **`herd_id`**: `boss_limbs` - Identifies it as part of a boss limb group.
*   **`is_predator`**: `1` - It is a predator.

### HitboxComponent
Defines the area that can inflict damage:
*   **`aabb_max_x`, `aabb_max_y`**: `16`, `12` - Defines the upper bounds of the hitbox.
*   **`aabb_min_x`, `aabb_min_y`**: `-16`, `-12` - Defines the lower bounds of the hitbox.

### CameraBoundComponent
*   **`max_count`**: `20` - Maximum number of this entity that can be active within camera bounds.
*   **`distance`**: `160000` - The distance from the camera within which the entity is considered active.

## Other Components

### AudioComponent
*   **`file`**: `data/audio/Desktop/animals.bank` - Specifies the audio bank.
*   **`event_root`**: `animals` or `animals/boss_limbs` - Defines the root for audio events.

### SpriteAnimatorComponent
Enables sprite animations for the entity.

### CellEaterComponent
*   **`radius`**: `32` - The radius within which the entity can "eat" cells.
*   **`eat_probability`**: `100` - Always attempts to eat cells within its radius.

## Tentacle Structure

The "Parallel Tentacles" entity is composed of multiple individual tentacle entities, each inheriting from `data/entities/animals/parallel/tentacles/tentacle.xml`. Their positions are offset relative to the main entity.

*   **Tentacle 1**: `position.x="-8"`, `position.y="-8"`
*   **Tentacle 2**: `position.x="8"`, `position.y="-8"`
*   **Tentacle 3**: `position.x="4"`, `position.y="-6"`
*   **Tentacle 4**: `position.x="8"`, `position.y="-8"`
*   **Tentacle 5**: `position.x="-4"`, `position.y="2"`
*   **Tentacle 6**: `position.x="0"`, `position.y="4"`

## Protective Effects

Two additional entities are spawned, providing passive protective effects:
*   **Protection Freeze**: Grants immunity to freezing indefinitely (`frames="-1"`).
*   **Protection Electricity**: Grants immunity to electricity indefinitely (`frames="-1"`).