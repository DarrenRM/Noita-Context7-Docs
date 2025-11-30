---
title: Generic Boss Limb Entity
category: entities
---

# Generic Boss Limb Entity

This entity defines a generic limb for a boss enemy. It serves as a base for more specific boss limb implementations, inheriting common behaviors and properties.

## Key Components

### LightComponent
Provides a visual glow effect for the boss limb.

*   `radius`: The radius of the light effect.
*   `r`, `g`, `b`: RGB color values for the light.
*   `offset_y`: Vertical offset for the light source.

### SpriteComponent
Defines the visual appearance of the boss limb. Multiple `SpriteComponent`s are used to layer different visual elements.

*   `image_file`: Path to the sprite image or XML definition.
*   `rect_animation`: The name of the animation to use (e.g., "stand").
*   `offset_y`, `offset_x`: Offsets for positioning the sprite.

### LuaComponent
Attaches a Lua script to the entity for custom behavior and logic.

*   `script_source_file`: Path to the Lua script.
*   `vm_type`: Specifies the virtual machine type.
*   `enable_coroutines`: Enables coroutine support.
*   `execute_on_added`: Whether to execute the script when the entity is added.
*   `execute_every_n_frame`: How often to execute the script (e.g., -1 for once).
*   `execute_times`: Number of times to execute the script.

### LimbBossComponent
A marker component indicating this entity is a boss limb.

### Base Entity Inheritance
This entity inherits from several base files to define its core functionality.

#### `data/entities/animals/boss_limbs/limb.xml`
Inherits basic limb properties. Multiple instances of this base are included, suggesting a modular limb structure.

#### `data/entities/base_enemy_robot_boss_limbs.xml`
Inherits common properties for robot boss limbs.

##### AnimalAIComponent
Controls the AI behavior of the boss limb.

*   `preferred_job`: The AI's preferred job.
*   `creature_detection_range_x`, `creature_detection_range_y`: Range for detecting creatures.
*   `attack_ranged_min_distance`, `attack_ranged_max_distance`: Range for ranged attacks.
*   `food_material`: The material the creature consumes.
*   `needs_food`: Whether the creature requires food.
*   `sense_creatures`: Whether the creature can sense other creatures.
*   `attack_ranged_enabled`: Whether ranged attacks are enabled.
*   `attack_melee_enabled`: Whether melee attacks are enabled.
*   `can_fly`: Whether the creature can fly.
*   `can_walk`: Whether the creature can walk.

##### DamageModelComponent
Defines the damage and health properties of the boss limb.

*   `hp`: Hit points of the limb.
*   `ragdoll_filenames_file`: File containing ragdoll animation names.
*   `fire_probability_of_ignition`: Probability of catching fire.
*   `ragdoll_material`: Material used for ragdoll physics.

##### SpriteComponent (Inherited)
Defines the default sprite properties inherited from the base.

*   `image_file`: Default sprite image.
*   `rect_animation`: Default animation.
*   `next_rect_animation`: Default next animation.
*   `special_scale_x`: Special scaling factor.
*   `has_special_scale`: Whether special scaling is enabled.
*   `emissive`: Whether the sprite is emissive.
*   `additive`: Whether additive blending is used.
*   `offset_x`, `offset_y`: Default sprite offsets.

##### PathFindingComponent
Defines how the entity navigates the game world.

*   `can_jump`: Whether the entity can jump.
*   `can_walk`: Whether the entity can walk.
*   `can_fly`: Whether the entity can fly.

##### PathFindingGridMarkerComponent
Marks the entity on the pathfinding grid.

*   `marker_work_flag`: The flag used for pathfinding.

##### GenomeDataComponent
Contains genetic information for the creature.

*   `herd_id`: The ID of the creature's herd.
*   `food_chain_rank`: The creature's rank in the food chain.
*   `is_predator`: Whether the creature is a predator.

##### CharacterPlatformingComponent
Controls the character's movement, including jumping and flying.

*   `jump_velocity_y`: Vertical velocity for jumping.
*   `run_velocity`: Horizontal movement speed.
*   `fly_speed_max_up`, `fly_speed_max_down`: Maximum vertical flying speeds.
*   `fly_speed_mult`: Multiplier for flying speed.
*   `fly_speed_change_spd`: Speed at which flying speed changes.
*   `fly_velocity_x`: Horizontal flying speed.

##### HitboxComponent
Defines the collision hitbox for the entity.

*   `aabb_min_x`, `aabb_max_x`: Minimum and maximum X coordinates of the bounding box.
*   `aabb_min_y`, `aabb_max_y`: Minimum and maximum Y coordinates of the bounding box.

##### CharacterDataComponent
General character data, including collision bounds.

*   `collision_aabb_min_x`, `collision_aabb_max_x`: Minimum and maximum X coordinates for collision.
*   `collision_aabb_min_y`, `collision_aabb_max_y`: Minimum and maximum Y coordinates for collision.

##### CameraBoundComponent
Manages the entity's visibility and interaction with the camera.

*   `max_count`: Maximum number of entities of this type that can be active.
*   `distance`: The distance at which the entity becomes relevant to the camera.