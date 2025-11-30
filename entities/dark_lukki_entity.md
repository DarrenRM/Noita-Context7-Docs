---
title: Dark Lukki Entity
category: entities
---

# Dark Lukki Entity

This document details the configuration of the Dark Lukki entity in Noita, focusing on its key attributes for AI-assisted modding.

## Core Attributes

The Dark Lukki is an enemy creature with specific behaviors and resistances.

*   **`name`**: `$animal_lukki_dark` - Internal identifier for the entity.
*   **`tags`**: `enemy,mortal,hittable,homing_target,teleportable_NOT,music_energy_100,lukki,glue_NOT` - Defines its fundamental properties, including being an enemy, mortal, targetable, non-teleportable, and a type of "lukki".
*   **`ItemChestComponent`**: `level="4", enemy_drop="1"` - Indicates it can drop loot of level 4 rarity and has a 100% chance to drop enemy loot.
*   **`LuaComponent`**: `script_death="data/scripts/items/drop_money.lua", remove_after_executed="1"` - When the entity dies, it executes a script to drop money and is then removed from the game.

## Visuals

The Dark Lukki has distinct visual components for its body and emissive effects.

*   **`SpriteComponent` (Body)**:
    *   `image_file="data/entities/animals/lukki/lukki_feet/lukki_dark_sprite.xml"` - Specifies the primary sprite for the entity's body.
    *   `offset_x="0", offset_y="0"` - Centers the sprite.
*   **`SpriteComponent` (Emissive)**:
    *   `image_file="data/entities/animals/lukki/lukki_feet/lukki_dark_sprite_emissive.xml"` - Defines the emissive sprite for glowing effects.
    *   `additive="1", emissive="1"` - Configures it for additive blending and emissive rendering.

## AI and Pathfinding

The Dark Lukki possesses advanced AI for movement and target acquisition.

*   **`PathFindingComponent`**:
    *   `can_dive="1", can_fly="1", can_walk="1", can_swim_on_surface="1"` - Allows it to navigate through various terrains and aerial spaces.
    *   `cost_of_flying="500"` - A high cost associated with flying, suggesting it's a less preferred movement method.
    *   `initial_jump_max_distance_x="100", initial_jump_max_distance_y="60"` - Defines its jumping capabilities.
    *   `frames_between_searches="20"` - How often it recalculates its path.
    *   `frames_to_get_stuck="120"` - Time before it considers itself stuck.
*   **`LimbBossComponent`**: `state = "1"` - Likely related to its boss-like behavior or limb management.
*   **`IKLimbsAnimatorComponent`**: Manages Inverse Kinematics for limb animations.

## Physics and Collision

Defines the physical properties and collision shapes of the Dark Lukki.

*   **`PhysicsAIComponent`**:
    *   `force_coeff="16.0", torque_coeff="50"` - Coefficients for applying forces and torques, influencing its movement responsiveness.
    *   `damage_deactivation_probability="0"` - It does not deactivate upon taking damage.
*   **`PhysicsBodyComponent`**:
    *   `angular_damping="0.02", linear_damping="0"` - Controls how quickly rotational and linear motion decays.
*   **`PhysicsShapeComponent`**:
    *   `is_circle="1", radius_x="10", radius_y="10"` - Defines a circular collision shape with a radius of 10.
    *   `friction="0.0", restitution="0.3"` - Low friction and moderate bounciness.
*   **`CellEaterComponent`**: `radius="19", eat_probability="100"` - Can consume cells within a radius of 19 with 100% probability.

## Damage and Health

Details the Dark Lukki's health, resistances, and how it takes damage.

*   **`DamageModelComponent`**:
    *   `hp="24"` - Has 24 hit points.
    *   `blood_material="slime", blood_spray_material="slime"` - Spawns slime when damaged.
    *   `materials_that_damage="acid"` - Acid damages it.
    *   `materials_how_much_damage="0.00001"` - Very low damage from environmental materials.
    *   `damage_multipliers`:
        *   `melee="0.2"` - Takes 20% damage from melee.
        *   `projectile="-0.2"` - Takes 20% less damage from projectiles.
        *   `explosion="-0.2"` - Takes 20% less damage from explosions.
        *   `fire="0.4"` - Takes 40% damage from fire.
        *   `ice="1.2"` - Takes 20% more damage from ice.
*   **`GenomeDataComponent`**:
    *   `food_chain_rank="5"` - Its position in the food chain.
    *   `is_predator="1"` - It is a predator.
*   **`HitboxComponent`**: `_tags="hitbox_weak_spot", aabb_min_x="-10", aabb_max_x="10", aabb_min_y="-10", aabb_max_y="10", damage_multiplier="1.0"` - Defines a central weak spot that takes normal damage.

## Other Components

Miscellaneous components that add to the entity's functionality.

*   **`AudioComponent`**: Two instances for general animal sounds and specific lukki sounds.
*   **`SpriteAnimatorComponent`**: `rotate_to_surface_normal="1"` - Allows sprites to rotate based on the surface normal.
*   **`ParticleEmitterComponent`**: Emits slime particles with varying velocities and lifetimes.
*   **`AreaDamageComponent`**: `damage_per_frame="0.14", damage_type="DAMAGE_MELEE"` - Deals 0.14 melee damage per frame to nearby "human" entities.
*   **Limbs**: Multiple instances of `lukki_dark_limb_animated.xml` define its articulated limbs.
*   **`GameEffectComponent`**: `effect="PROTECTION_ELECTRICITY", frames="-1"` - Grants immunity to electricity.