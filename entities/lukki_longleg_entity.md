---
title: Lukki Longleg Entity
category: entities
---

# Lukki Longleg Entity

This document describes the `lukki_longleg.xml` entity, a type of enemy creature in Noita. It details its core attributes, AI behaviors, physics properties, damage handling, and visual components.

## Core Attributes

*   **`name`**: `$animal_lukki_longleg` - The internal name for this entity.
*   **`tags`**: `enemy, mortal, hittable, homing_target, teleportable_NOT, music_energy_100, lukki, glue_NOT` - Defines its behavior and interactions within the game world. Key tags include `enemy`, `hittable`, and `lukki` (identifying it as a spider-like creature).

## Components

### ItemChestComponent

Handles item drops upon death.

*   **`level`**: `4` - Indicates the tier of loot it can drop.
*   **`enemy_drop`**: `1` - Specifies that it has a chance to drop items.

### LuaComponent

Executes Lua scripts.

*   **`script_death`**: `data/scripts/items/drop_money.lua` - The script executed when the entity dies, likely for dropping currency.
*   **`remove_after_executed`**: `1` - The component is removed after the script finishes.

### LightComponent

Defines the light emitted by the entity.

*   **`radius`**: `32` - The range of the light.
*   **`r`, `g`, `b`**: `120, 60, 10` - The color of the light (a reddish-orange).
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.

### SpriteComponent

Defines the visual appearance of the entity.

*   **`image_file`**: `data/entities/animals/lukki/lukki_feet/lukki_sprite.xml` - The primary sprite for the entity.
*   **`additive`**, **`emissive`**: `1` - Used for the `lukki_sprite_emissive.xml` to create glowing effects.

### LimbBossComponent

Indicates this entity might have boss-like properties or behaviors.

*   **`state`**: `1` - Likely an active state.

### PathFindingComponent

Governs the entity's movement and navigation.

*   **`can_dive`**, **`can_fly`**, **`can_swim_on_surface`**, **`can_walk`**: `1` - Allows the entity to move in various ways.
*   **`cost_of_flying`**: `500` - A high cost, suggesting flying is a less preferred movement method.
*   **`initial_jump_max_distance_x`**, **`initial_jump_max_distance_y`**: `100`, `60` - Defines its jumping capabilities.
*   **`jump_speed`**: `200` - The speed at which it jumps.

### PhysicsAIComponent

Controls the physics-based AI and movement forces.

*   **`force_coeff`**: `10.0` - Coefficient for applying forces.
*   **`torque_coeff`**: `50` - Coefficient for applying rotational forces.
*   **`damage_deactivation_probability`**: `0` - It does not deactivate when taking damage.

### PhysicsBodyComponent

Defines the physical properties of the entity's body.

*   **`fixed_rotation`**: `1` - Prevents the entity from rotating freely.
*   **`linear_damping`**: `0` - No linear damping, allowing for continuous movement.

### PhysicsShapeComponent

Defines the collision shape.

*   **`is_circle`**: `1` - The collision shape is a circle.
*   **`radius_x`**, **`radius_y`**: `7` - The radius of the circular collision shape.

### DamageModelComponent

Manages health, damage taken, and damage dealt.

*   **`hp`**: `8` - The entity's health points.
*   **`fire_damage_amount`**: `0.2` - The amount of fire damage it takes.
*   **`fire_probability_of_ignition`**: `0.5` - Has a 50% chance to ignite when hit by fire.
*   **`blood_material`**, **`blood_spray_material`**: `slime_green` - The material of its blood.
*   **`materials_that_damage`**: `acid` - It is damaged by acid.
*   **`damage_multipliers`**:
    *   **`melee`**: `2.0` - Takes double damage from melee attacks.
    *   **`projectile`**: `0.2` - Takes significantly less damage from projectiles.
    *   **`explosion`**: `0.8` - Takes slightly less damage from explosions.
    *   **`slice`**: `2.0` - Takes double damage from slicing attacks.

### GenomeDataComponent

Defines its place in the ecosystem.

*   **`food_chain_rank`**: `5` - Its position in the food chain.
*   **`herd_id`**: `spider` - Identifies it as part of the "spider" group.
*   **`is_predator`**: `1` - It is a predator.

### HitboxComponent

Defines a specific hitbox, likely a weak spot.

*   **`_tags`**: `hitbox_weak_spot` - Tagged as a weak spot.
*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_x`**: Defines a small rectangular area for this hitbox.
*   **`damage_multiplier`**: `1.0` - Standard damage multiplier for this hitbox.

### AudioComponent

Manages sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank used.
*   **`event_root`**: `animals` and `animals/lukki` - Specifies the sound events related to general animals and specifically lukki.

### ParticleEmitterComponent

Emits particles.

*   **`emitted_material_name`**: `radioactive_liquid` - The material of the emitted particles.
*   **`count_min`**, **`count_max`**: `1`, `5` - The number of particles emitted per burst.
*   **`lifetime_min`**, **`lifetime_max`**: `0.3`, `1.6` - The duration particles exist.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `7`, `20` - The frequency of particle emissions.
*   **`is_emitting`**: `1` - The emitter is active.

### Limbs

The entity is composed of multiple limb entities.

*   **`lukki_limb_long_animated.xml`**: Multiple instances of this base limb are used.
*   **`lukki_limb_attacker_long.xml`**: A specific limb designated for attacking.