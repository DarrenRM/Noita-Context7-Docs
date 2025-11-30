---
title: Boss Limbs Physics Configuration
category: entities
---

---

# Boss Limbs Physics Configuration

This document details the configuration for the physics and AI components of boss limbs in Noita, as defined in `boss_limbs_physics.xml`.

## Core Components

### LightComponent
Provides a visual light source for the boss limb.

*   `radius`: The radius of the light's influence.
*   `r`, `g`, `b`: RGB color values for the light.
*   `offset_y`: Vertical offset for the light source.

### PhysicsBodyComponent
Defines the physical properties of the boss limb's body.

*   `allow_sleep`: Whether the body can enter a sleep state to save performance.
*   `angular_damping`: Resistance to rotational movement.
*   `fixed_rotation`: If true, prevents the body from rotating.
*   `linear_damping`: Resistance to linear movement.
*   `on_death_leave_physics_body`: If true, the physics body persists after death.

### PhysicsImageShapeComponent
Defines the collision shape based on an image.

*   `image_file`: Path to the image used for the shape.
*   `centered`: If true, the image is centered for the shape.
*   `material`: The physics material of the shape (e.g., "aluminium").

### PhysicsAIComponent
Controls the AI-driven physics behavior of the boss limb.

*   `target_vec_max_len`: Maximum length of the target vector for movement.
*   `force_coeff`: Coefficient for applying force.
*   `force_balancing_coeff`: Coefficient for balancing forces.
*   `force_max`: Maximum force that can be applied.
*   `torque_coeff`: Coefficient for applying torque.
*   `torque_balancing_coeff`: Coefficient for balancing torques.
*   `torque_max`: Maximum torque that can be applied.
*   `damage_deactivation_probability`: Probability of deactivating due to damage.
*   `damage_deactivation_time_min`, `damage_deactivation_time_max`: Minimum and maximum duration of deactivation after taking damage.

### SpriteComponent
Defines visual sprites for the boss limb.

*   `image_file`: Path to the sprite image or animation XML.
*   `rect_animation`: The name of the rectangle animation to use.

### LuaComponent
Attaches Lua scripts for custom behavior.

*   `script_source_file`: Path to the Lua script.
*   `vm_type`: Type of virtual machine for script execution.
*   `enable_coroutines`: Whether coroutines are enabled.
*   `execute_on_added`: If true, executes the script when the entity is added.
*   `execute_every_n_frame`: How often to execute the script (e.g., -1 for once).
*   `execute_times`: Number of times to execute the script.

### LimbBossComponent
A marker component indicating this entity is a boss limb.

### MaterialInventoryComponent
Manages the materials contained within the entity.

*   `drop_as_item`: If true, materials are dropped as items on death.
*   `on_death_spill`: If true, materials spill out on death.
*   `leak_pressure_min`, `leak_pressure_max`: Pressure range for material leakage.
*   `leak_on_damage_percent`: Percentage of HP loss at which leakage occurs.
*   `b2_force_on_leak`: Force applied when materials leak.
*   `count_per_material_type`: Defines the types and amounts of materials.

## Base Entity Inheritance

This entity inherits properties from `data/entities/base_enemy_robot_boss_limbs.xml`, which provides common attributes for robot boss limbs. Key overridden or configured components include:

### AnimalAIComponent
AI behavior for creatures.

*   `preferred_job`: The AI's preferred task.
*   `creature_detection_range_x`, `creature_detection_range_y`: Range for detecting creatures.
*   `attack_ranged_min_distance`, `attack_ranged_max_distance`: Range for ranged attacks.
*   `food_material`: Material the creature prefers to consume.
*   `needs_food`: Whether the creature requires food.
*   `sense_creatures`: If true, the creature can sense other creatures.
*   `attack_ranged_enabled`: If true, ranged attacks are enabled.
*   `attack_melee_enabled`: If true, melee attacks are enabled.
*   `can_fly`: If true, the creature can fly.
*   `can_walk`: If true, the creature can walk.

### DamageModelComponent
Defines health and damage-related properties.

*   `hp`: Hit points of the entity.
*   `ragdoll_filenames_file`: File containing ragdoll animation names.
*   `fire_probability_of_ignition`: Probability of catching fire.
*   `ragdoll_material`: Material used for the ragdoll.

### SpriteComponent (from base)
Base sprite properties.

*   `image_file`: Default image file.
*   `rect_animation`: Default animation.
*   `next_rect_animation`: Default next animation.
*   `special_scale_x`: Special scaling factor.
*   `has_special_scale`: If true, special scaling is applied.
*   `emissive`: If true, the sprite emits light.
*   `additive`: If true, uses additive blending.
*   `offset_x`, `offset_y`: Offset for the sprite.

### PathFindingComponent
Defines pathfinding capabilities.

*   `can_walk`: If true, can use walking paths.
*   `can_fly`: If true, can use flying paths.

### PathFindingGridMarkerComponent
Marks the entity on the pathfinding grid.

*   `marker_work_flag`: Flag used for pathfinding grid marking.

### GenomeDataComponent
Genetic information for the creature.

*   `herd_id`: Identifier for the creature's herd.
*   `food_chain_rank`: Position in the food chain.
*   `is_predator`: If true, the creature is a predator.

### CharacterPlatformingComponent
Controls character movement and platforming.

*   `jump_velocity_y`: Vertical velocity for jumping.
*   `run_velocity`: Horizontal movement speed.
*   `fly_speed_max_up`, `fly_speed_max_down`: Maximum vertical flight speeds.
*   `fly_speed_mult`: Multiplier for flight speed.
*   `fly_speed_change_spd`: Speed at which flight speed changes.
*   `fly_velocity_x`: Horizontal flight speed.

### HitboxComponent
Defines the entity's collision hitbox.

*   `aabb_min_x`, `aabb_max_x`: Minimum and maximum X-axis bounds.
*   `aabb_min_y`, `aabb_max_y`: Minimum and maximum Y-axis bounds.

### CameraBoundComponent
Manages how the entity interacts with the camera.

*   `max_count`: Maximum number of entities of this type within the camera's view.
*   `distance`: Distance threshold for camera interaction.

## Embedded Entities

The boss limb entity also embeds multiple instances of `data/entities/animals/boss_limbs/limb.xml`, suggesting it is composed of several smaller limb components.