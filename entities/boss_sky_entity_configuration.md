---
title: Boss Sky Entity Configuration
category: entities
---

# Boss Sky Entity Configuration

This document details the configuration of the "Boss Sky" entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Entity Definition

The `boss_sky.xml` file defines the Boss Sky entity, a formidable airborne enemy.

```xml
<Entity tags="enemy,mortal,human,hittable,homing_target,teleportable_NOT,boss,polymorphable_NOT,miniboss,music_energy_000,necrobot_NOT,glue_NOT,touchmagic_immunity" name="$animal_boss_sky" >
  <!-- ... other components ... -->
</Entity>
```

### Key Tags:

*   **`enemy`**: Identifies the entity as an enemy.
*   **`mortal`**: The entity can be killed.
*   **`hittable`**: The entity can be damaged.
*   **`homing_target`**: Can be targeted by homing projectiles.
*   **`teleportable_NOT`**: Cannot be teleported.
*   **`boss`**: Marks the entity as a boss.
*   **`polymorphable_NOT`**: Cannot be polymorphed.
*   **`miniboss`**: Indicates it's a miniboss.
*   **`music_energy_000`**: Likely relates to music cues or energy states.
*   **`touchmagic_immunity`**: Immune to touch-based magic.

## Physics Components

These components govern the physical behavior and collision of the Boss Sky.

### `PhysicsBodyComponent`

Controls the fundamental physics properties.

*   **`is_bullet="1"`**: Suggests it might behave like a projectile in some contexts, though its primary role is an enemy.
*   **`angular_damping="0.9"`**: High damping for rotational stability.
*   **`hax_fix_going_through_ground="1"`**: A specific fix to prevent clipping through terrain.

### `PhysicsShapeComponent`

Defines the entity's collision shape and material properties.

*   **`is_circle="1"`**: The collision shape is a circle.
*   **`radius_x="6"`, `radius_y="6"`**: Defines the radius of the circular collision.
*   **`material="rock_box2d_nohit_heavy"`**: The material used for physics interactions, indicating it's heavy and doesn't take impact damage itself.
*   **`density="50"`**: High density contributes to its weight and physics.

## Damage and Health

### `DamageModelComponent`

Manages the entity's health and how it takes damage.

*   **`hp="10"`**: The entity has 10 hit points.
*   **`fire_damage_amount="0.2"`**: Takes a small amount of damage from fire.
*   **`materials_that_damage="lava"`**: Only lava causes it damage.
*   **`materials_how_much_damage="0.001"`**: Lava deals minimal damage.
*   **`ragdoll_fx_forced="DISINTEGRATED"`**: Upon death, it disintegrates.

## AI and Behavior

### `Base file="data/entities/base_enemy_flying.xml"`

Inherits core flying enemy behaviors.

#### `AnimalAIComponent`

Governs the AI decision-making.

*   **`escape_if_damaged_probability="35"`**: Has a 35% chance to flee when damaged.
*   **`creature_detection_range_x="250"`, `creature_detection_range_y="250"`**: Detects creatures within a large radius.
*   **`needs_food="0"`**: Does not require food.
*   **`sense_creatures="1"`**: Actively senses other creatures.
*   **`can_fly="0"`**: Despite being an airborne enemy, this is set to 0, implying its flight is managed by other components.

#### `PathFindingComponent`

Handles movement and pathfinding logic.

*   **`can_swim_on_surface="1"`, `can_dive="1"`, `can_walk="1"`, `can_jump="1"`**: Capable of various movement types.
*   **`jump_speed="100"`**: Defines its jump velocity.
*   **`jump_trajectories`**: A list of predefined jump arcs for movement.

### `PhysicsAIComponent`

Provides physics-based AI control for movement and reactions.

*   **`target_vec_max_len="15.0"`**: Maximum length of the target vector for movement.
*   **`force_coeff="20.0"`**: Coefficient for applying force.
*   **`damage_deactivation_probability="80"`**: High probability (80%) of deactivating when damaged.
*   **`damage_deactivation_time_min="60"`, `damage_deactivation_time_max="120"`**: Deactivation lasts between 60-120 frames.
*   **`levitate="0"`**: Not set to levitate by default.

## Visuals and Audio

### `SpriteComponent`

Defines the visual appearance of the entity.

*   **`image_file="data/entities/animals/boss_sky/boss_sky.png"`**: Specifies the sprite image.
*   **`offset_x="6"`, `offset_y="6"`**: Offsets for sprite positioning.

### `AudioComponent`

Manages sound effects.

*   **`file="data/audio/Desktop/animals.bank"`**: Points to the audio bank.
*   **`event_root="animals/skullfly"`**: Base event name for sounds.

### `AudioLoopComponent`

Handles looping audio for continuous effects.

*   **`event_name="animals/boss_sky/movement_loop"`**: The specific looping sound event.
*   **`auto_play="1"`**: The loop starts automatically.

## Special Components

### `LuaComponent`

Allows for custom scripting.

*   **`script_source_file="data/entities/animals/boss_sky/boss_sky.lua"`**: The primary Lua script for the entity.
*   **`script_damage_received`, `script_death`**: Specifies scripts to call on damage and death events.
*   **`call_init_function="1"`, `execute_on_added="1"`**: Ensures initialization and execution on entity addition.

### `BossHealthBarComponent`

Enables a health bar for the boss.

*   **`gui_max_distance_visible="350"`**: The health bar is visible up to 350 units away.

### `ParticleEmitterComponent`

Creates visual particle effects.

*   **`emitted_material_name="spark"`**: Emits "spark" particles.
*   **`lifetime_min="0.5"`, `lifetime_max="1.2"`**: Particle lifespan.
*   **`area_circle_radius.min="32"`, `area_circle_radius.max="72"`**: Emission area.
*   **`velocity_always_away_from_center="240"`**: Particles are strongly pushed away from the emitter's center.