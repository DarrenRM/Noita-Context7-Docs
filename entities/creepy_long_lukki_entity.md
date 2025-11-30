---
title: Creepy Long Lukki Entity
category: entities
---

# Creepy Long Lukki Entity

This document details the `lukki_creepy_long.xml` entity, representing a specific type of "Lukki" enemy in Noita. It focuses on its key attributes and components relevant for AI-assisted modding.

## Core Entity Properties

*   **`name`**: `$animal_lukki_creepy_long` - The internal identifier for this entity.
*   **`tags`**: `enemy,mortal,hittable,homing_target,teleportable_NOT,music_energy_100,lukki,glue_NOT` - A collection of tags defining its behavior and interactions. Notably, it's an enemy, mortal, hittable, a homing target, cannot be teleported, has specific music energy, is a "lukki," and is not affected by glue.

## Key Components

### ItemChestComponent

*   **`level`**: `4` - Indicates the loot tier or quality.
*   **`enemy_drop`**: `1` - Suggests a chance or probability for enemy drops.

### LuaComponent

*   **`script_death`**: `data/scripts/items/drop_money.lua` - Specifies the script to execute upon the entity's death, likely for dropping currency.
*   **`remove_after_executed`**: `1` - The script will be removed after execution.

### LightComponent

*   **`radius`**: `32` - The radius of the light emitted by the entity.
*   **`r`, `g`, `b`**: `50`, `40`, `2` - Defines the color of the light (a dim, yellowish hue).
*   **`fade_out_time`**: `1.5` - How long the light takes to fade out.

### SpriteComponent

*   **`image_file`**: `data/entities/animals/lukki/lukki_feet/lukki_sprite_creepy2.xml` - Points to the XML file defining the entity's visual sprite.

### LimbBossComponent

*   **`state`**: `1` - Likely indicates an active or primary state for the limb-based AI.

### PathFindingComponent

This component governs the entity's movement and navigation.

*   **`can_dive`**: `1` - Can dive.
*   **`can_fly`**: `1` - Can fly.
*   **`can_swim_on_surface`**: `1` - Can swim on the surface.
*   **`can_walk`**: `1` - Can walk.
*   **`cost_of_flying`**: `500` - The perceived cost or effort of flying.
*   **`initial_jump_max_distance_x`**: `100` - Maximum horizontal jump distance.
*   **`initial_jump_max_distance_y`**: `60` - Maximum vertical jump distance.
*   **`jump_speed`**: `200` - The speed at which it jumps.

### PhysicsAIComponent

Manages the physics-driven AI behavior.

*   **`target_vec_max_len`**: `15.0` - Maximum length of the target vector for movement.
*   **`force_coeff`**: `10.0` - Coefficient for applying force.
*   **`torque_coeff`**: `50` - Coefficient for applying torque.

### PhysicsBodyComponent

Defines the physical properties of the entity's body.

*   **`angular_damping`**: `0.02` - Reduces rotational velocity over time.
*   **`fixed_rotation`**: `1` - Prevents the body from rotating freely.

### PhysicsShapeComponent

Defines the collision shape.

*   **`is_circle`**: `1` - The collision shape is a circle.
*   **`radius_x`, `radius_y`**: `6`, `6` - The radius of the circular shape.

### DamageModelComponent

Handles health, damage, and related effects.

*   **`hp`**: `6` - The entity's hit points.
*   **`fire_damage_amount`**: `0.2` - Amount of damage taken from fire per tick.
*   **`fire_probability_of_ignition`**: `0.5` - Probability of igniting when hit by fire.
*   **`blood_material`**: `blood_worm` - The material used for blood drops.
*   **`ragdoll_material`**: `meat_worm` - The material used for the ragdoll.
*   **`damage_multipliers`**:
    *   `melee`: `2.0` - Takes double damage from melee attacks.
    *   `projectile`: `0.5` - Takes half damage from projectiles.
    *   `explosion`: `0.0` - Takes no damage from explosions.
    *   `slice`: `0.0` - Takes no damage from slicing.

### GenomeDataComponent

Relates to the entity's place in the ecosystem.

*   **`food_chain_rank`**: `5` - Its position in the food chain.
*   **`herd_id`**: `spider` - Identifies it as part of the "spider" group.
*   **`is_predator`**: `1` - It is a predator.

### HitboxComponent

Defines a specific hitbox, likely a weak spot.

*   **`_tags`**: `hitbox_weak_spot` - Tagged as a weak spot.
*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: Defines the bounding box of the weak spot.
*   **`damage_multiplier`**: `1.0` - Standard damage multiplier for this hitbox.

### ParticleEmitterComponent

Responsible for emitting particles.

*   **`emitted_material_name`**: `radioactive_liquid_yellow` - The material of the emitted particles.
*   **`count_min`, `count_max`**: `1`, `5` - The number of particles emitted per burst.
*   **`lifetime_min`, `lifetime_max`**: `0.3`, `1.6` - The lifespan of emitted particles.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.

### Limbs

The entity utilizes multiple instances of `lukki_limb_long2.xml` for its body and a specific `lukki_limb_attacker_long2.xml` for an attacking limb.