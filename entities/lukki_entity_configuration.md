---
title: Lukki Entity Configuration
category: entities
---

# Lukki Entity Configuration

This document details the configuration of the "Lukki" entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Core Entity Properties

The Lukki is an enemy creature with several defining tags and properties.

*   **Name:** `$animal_lukki` (internal identifier)
*   **Tags:** `enemy`, `mortal`, `hittable`, `homing_target`, `music_energy_100`, `lukki`, `glue_NOT`
    *   `enemy`: Identifies it as a hostile creature.
    *   `mortal`: Indicates it can be killed.
    *   `hittable`: Can be targeted and damaged.
    *   `homing_target`: Can be targeted by homing projectiles.
    *   `music_energy_100`: Likely relates to its contribution to in-game music.
    *   `lukki`: Specific tag for this creature type.
    *   `glue_NOT`: Does not interact with glue effects.

## Combat and Loot

### ItemChestComponent

This component governs loot drops.

*   **level:** `4` (Indicates the rarity or tier of loot)
*   **enemy_drop:** `1` (Likely a probability or flag for dropping items)

### LuaComponent

Handles scripting for death events.

*   **script_death:** `data/scripts/items/drop_money.lua` (Executes a script to drop money upon death)
*   **remove_after_executed:** `1` (The component is removed after the script runs)

## Visuals

### LightComponent

Defines the emissive light cast by the Lukki.

*   **radius:** `32`
*   **r, g, b:** `120, 60, 10` (A reddish-orange hue)
*   **fade_out_time:** `1.5` seconds

### SpriteComponent

Multiple components define the Lukki's visual appearance, layering different sprite assets.

*   **image_file:** Specifies the XML file for each sprite part (e.g., `lukki_sprite_b.xml`, `lukki_wiggle.xml`, `lukki_sprite_emissive_b.xml`).
*   **additive:** `1` (For the emissive sprite, indicating additive blending)
*   **emissive:** `1` (For the emissive sprite, indicating it emits light)

## AI and Movement

### LimbBossComponent

*   **state:** `1` (Likely an initial state for boss-like behavior)

### PathFindingComponent

This is a crucial component for defining how the Lukki navigates the game world.

*   **can_dive:** `1` (Can move underwater)
*   **can_fly:** `1` (Can move through the air)
*   **can_walk:** `1` (Can move on ground)
*   **can_swim_on_surface:** `1` (Can swim on the water's surface)
*   **cost_of_flying:** `500` (High cost, suggesting it prefers not to fly unless necessary)
*   **jump_speed:** `200`
*   **initial_jump_max_distance_x:** `100`
*   **initial_jump_max_distance_y:** `60`
*   **frames_between_searches:** `20` (How often it re-evaluates its path)
*   **frames_to_get_stuck:** `120` (Time before it considers itself stuck)

### PathFindingGridMarkerComponent

Helps the pathfinding system understand the entity's position on the grid.

*   **marker_offset_y:** `-6`
*   **marker_work_flag:** `16`

### IKLimbsAnimatorComponent

Component for Inverse Kinematics limb animation.

## Physics

### PhysicsAIComponent

Governs the physics-based AI movement and forces.

*   **force_coeff:** `10.0`
*   **torque_coeff:** `50`
*   **damage_deactivation_probability:** `0` (Does not deactivate when damaged)

### PhysicsBodyComponent

Defines the physical properties of the Lukki's body.

*   **angular_damping:** `0.02`
*   **fixed_rotation:** `1` (Prevents unwanted rotation)
*   **linear_damping:** `0`

### PhysicsShapeComponent

Defines the collision shape.

*   **is_circle:** `1`
*   **radius_x, radius_y:** `8`
*   **friction:** `0.0`
*   **restitution:** `0.3` (Bounciness)

### CellEaterComponent

Allows the entity to consume cells.

*   **radius:** `13`
*   **eat_probability:** `100` (Always attempts to eat cells within its radius)

## Damage and Health

### DamageModelComponent

Manages health, damage taken, and damage multipliers.

*   **hp:** `6.5`
*   **fire_damage_amount:** `0.2`
*   **fire_probability_of_ignition:** `0.5`
*   **blood_material:** `slime_green`
*   **blood_spray_material:** `slime_green`
*   **materials_damage:** `acid` (Takes damage from acid)
*   **materials_how_much_damage:** `0.1`
*   **ragdoll_material:** `meat_slime_green`

#### Damage Multipliers

| Damage Type | Multiplier |
| :---------- | :--------- |
| melee       | 2.0        |
| projectile  | 0.2        |
| explosion   | 0.8        |
| electricity | 0.6        |
| fire        | 1.2        |
| slice       | 2.0        |
| ice         | 1.2        |

### GenomeDataComponent

*   **herd_id:** `slimes` (Groups it with other slime-like creatures)

### HitboxComponent

Defines a weak spot for increased damage.

*   **_tags:** `hitbox_weak_spot`
*   **aabb_min_x, aabb_max_x:** `-10, 10`
*   **aabb_min_y, aabb_max_y:** `-10, 10`
*   **damage_multiplier:** `1.0` (This multiplier is applied *on top* of the base damage multipliers for the weak spot itself)

## Other Components

### AudioComponent

Defines sound events associated with the Lukki.

*   **file:** `data/audio/Desktop/animals.bank`
*   **event_root:** `animals` and `animals/lukki`

### SpriteAnimatorComponent

Handles sprite animations.

*   **target_sprite_comp_name:** `character` (Likely targets the main sprite component for animation)

### ParticleEmitterComponent

Emits particles, in this case, `radioactive_liquid`.

*   **emitted_material_name:** `radioactive_liquid`
*   **count_min/max:** `1-5`
*   **lifetime_min/max:** `0.3-1.6` seconds
*   **emission_interval_min/max_frames:** `7-20` frames
*   **is_emitting:** `1` (Actively emits particles)

## Limbs

The Lukki entity is composed of multiple limb entities, including animated limbs and a specific attacker limb.

*   **Base file:** `data/entities/animals/lukki/lukki_feet/lukki_limb_animated.xml` (Used for multiple standard limbs)
*   **Entity name:** `limb_attacker`
    *   **Base file:** `data/entities/animals/lukki/lukki_feet/lukki_limb_attacker.xml` (Specific limb for attacking)