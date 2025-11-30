---
title: Big Firebug Entity
category: entities
---

# Big Firebug Entity

This document details the `bigfirebug.xml` entity, a flying enemy in Noita.

## Core Components

### Base Enemy Flying (`Base file="data/entities/base_enemy_flying.xml"`)

This is the primary component defining the Big Firebug's behavior and attributes.

#### AnimalAIComponent

*   **`attack_ranged_frames_between`**: `40` - Time in frames between ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/fireball_bigfirebug.xml` - The projectile fired during ranged attacks.
*   **`attack_ranged_enabled`**: `1` - Enables ranged attacks.
*   **`attack_ranged_offset_x`**: `5` - Horizontal offset for the ranged attack origin.
*   **`attack_ranged_offset_y`**: `-3` - Vertical offset for the ranged attack origin.
*   **`attack_ranged_action_frame`**: `3` - The frame within the attack animation when the projectile is fired.
*   **`attack_dash_enabled`**: `1` - Enables dashing attacks.
*   **`creature_detection_range_x`**: `300` - Horizontal range for detecting creatures.
*   **`creature_detection_range_y`**: `300` - Vertical range for detecting creatures.
*   **`attack_ranged_max_distance`**: `200` - Maximum distance for ranged attacks.
*   **`can_fly`**: `1` - Allows the creature to fly.
*   **`max_distance_to_move_from_home`**: `256` - Maximum distance the creature will wander from its spawn point.
*   **`needs_food`**: `0` - The creature does not require food.

#### DamageModelComponent

*   **`hp`**: `1` - The creature's health points.
*   **`materials_that_damage`**: `acid,water,poison,blood_cold,blood_cold_vapour,mud,water_swamp,water_salt,swamp,snow,water_ice` - A list of materials that inflict damage to the Big Firebug.
*   **`materials_how_much_damage`**: `0.004,0.005,0.001,0.0008,0.0007,0.005,0.005,0.005,0.005,0.005,0.005` - Corresponding damage values for each material in `materials_that_damage`.
*   **`fire_probability_of_ignition`**: `0` - The probability of igniting from fire.
*   **`ragdoll_filenames_file`**: `data/ragdolls/bigfirebug/filenames.txt` - Specifies the file containing ragdoll bone names.
*   **`ragdoll_material`**: `lavarock_static` - The material used for the ragdoll.
*   **`blood_material`**: `lava` - The material of the blood.
*   **`blood_spray_material`**: `lava` - The material of the blood spray.
*   **`blood_sprite_directional`**: `data/particles/bloodsplatters/bloodsplatter_directional_orange_$[1-3].xml` - Sprite for directional blood splatters.
*   **`blood_sprite_large`**: `data/particles/bloodsplatters/bloodsplatter_orange_$[1-3].xml` - Sprite for large blood splatters.
*   **`wet_status_effect_damage`**: `0.05` - Damage taken when in a wet status effect.
*   **`blood_multiplier`**: `0.8` - Multiplier for blood effects.

#### PathFindingComponent

*   **`can_fly`**: `1` - The creature can fly.
*   **`can_walk`**: `0` - The creature cannot walk.

#### SpriteComponent

*   **`image_file`**: `data/enemies_gfx/bigfirebug.xml` - The primary sprite sheet for the creature.
*   **`offset_x`**: `0` - Horizontal offset for the sprite.
*   **`offset_y`**: `0` - Vertical offset for the sprite.

#### GenomeDataComponent

*   **`herd_id`**: `fly` - Identifier for the creature's herd.
*   **`food_chain_rank`**: `10` - Its position in the food chain.
*   **`is_predator`**: `1` - Indicates it is a predator.

#### HitboxComponent

*   **`aabb_min_x`**: `-7` - Minimum X-axis bounding box coordinate.
*   **`aabb_max_x`**: `7` - Maximum X-axis bounding box coordinate.
*   **`aabb_min_y`**: `-9` - Minimum Y-axis bounding box coordinate.
*   **`aabb_max_y`**: `0` - Maximum Y-axis bounding box coordinate.
*   **`is_enemy`**: `1` - This hitbox belongs to an enemy.
*   **`is_item`**: `0` - Not an item.
*   **`is_player`**: `0` - Not the player.

#### CharacterDataComponent

*   **`climb_over_y`**: `4` - The Y-axis height the character can climb over.
*   **`collision_aabb_min_x`**: `-4.6` - Minimum X-axis collision box coordinate.
*   **`collision_aabb_max_x`**: `4.6` - Maximum X-axis collision box coordinate.
*   **`collision_aabb_min_y`**: `-10` - Minimum Y-axis collision box coordinate.
*   **`collision_aabb_max_y`**: `0` - Maximum Y-axis collision box coordinate.
*   **`mass`**: `0.8` - The mass of the character.

### ParticleEmitterComponent

This component handles the emission of particles, likely for visual effects.

*   **`emitted_material_name`**: `flame` - The material of the emitted particles.
*   **`offset.x`**: `0` - X-axis offset for particle emission.
*   **`offset.y`**: `0` - Y-axis offset for particle emission.
*   **`x_pos_offset_min`**: `-2` - Minimum X-position variation for emitted particles.
*   **`y_pos_offset_min`**: `-2` - Minimum Y-position variation for emitted particles.
*   **`x_pos_offset_max`**: `2` - Maximum X-position variation for emitted particles.
*   **`y_pos_offset_max`**: `2` - Maximum Y-position variation for emitted particles.
*   **`x_vel_min`**: `-10` - Minimum X-velocity for emitted particles.
*   **`x_vel_max`**: `10` - Maximum X-velocity for emitted particles.
*   **`y_vel_min`**: `-10` - Minimum Y-velocity for emitted particles.
*   **`y_vel_max`**: `10` - Maximum Y-velocity for emitted particles.
*   **`count_min`**: `1` - Minimum number of particles emitted per burst.
*   **`count_max`**: `2` - Maximum number of particles emitted per burst.
*   **`lifetime_min`**: `0.6` - Minimum lifetime of emitted particles in seconds.
*   **`lifetime_max`**: `1.8` - Maximum lifetime of emitted particles in seconds.
*   **`create_real_particles`**: `1` - Creates actual game particles.
*   **`emit_cosmetic_particles`**: `0` - Does not emit cosmetic particles.
*   **`emission_interval_min_frames`**: `5` - Minimum frames between emission bursts.
*   **`emission_interval_max_frames`**: `15` - Maximum frames between emission bursts.
*   **`is_emitting`**: `1` - The particle emitter is active.

### LightComponent

This component adds a light source to the entity.

*   **`r`**: `30` - Red component of the light color.
*   **`g`**: `60` - Green component of the light color.
*   **`b`**: `20` - Blue component of the light color.
*   **`radius`**: `48` - The radius of the light.

### SpriteComponent (Emissive)

This component defines the emissive sprite for the Big Firebug.

*   **`_tags`**: `character` - Tag associated with this sprite.
*   **`alpha`**: `1` - Full opacity.
*   **`image_file`**: `data/enemies_gfx/bigfirebug_emissive.xml` - The emissive sprite sheet.
*   **`offset_x`**: `0` - Horizontal offset.
*   **`offset_y`**: `0` - Vertical offset.
*   **`emissive`**: `1` - This sprite is emissive.
*   **`additive`**: `1` - Uses additive blending for emissive effects.
*   **`rect_animation`**: `walk` - The default animation to play.

### AudioComponent

Handles general sound effects for the Big Firebug.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank file.
*   **`event_root`**: `animals/bigfirebug` - The root event for Big Firebug sounds.

### AudioLoopComponent

Manages looping sound effects, specifically wing flaps.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank file.
*   **`event_name`**: `animals/wing_flap_insect/movement_loop` - The name of the looping sound event.
*   **`set_speed_parameter`**: `1` - Allows the sound speed to be controlled by game parameters.
*   **`auto_play`**: `1` - The sound starts playing automatically.