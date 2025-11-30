---
title: Berserk Spirit Entity
category: entities
---

# Berserk Spirit Entity

This document details the configuration of the Berserk Spirit entity in Noita, focusing on its AI, combat, and visual properties for modding purposes.

## Core Components

The Berserk Spirit is a flying, aggressive enemy with unique visual and behavioral traits.

### Base Enemy Flying

This entity inherits core functionalities from the `base_enemy_flying.xml`.

### AnimalAIComponent

This component governs the Berserk Spirit's behavior and senses.

*   **`preferred_job`**: `JobDefault` - Indicates its default AI behavior.
*   **`escape_if_damaged_probability`**: `35` - Has a 35% chance to flee when damaged.
*   **`attack_melee_damage_min`**: `0.6` - Minimum melee damage.
*   **`attack_melee_damage_max`**: `0.8` - Maximum melee damage.
*   **`creature_detection_range_x` / `y`**: `250` - Range at which it detects other creatures.
*   **`needs_food`**: `0` - Does not require food.
*   **`sense_creatures`**: `1` - Actively senses creatures.
*   **`can_fly`**: `1` - Capable of flight.

### DamageModelComponent

Defines the Berserk Spirit's health and damage resistances/vulnerabilities.

*   **`hp`**: `3` - Has 3 hit points.
*   **`ragdoll_material`**: `rock_static_glow` - The material used for its ragdoll effect.
*   **`blood_material`**: `plasma_fading` - The material of its blood.
*   **`air_needed`**: `0` - Does not require air.

#### Damage Multipliers

*   **`projectile`**: `0.8` - Takes 80% damage from projectiles.
*   **`explosion`**: `0.8` - Takes 80% damage from explosions.
*   **`slice`**: `0.4` - Takes 40% damage from slicing attacks.
*   **`holy`**: `1.2` - Takes 120% damage from holy attacks.

### SpriteComponent

Controls the visual appearance of the Berserk Spirit.

*   **`image_file`**: `data/enemies_gfx/berserkspirit.xml` - Specifies the graphical definition.
*   **`additive`**: `1` - Uses additive blending for rendering.
*   **`emissive`**: `1` - The sprite is emissive, meaning it glows.

### PathFindingComponent

Determines how the entity navigates the game world.

*   **`can_fly`**: `1` - Can navigate through the air.

### GenomeDataComponent

Information related to the entity's genetic makeup and role in the ecosystem.

*   **`herd_id`**: `ghost` - Identifies its group.
*   **`food_chain_rank`**: `15` - Its position in the food chain.
*   **`is_predator`**: `1` - It is a predator.

### CharacterPlatformingComponent

Defines movement parameters, though less relevant for a flying entity.

*   **`pixel_gravity`**: `600` - Gravity applied to its movement.
*   **`jump_velocity_y`**: `0` - Cannot jump.
*   **`run_velocity`**: `0` - Cannot run.

### HitboxComponent

Defines the collision area for the entity.

*   **`aabb_min_x` / `max_x`**: `-3.5` / `3.5` - X-axis bounds of the hitbox.
*   **`aabb_min_y` / `max_y`**: `-3.5` / `3.5` - Y-axis bounds of the hitbox.

### AudioComponent

Manages the entity's sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank containing its sounds.
*   **`event_root`**: `animals/ghost` - The root event name for its sounds.

## Additional Components

### AudioLoopComponent

Plays a continuous sound effect during movement.

*   **`event_name`**: `animals/ghost/movement_loop` - The specific sound event for movement.
*   **`auto_play`**: `1` - Starts playing automatically.

### GameEffectComponent

Applies a persistent game effect to the entity.

*   **`effect`**: `PROTECTION_FREEZE` - Grants immunity to freezing.
*   **`frames`**: `-1` - The effect is permanent.

### LuaComponent

Attaches a Lua script to control custom behaviors.

*   **`script_source_file`**: `data/scripts/animals/spirit_aura_berserk.lua` - The script file responsible for its unique aura effects.
*   **`execute_every_n_frame`**: `101` - The script runs every 101 frames.

### ParticleEmitterComponent

Generates visual particle effects.

*   **`emitted_material_name`**: `spark_red` - The material of the emitted particles.
*   **`lifetime_min` / `max`**: `0.5` / `1.2` - Duration particles exist.
*   **`count_min` / `max`**: `20` / `30` - Number of particles emitted per burst.
*   **`area_circle_radius.min` / `max`**: `32` / `72` - The radius of the emission area.
*   **`velocity_always_away_from_center`**: `240` - Particles are strongly pushed away from the emitter's center.