---
title: Poltergeist Physics AI
category: entities
---

# Poltergeist Physics AI

This entity defines the behavior and physics of a "Poltergeist" type entity, primarily focused on its AI and interaction with the environment.

## Core Components

### PhysicsAIComponent
This component governs the physical interactions and AI-driven movement of the entity.

*   **`target_vec_max_len`**: Maximum length of the vector used to guide the entity's movement towards a target.
*   **`force_coeff`**: Coefficient for applying force to move the entity.
*   **`force_balancing_coeff`**: Coefficient for balancing forces to maintain stability.
*   **`force_max`**: Maximum force that can be applied.
*   **`torque_coeff`**: Coefficient for applying rotational force (torque).
*   **`torque_balancing_coeff`**: Coefficient for balancing rotational forces.
*   **`torque_max`**: Maximum torque that can be applied.
*   **`rotation_speed`**: Base speed of rotation.
*   **`damage_deactivation_probability`**: Chance (in percent) for the entity to deactivate upon taking damage.
*   **`damage_deactivation_time_min`**: Minimum duration (in frames) the entity remains deactivated after taking damage.
*   **`damage_deactivation_time_max`**: Maximum duration (in frames) the entity remains deactivated after taking damage.

### AnimalAIComponent
This component defines the creature-like behaviors and senses of the entity.

*   **`_enabled`**: Controls whether this component is active (1 for enabled, 0 for disabled).
*   **`preferred_job`**: The default job assigned to this creature.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: The range (in pixels) within which the entity can detect other creatures.
*   **`sense_creatures`**: Whether the entity actively senses creatures.
*   **`needs_food`**: Whether the entity requires food to survive.
*   **`attack_ranged_enabled`**: Whether ranged attacks are enabled.
*   **`attack_melee_enabled`**: Whether melee attacks are enabled.
*   **`can_fly`**: Whether the entity is capable of flight.
*   **`aggressiveness_min` / `aggressiveness_max`**: The minimum and maximum aggressiveness levels of the entity.
*   **`eye_offset_y`**: Vertical offset for the entity's "eyes" or detection point.

### PathFindingComponent
This component handles the entity's navigation and pathfinding capabilities.

*   **`distance_to_reach_node_x` / `distance_to_reach_node_y`**: The tolerance (in pixels) for reaching a pathfinding node.
*   **`frames_to_get_stuck`**: Number of frames the entity can remain stuck before attempting to re-evaluate its path.
*   **`can_jump`**: Whether the entity can jump.
*   **`can_fly`**: Whether the entity can fly.
*   **`jump_speed`**: The vertical speed applied when jumping.

### CharacterPlatformingComponent
This component defines basic platforming movement characteristics.

*   **`jump_velocity_y`**: The vertical velocity applied when jumping.
*   **`run_velocity`**: The horizontal movement speed.

### GenomeDataComponent
This component provides genetic information, influencing AI and ecological interactions.

*   **`herd_id`**: Identifier for the herd or group this entity belongs to.
*   **`food_chain_rank`**: The entity's position in the food chain.
*   **`is_predator`**: Indicates whether the entity is a predator.

### ParticleEmitterComponent
This component is responsible for emitting particles, likely for visual effects.

*   **`emitted_material_name`**: The name of the material used for the emitted particles (e.g., "spark\_red").
*   **`offset.x` / `offset.y`**: The origin point for particle emission relative to the entity.
*   **`x_pos_offset_min` / `x_pos_offset_max`**: Range for random horizontal position offset of emitted particles.
*   **`y_pos_offset_min` / `y_pos_offset_max`**: Range for random vertical position offset of emitted particles.
*   **`x_vel_min` / `x_vel_max`**: Range for random horizontal velocity of emitted particles.
*   **`y_vel_min` / `y_vel_max`**: Range for random vertical velocity of emitted particles.
*   **`count_min` / `count_max`**: Minimum and maximum number of particles emitted per emission cycle.
*   **`lifetime_min` / `lifetime_max`**: Minimum and maximum lifetime (in seconds) of emitted particles.
*   **`create_real_particles`**: Whether to create actual physics-simulated particles.
*   **`emit_cosmetic_particles`**: Whether to emit purely visual particles.
*   **`fade_based_on_lifetime`**: Whether particles fade out as their lifetime decreases.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Minimum and maximum frames between particle emission cycles.
*   **`is_emitting`**: Controls whether particle emission is currently active.

## Other Components

*   **`PathFindingGridMarkerComponent`**: Marks the entity on the pathfinding grid.
*   **`SpriteAnimatorComponent`**: Handles sprite animations for the entity.