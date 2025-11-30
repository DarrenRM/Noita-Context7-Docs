---
title: Boss Pit Entity
category: entities
---

# Boss Pit Entity

This document details the `boss_pit.xml` entity, a formidable boss creature in Noita. It outlines its core attributes, AI behaviors, physics, damage properties, and visual components.

## Core Attributes

The `boss_pit` entity is defined by a set of tags that dictate its fundamental nature and interactions within the game world.

### Tags

*   `enemy`: Identifies the entity as a hostile creature.
*   `mortal`: Indicates the entity can be killed.
*   `human`: Suggests a humanoid-like structure or behavior.
*   `hittable`: The entity can be targeted and damaged.
*   `homing_target`: Can be targeted by homing projectiles.
*   `teleportable_NOT`: Cannot be teleported.
*   `boss`: Designates this entity as a boss-level enemy.
*   `touchmagic_immunity`: Immune to magic effects that trigger on touch.
*   `music_energy_100`: Likely related to its boss music or encounter phase.
*   `miniboss`: Can be considered a miniboss.
*   `polymorphable_NOT`: Cannot be polymorphed.
*   `necrobot_NOT`: Not affected by Necrobot mechanics.
*   `glue_NOT`: Not affected by glue.
*   `curse_NOT`: Not affected by curses.

## Visual Components

These components define the appearance and visual effects associated with the Boss Pit.

### Light Component

Provides a persistent light source around the entity.

*   `radius`: 256 (The range of the light).
*   `r`, `g`, `b`: 100, 255, 130 (Color of the light, a greenish-blue).
*   `offset_y`: 0 (Vertical offset of the light source).
*   `fade_out_time`: 1.5 (How long the light takes to fade).

### Sprite Component (Main Body)

Defines the primary visual representation of the Boss Pit.

*   `image_file`: `data/entities/animals/boss_pit/body.xml` (Points to the sprite definition).

### Sprite Components (Health Bar)

These components render the entity's health bar on the UI.

*   `_tags`: `health_bar_back`, `ui` (Identifies UI elements).
*   `image_file`: `data/ui_gfx/health_slider_back.png` and `data/ui_gfx/health_slider_front.png` (Sprites for the background and foreground of the health bar).
*   `offset_x`, `offset_y`: 12, 42 (Positioning of the health bar relative to the entity).
*   `z_index`: -9000 (Ensures the health bar is rendered in the foreground).

## AI and Behavior

This section covers the logic and decision-making processes of the Boss Pit.

### LimbBoss Component

*   `state`: 1 (Likely indicates an active or primary state).

### Variable Storage Components

Used to store and manage internal states and data for the AI.

*   `name="state"`, `value_int="0"`: Stores the current state of the entity (initial state).
*   `name="memory"`, `value_string="data/entities/projectiles/enlightened_laser_darkbeam.xml"`: Stores a reference to a projectile, possibly for attack patterns.
*   `name="pathfinding_frames_stuck"`, `value_int="0"`: Tracks frames the entity has been stuck during pathfinding.

### Lua Components

These components execute custom AI logic defined in separate Lua scripts.

*   `script_source_file="data/entities/animals/boss_pit/boss_pit_logic.lua"`: Main AI logic.
    *   `execute_every_n_frame`: 40 (Runs the script every 40 frames).
*   `script_source_file="data/entities/animals/boss_pit/boss_pit_memory.lua"`: Memory and perception logic.
    *   `execute_every_n_frame`: 1 (Runs every frame for real-time updates).
*   `script_damage_received="data/entities/animals/boss_pit/boss_pit_damage.lua"`: Handles damage calculations and reactions.
*   `script_death="data/entities/animals/boss_pit/boss_pit_death.lua"`: Manages the entity's death sequence.

### PathFinding Component

Defines how the Boss Pit navigates the game world.

*   `can_dive`, `can_fly`: 1 (Can move through water and fly).
*   `can_jump`, `can_walk`, `can_swim_on_surface`: 0 (Cannot jump, walk, or swim on the surface).
*   `cost_of_flying`: 500 (High cost associated with flying, suggesting it's a primary movement method).
*   `frames_to_get_stuck`: 120 (Time before being considered stuck).
*   `jump_speed`: 200 (Speed when jumping).
*   `max_jump_distance_from_camera`: 400 (Maximum jump distance relative to the camera).

### PathFindingGridMarker Component

Helps the pathfinding system understand the entity's position on the grid.

*   `marker_offset_y`: -6 (Vertical offset for the marker).
*   `marker_work_flag`: 16 (A flag used by the pathfinding system).

### Particle Emitter Components

These components generate visual particle effects.

*   `emitted_material_name`: `spark_blue` (The type of particle emitted).
*   `gravity.y`: 0.0 (Particles are not affected by gravity).
*   `lifetime_min`, `lifetime_max`: Varies (Duration of particles).
*   `count_min`, `count_max`: Varies (Number of particles emitted).
*   `area_circle_radius.min`, `area_circle_radius.max`: Varies (Size of the emission area).
*   `is_emitting`: 1 (The emitter is active).

## Physics Components

These components govern the physical properties and interactions of the Boss Pit.

### PhysicsAI Component

Handles AI-driven physics forces and reactions.

*   `force_coeff`, `force_max`: Control the magnitude of forces applied.
*   `torque_coeff`, `torque_max`: Control rotational forces.
*   `damage_deactivation_probability`, `damage_deactivation_time_min/max`: Influence how damage affects physics activity.

### PhysicsBody Component

Defines the physical body of the entity.

*   `angular_damping`: 0.02 (Reduces rotational velocity over time).
*   `fixed_rotation`: 1 (Prevents the body from rotating freely).

### PhysicsShape Component

Describes the collision shape of the entity.

*   `is_circle`: 1 (The shape is a circle).
*   `radius_x`, `radius_y`: 19 (Radius of the circular collision shape).
*   `friction`: 0.0 (No friction).
*   `restitution`: 0.3 (Bounciness).

## Damage and Health

This section details how the Boss Pit takes damage and its health properties.

### DamageModelComponent

Manages the entity's health, damage resistances, and death effects.

*   `hp`: 32 (Hit points).
*   `air_needed`: 0 (Does not require air).
*   `falling_damages`: 0 (Does not take damage from falling).
*   `fire_probability_of_ignition`: 0 (Cannot be set on fire).
*   `blood_material`: `slime_green` (The material of blood splatters).
*   `ragdoll_material`: `rock_static_glow` (Material for the ragdoll effect).
*   `ragdoll_fx_forced`: `DISINTEGRATED` (The type of ragdoll effect).
*   `critical_damage_resistance`: 1.0 (No resistance to critical damage).
*   `physics_objects_damage`: 0 (Cannot be damaged by physics objects).

#### Damage Multipliers

These define how much damage the entity takes from different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| melee       | 1.0        |
| projectile  | 0.3        |
| explosion   | 0.3        |
| electricity | 0.3        |
| fire        | 0.3        |
| ice         | 0.3        |
| drill       | 0          |
| holy        | 0.4        |

### GenomeData Component

Relates to the entity's place in the game's ecosystem.

*   `food_chain_rank`: 5 (High rank, indicating it's a top predator).
*   `herd_id`: `boss_limbs` (Likely groups it with other boss-related entities).
*   `is_predator`: 1 (It is a predator).

### Hitbox Component

Defines the area that registers hits.

*   `damage_multiplier`: 0.1 (Reduces damage taken by 90% within this hitbox).
*   `aabb_max_x`, `aabb_max_y`, `aabb_min_x`, `aabb_min_y`: Define the bounding box of the hitbox.

## Other Components

Miscellaneous components that add functionality.

### Audio Component

Manages sound effects for the entity.

*   `file`: `data/audio/Desktop/animals.bank` (The audio bank containing the sounds).
*   `event_root`: `animals` or `animals/boss_limbs` (The root event for sounds).

### SpriteAnimator Component

Enables sprite animations for the entity.

### CellEater Component

Allows the entity to consume cells or other entities.

*   `radius`: 32 (The radius within which it can eat).
*   `eat_probability`: 100 (Always attempts to eat within its radius).

### GameEffect Components

Applied effects to the entity.

*   `effect`: `STUN_PROTECTION_FREEZE`, `STUN_PROTECTION_ELECTRICITY` (Provides immunity to these status effects).
*   `frames`: -1 (Indicates the effect is permanent).

## Tentacles

The Boss Pit spawns multiple tentacle entities, which are defined as separate entities inheriting from a base tentacle file.

### Tentacle Entities

Each `Entity` block with a `<Base file="data/entities/animals/boss_pit/tentacle.xml">` tag instantiates a tentacle.

*   `InheritTransformComponent`: Used to position each tentacle relative to the Boss Pit.
    *   `Transform position.x`, `position.y`: Specific coordinates for each tentacle's placement.

## Summary

The Boss Pit is a complex entity designed as a challenging boss encounter. Its AI is driven by multiple Lua scripts, enabling sophisticated movement and attack patterns. It possesses significant health and resistances, along with visual cues like a light source and a health bar. The inclusion of tentacles adds to its threat and visual complexity. Its pathfinding capabilities suggest it can navigate various terrain types, primarily through flight.