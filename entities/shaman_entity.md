---
title: Shaman Entity
category: entities
---

# Shaman Entity

This document details the Shaman entity, a creature found in Noita. It focuses on its AI behavior, combat capabilities, and visual components.

## Core Attributes

The Shaman is a basic enemy with several key attributes defining its behavior and appearance.

### Base Entity

The Shaman inherits from `data/entities/base_enemy_basic.xml`, providing fundamental enemy functionalities.

### ItemChestComponent

*   `level`: 1 - Indicates the loot tier associated with this enemy.

### AnimalAIComponent

This component governs the Shaman's artificial intelligence and combat actions.

*   `can_fly`: 0 - The Shaman cannot fly.
*   `preferred_job`: `JobDefault` - Its default AI behavior.
*   `escape_if_damaged_probability`: 35 - A 35% chance to flee when damaged.
*   `creature_detection_range_x`, `creature_detection_range_y`: 250 - The range at which it detects other creatures.
*   `sense_creatures`: 1 - It actively senses creatures.
*   `attack_ranged_enabled`: 1 - Ranged attacks are enabled.
*   `attack_ranged_min_distance`: 20 - Minimum distance for ranged attacks.
*   `attack_ranged_max_distance`: 200 - Maximum distance for ranged attacks.
*   `attack_ranged_entity_file`: `data/entities/projectiles/orb_cursed.xml` - The projectile used for ranged attacks.
*   `attack_ranged_entity_count_min`, `attack_ranged_entity_count_max`: 2 - Fires 2 projectiles per attack.
*   `attack_ranged_frames_between`: 150 - Delay between ranged attacks.
*   `attack_ranged_action_frame`: 10 - The frame within the attack animation when the projectile is fired.
*   `attack_ranged_offset_y`: -11 - Vertical offset for projectile firing.
*   `attack_ranged_offset_x`: 8 - Horizontal offset for projectile firing.

### DamageModelComponent

Defines the Shaman's health and how it reacts to damage.

*   `hp`: 5 - The Shaman has 5 hit points.
*   `materials_create_messages`: 1 - Damage creates messages.
*   `ragdoll_material`: `meat` - The material used for its ragdoll.
*   `blood_material`: `water_swamp` - The material of its blood.
*   `blood_multiplier`: 0.3 - Controls blood quantity.
*   `ragdoll_filenames_file`: `data/ragdolls/shaman/filenames.txt` - Specifies ragdoll sprites.
*   `fire_probability_of_ignition`: 0 - Cannot be ignited by fire.
*   `physics_objects_damage`: 1 - Can be damaged by physics objects.

### SpriteComponent

Determines the Shaman's visual appearance.

*   `image_file`: `data/enemies_gfx/shaman.xml` - The primary sprite file.
*   `offset_x`, `offset_y`: 0 - No sprite offset.

### PathFindingComponent

Controls the Shaman's movement and navigation.

*   `can_swim_on_surface`: 1 - Can swim on water surfaces.
*   `can_dive`: 1 - Can dive underwater.
*   `frames_to_get_stuck`: 30 - Time before considering itself stuck.
*   `can_jump`: 1 - Capable of jumping.
*   `jump_speed`: 80 - The speed of its jumps.
*   `initial_jump_max_distance_x`, `initial_jump_max_distance_y`: Defines jump distance.

### GenomeDataComponent

Provides genetic information for AI and world generation.

*   `herd_id`: `mage` - Identifies its group.
*   `food_chain_rank`: 10 - Its position in the food chain.

### CharacterDataComponent

Defines physical properties for collision and interaction.

*   `collision_aabb_min_x`, `collision_aabb_max_x`, `collision_aabb_min_y`, `collision_aabb_max_y`: Defines its collision bounding box.
*   `mass`: 1.0 - Its mass.

### CharacterPlatformingComponent

Governs its platforming abilities.

*   `pixel_gravity`: 600 - The gravity affecting it.
*   `jump_velocity_y`: -20 - The vertical velocity applied when jumping.
*   `run_velocity`: 12 - Its running speed.

### HitboxComponent

Defines the entity's hitbox for interactions.

*   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Defines the hitbox dimensions.
*   `is_enemy`: 1 - It is an enemy.

## Attached Lantern Entity

The Shaman entity includes a child entity representing a lantern attached to its hand.

### InheritTransformComponent

*   `parent_hotspot_tag`: `hand_hotspot` - The lantern's position is inherited from the "hand" hotspot.

### SpriteComponent (Lantern)

*   `image_file`: `data/enemies_gfx/shaman_lantern.png` - The sprite for the lantern.
*   `z_index`: -1.1 - Controls rendering order.

### SpriteComponent (Lantern Flame)

*   `_enabled`: 0 - Initially disabled.
*   `image_file`: `data/props_gfx/lantern_small_flame.xml` - Sprite for the flame.
*   `emissive`: 1 - The flame emits light.

### LuaComponent

*   `script_source_file`: `data/scripts/animals/shaman_lantern.lua` - The script controlling the lantern's behavior.

### LightComponent

*   `r`, `g`, `b`: 30, 255, 30 - Green light color.
*   `radius`: 120 - The radius of the light emitted by the lantern.

### ParticleEmitterComponent (Lantern)

*   `emitted_material_name`: `steam` - Emits steam particles.
*   `count_min`, `count_max`: 4, 10 - Number of particles emitted.
*   `lifetime_min`, `lifetime_max`: 0.1, 0.3 - Duration of steam particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: 30, 120 - Interval between steam emissions.

*   `emitted_material_name`: `spark_green` - Emits green sparks.
*   `lifetime_min`, `lifetime_max`: 0.3, 8.9 - Duration of sparks.
*   `create_real_particles`: 0 - Cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: 3, 3 - Constant spark emission.

## Visual Effects (FX)

### ParticleEmitterComponent (Blood/Water FX)

*   `emitted_material_name`: `water_fading` - Emits fading water particles.
*   `y_vel_min`, `y_vel_max`: -5, -50 - Downward velocity for particles.
*   `lifetime_min`, `lifetime_max`: 0.1, 0.3 - Short lifespan for these particles.

## Audio Component

### AudioComponent

*   `file`: `data/audio/Desktop/animals.bank` - The audio bank used.
*   `event_root`: `animals/shaman` - The root event for Shaman sounds.