---
title: Phantom B (Enemy)
category: entities
---

# Phantom B (Enemy)

This document details the configuration of the "Phantom B" enemy entity in Noita, focusing on its AI, combat, and visual properties.

## Core Components

### Base Entity

The Phantom B inherits its core functionality from `data/entities/base_enemy_flying.xml`.

### AnimalAIComponent

This component governs the creature's behavior, including its combat capabilities and sensory perception.

*   **`preferred_job`**: `JobDefault` - Indicates its default AI behavior.
*   **`escape_if_damaged_probability`**: `35` - Has a 35% chance to attempt to flee when damaged.
*   **`attack_ranged_min_distance`**: `0` - Can attack at any range.
*   **`attack_melee_damage_min`**: `0.6` - Minimum melee damage.
*   **`attack_melee_damage_max`**: `0.8` - Maximum melee damage.
*   **`attack_dash_enabled`**: `0` - Cannot perform a dash attack.
*   **`attack_melee_enabled`**: `1` - Can perform melee attacks.
*   **`attack_melee_action_frame`**: `3` - The frame at which the melee attack is executed.
*   **`creature_detection_range_x`**: `250` - Horizontal range for detecting creatures.
*   **`creature_detection_range_y`**: `250` - Vertical range for detecting creatures.
*   **`food_material`**: `meat` - Its preferred food source (though it doesn't need food).
*   **`needs_food`**: `0` - Does not require food to survive.
*   **`sense_creatures`**: `1` - Actively senses other creatures.
*   **`attack_ranged_enabled`**: `1` - Can perform ranged attacks.
*   **`can_fly`**: `1` - Capable of flight.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/orbspawner_green.xml` - The projectile entity used for ranged attacks.
*   **`attack_ranged_frames_between`**: `250` - Delay in frames between ranged attacks.
*   **`attack_landing_ranged_enabled`**: `1` - Can perform ranged attacks while landing.
*   **`attack_ranged_action_frame`**: `4` - The frame at which the ranged attack is executed.

### DamageModelComponent

Defines the entity's health and how it takes damage.

*   **`hp`**: `3` - Has 3 hit points.
*   **`physics_objects_damage`**: `0` - Does not deal damage to physics objects.
*   **`ragdoll_filenames_file`**: `""` - No specific ragdoll files.
*   **`fire_probability_of_ignition`**: `0` - Cannot be ignited by fire.
*   **`ragdoll_material`**: `rock_static_glow` - The material used for its ragdoll effect.
*   **`blood_material`**: `plasma_fading` - The material for its blood.
*   **`blood_spray_material`**: `plasma_fading` - The material for its blood spray.
*   **`air_needed`**: `0` - Does not require air.

#### Damage Multipliers

*   **`projectile`**: `0.5` - Takes half damage from projectiles.
*   **`explosion`**: `0.4` - Takes 40% damage from explosions.
*   **`electricity`**: `1` - Takes normal damage from electricity.
*   **`fire`**: `0` - Immune to fire damage.
*   **`slice`**: `1` - Takes normal damage from slicing.
*   **`holy`**: `1.2` - Takes 20% more damage from holy sources.

### SpriteComponent

Controls the visual appearance of the Phantom B.

*   **`image_file`**: `data/enemies_gfx/phantom_b.xml` - Specifies the sprite sheet.
*   **`additive`**: `1` - Uses additive blending for rendering.
*   **`emissive`**: `1` - The sprite is emissive, meaning it glows.

### PathFindingComponent

Determines how the entity navigates the game world.

*   **`can_swim_on_surface`**: `1` - Can swim on the surface of liquids.
*   **`frames_to_get_stuck`**: `20` - Will attempt to escape if stuck for 20 frames.
*   **`can_fly`**: `1` - Capable of flight.
*   **`can_jump`**: `0` - Cannot jump.

### GenomeDataComponent

Provides genetic information for creature interactions and AI.

*   **`herd_id`**: `ghost` - Identifies it as part of the "ghost" herd.
*   **`food_chain_rank`**: `15` - Its position in the food chain.
*   **`is_predator`**: `1` - It is a predator.

### CharacterPlatformingComponent

Defines movement parameters for characters.

*   **`pixel_gravity`**: `600` - The gravity applied to the entity.
*   **`jump_velocity_y`**: `-12` - The vertical velocity applied when jumping (though it cannot jump).
*   **`run_velocity`**: `14` - Its movement speed.

### HitboxComponent

Defines the collision boundaries of the entity.

*   **`aabb_min_x`**: `-4.5`
*   **`aabb_max_x`**: `4.5`
*   **`aabb_min_y`**: `-14`
*   **`aabb_max_y`**: `3`

### CharacterDataComponent

General character data, including collision and mass.

*   **`collision_aabb_min_x`**: `-2`
*   **`collision_aabb_max_x`**: `2`
*   **`collision_aabb_min_y`**: `-14`
*   **`collision_aabb_max_y`**: `2`
*   **`mass`**: `1.0`

### AudioComponent

Manages sound effects for the entity.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank file.
*   **`event_root`**: `animals/ghost` - The root event name for ghost sounds.

## Additional Components

### ItemPickUpperComponent

*   **`is_in_npc`**: `1` - Indicates it can pick up items as if it were an NPC.

### AudioLoopComponent

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_name`**: `animals/wizard/movement_loop` - Plays a looping movement sound.
*   **`set_speed_parameter`**: `1` - The loop speed is tied to its movement speed.
*   **`auto_play`**: `1` - The sound plays automatically.

### Entity (GameEffectComponent)

This nested entity applies a game effect to the Phantom B.

*   **`effect`**: `PROTECTION_FREEZE` - Grants immunity to freezing.
*   **`frames`**: `-1` - The effect is permanent.