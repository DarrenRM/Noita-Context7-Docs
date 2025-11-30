---
title: Creepy Lukki Entity
category: entities
---

# Creepy Lukki Entity

This document details the `lukki_creepy.xml` entity, representing a "Creepy Lukki" enemy in Noita. It focuses on key attributes relevant to AI modding.

## Core Attributes

*   **`name`**: `$animal_lukki_creepy` - The internal identifier for this entity.
*   **`tags`**: `enemy,mortal,hittable,homing_target,teleportable_NOT,music_energy_100,lukki,glue_NOT` - Defines its behavior and interactions. Notably, it's an enemy, mortal, hittable, a homing target, cannot be teleported, and is not affected by glue.

## Components

### ItemChestComponent

*   **`level`**: `4` - Indicates the loot tier.
*   **`enemy_drop`**: `1` - Suggests a chance for drops.

### LuaComponent

*   **`script_death`**: `data/scripts/items/drop_money.lua` - Specifies the script to execute upon death, likely for dropping money.
*   **`remove_after_executed`**: `1` - The script will be removed after execution.

### LightComponent

*   **`radius`**: `32` - The radius of the light emitted.
*   **`r`, `g`, `b`**: `0`, `50`, `30` - Defines the color of the light (a greenish hue).
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.

### SpriteComponent

*   **`image_file`**: `data/entities/animals/lukki/lukki_feet/lukki_sprite_creepy.xml` - Points to the sprite definition for the Creepy Lukki.

### AI Components

#### LimbBossComponent

*   **`state`**: `1` - Likely indicates an active or primary state.

#### PathFindingComponent

This component governs the entity's movement and pathfinding capabilities.

*   **`can_dive`**: `1` - Can dive.
*   **`can_fly`**: `1` - Can fly.
*   **`can_swim_on_surface`**: `1` - Can swim on the surface.
*   **`can_walk`**: `1` - Can walk.
*   **`cost_of_flying`**: `500` - The cost associated with flying in pathfinding calculations.
*   **`frames_between_searches`**: `20` - How often the AI searches for a new path.
*   **`frames_to_get_stuck`**: `120` - How long it takes for the AI to consider itself stuck.
*   **`initial_jump_max_distance_x`**: `100` - Maximum horizontal jump distance.
*   **`initial_jump_max_distance_y`**: `60` - Maximum vertical jump distance.
*   **`jump_speed`**: `200` - The speed at which it jumps.

#### PathFindingGridMarkerComponent

*   **`marker_work_flag`**: `16` - A flag used for grid-based pathfinding.

### Physics Components

#### PhysicsAIComponent

Manages the physics simulation for the AI.

*   **`target_vec_max_len`**: `15.0` - Maximum length of the target vector for movement.
*   **`force_coeff`**: `10.0` - Coefficient for applying force.
*   **`torque_coeff`**: `50` - Coefficient for applying torque.
*   **`damage_deactivation_probability`**: `0` - Never deactivates due to damage.

#### PhysicsBodyComponent

Defines the physical properties of the entity's body.

*   **`angular_damping`**: `0.02` - Resistance to rotational movement.
*   **`fixed_rotation`**: `1` - The entity's rotation is fixed.

#### PhysicsShapeComponent

Defines the collision shape.

*   **`is_circle`**: `1` - The collision shape is a circle.
*   **`radius_x`, `radius_y`**: `6`, `6` - The radius of the circular shape.
*   **`restitution`**: `0.3` - How "bouncy" the entity is.

### DamageModelComponent

Handles health and damage interactions.

*   **`hp`**: `6` - The entity's hit points.
*   **`fire_damage_amount`**: `0.2` - Amount of fire damage it can take.
*   **`fire_probability_of_ignition`**: `0.5` - 50% chance to ignite when hit by fire.
*   **`blood_material`**: `slime_green` - The material of the blood it bleeds.
*   **`materials_that_damage`**: `acid` - Materials that can damage this entity.
*   **`materials_how_much_damage`**: `0.1` - The amount of damage from those materials.
*   **`ragdoll_material`**: `meat_slime_green` - The material for its ragdoll.
*   **`damage_multipliers`**:
    *   `melee`: `2.0` - Takes double damage from melee attacks.
    *   `projectile`: `1.0` - Takes normal damage from projectiles.
    *   `explosion`: `0.5` - Takes half damage from explosions.
    *   `electricity`: `1.2` - Takes 20% more damage from electricity.
    *   `fire`: `1.2` - Takes 20% more damage from fire.

### GenomeDataComponent

Defines its place in the ecosystem.

*   **`food_chain_rank`**: `5` - Its position in the food chain.
*   **`herd_id`**: `spider` - Identifies it as part of the "spider" group.
*   **`is_predator`**: `1` - It is a predator.

### HitboxComponent

Defines a weak spot.

*   **`_tags`**: `hitbox_weak_spot` - Tagged as a weak spot.
*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: Defines the bounding box of the weak spot.
*   **`damage_multiplier`**: `1.0` - Standard damage multiplier for this hitbox.

### AudioComponent

*   Two instances are present, linking to `data/audio/Desktop/animals.bank` with different `event_root` values (`animals` and `animals/lukki`), suggesting distinct sound events for general animal sounds and specific lukki sounds.

### SpriteAnimatorComponent

*   **`target_sprite_comp_name`**: `character` - The sprite component to animate.

### ParticleEmitterComponent

*   **`emitted_material_name`**: `radioactive_liquid_yellow` - The material of the particles emitted.
*   **`count_min`, `count_max`**: `1`, `5` - The number of particles emitted per burst.
*   **`lifetime_min`, `lifetime_max`**: `0.3`, `1.6` - The lifespan of emitted particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `12`, `25` - The interval between particle emissions.
*   **`is_emitting`**: `1` - The emitter is active.

### Limbs

The entity utilizes several `lukki_limb.xml` and one `lukki_limb_attacker.xml` entities to form its body structure. These are defined using `<Entity><Base file="..."/></Entity>` tags.