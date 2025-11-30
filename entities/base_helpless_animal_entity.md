---
title: Base Helpless Animal Entity
category: entities
---

---

# Base Helpless Animal Entity

This document describes the base entity for "helpless animals" in Noita, serving as a foundational template for various passive creatures.

## Key Components and Attributes

This entity defines the core behaviors and properties of helpless animals.

### Entity Tags

These tags categorize the entity and determine its fundamental interactions within the game world.

*   `mortal`: The entity can be killed.
*   `hittable`: The entity can be damaged by attacks.
*   `helpless_animal`: Identifies this as a helpless animal type.
*   `homing_target`: Can be targeted by homing projectiles.
*   `teleportable_NOT`: Cannot be teleported.

### AnimalAIComponent

Manages the artificial intelligence and behaviors of the animal.

*   `ai_state`: Current AI state (0 is typically idle/passive).
*   `creature_detection_range_x`, `creature_detection_range_y`: The range at which the animal can detect other creatures.
*   `attack_melee_damage_min`, `attack_melee_damage_max`: Defines the minimum and maximum damage for melee attacks (though often disabled for helpless animals).
*   `food_material`: The material the animal consumes for sustenance.
*   `needs_food`: Whether the animal requires food to survive (set to `0` for many helpless animals).
*   `sense_creatures`: Whether the animal actively senses creatures (set to `0` for passive behavior).
*   `attack_ranged_enabled`, `attack_melee_enabled`: Flags to enable/disable ranged and melee attacks.
*   `aggressiveness_min`, `aggressiveness_max`: Defines the range of aggressiveness.

### PathFindingComponent

Handles the entity's movement and pathfinding capabilities.

*   `search_depth_max_no_goal`, `iterations_max_no_goal`: Parameters for pathfinding when no specific goal is set.
*   `cost_of_flying`: The cost associated with flying during pathfinding.
*   `can_fly`: Whether the entity is capable of flight.
*   `can_jump`: Whether the entity can jump.
*   `jump_trajectories`: Defines specific jump arcs the entity can perform.

### CharacterCollisionComponent

Defines how the entity interacts with physical collisions.

*   `getting_crushed_threshold`: The amount of force required to crush the entity.

### CharacterDataComponent

Contains general character-specific data and physics properties.

*   `gravity`: The gravitational pull affecting the entity (set to `0` for many flying or unique movement types).
*   `buoyancy_check_offset_y`: Offset for buoyancy checks in water.

### GenomeDataComponent

Relates to the entity's genetic properties and role in the ecosystem.

*   `herd_id`: Identifier for the animal's herd or species group.
*   `food_chain_rank`: Its position in the food chain.
*   `is_predator`: Whether the entity is a predator.

### CharacterPlatformingComponent

Manages platforming-related movement, such as running and jumping.

*   `jump_velocity_y`: The vertical velocity applied when jumping.
*   `run_velocity`: The base running speed.
*   `accel_x`: Horizontal acceleration.
*   `velocity_max_x`, `velocity_max_y`: Maximum horizontal and vertical velocities.

### DamageModelComponent

Defines how the entity takes damage and its health properties.

*   `hp`: The entity's hit points.
*   `falling_damages`: Whether the entity takes damage from falling.
*   `materials_damage`: A list of materials that inflict damage upon contact.
*   `materials_that_damage`: Specifies which materials cause damage.
*   `materials_how_much_damage`: The amount of damage inflicted by specific materials.
*   `ragdoll_material`: The material used for the entity's ragdoll when it dies.

### HitboxComponent

Defines the collision boundaries of the entity.

*   `aabb_max_x`, `aabb_max_y`, `aabb_min_x`, `aabb_min_y`: Axis-aligned bounding box coordinates.

### SpriteComponent

Controls the visual representation of the entity.

*   `image_file`: The path to the sprite's image file.
*   `rect_animation`: The name of the default rectangle animation to play.

### LuaComponent

Allows for custom Lua scripting to extend entity behavior.

*   `script_death`: The path to a Lua script executed when the entity dies.