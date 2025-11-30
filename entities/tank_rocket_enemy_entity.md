---
title: Tank Rocket Enemy Entity
category: entities
---

# Tank Rocket Enemy Entity

This document details the `tank_rocket.xml` entity, representing a formidable robotic enemy in Noita. It's designed to be a mid-to-late game threat, capable of ranged attacks and exploding upon death.

## Key Attributes and Components

The Tank Rocket entity is built upon a `base_enemy_robot.xml` foundation, inheriting many of its core functionalities. The following are the most significant components and their key attributes:

### Base Enemy Robot Inheritance

*   **`ItemChestComponent`**: Defines loot drops.
    *   `level`: Set to `2`, indicating a moderate tier of loot.

### `AnimalAIComponent`

This component governs the creature's behavior and combat capabilities.

*   **`preferred_job`**: `JobDefault` - Standard AI behavior.
*   **`escape_if_damaged_probability`**: `0` - Does not attempt to flee when damaged.
*   **`attack_melee_damage_min` / `max`**: `0.4` / `0.7` - Low melee damage, indicating it's not its primary threat.
*   **`creature_detection_range_x` / `y`**: `600` - Large detection radius.
*   **`attack_ranged_max_distance`**: `340` - Maximum range for its projectile attacks.
*   **`food_material`**: `blood` - Not relevant as `needs_food` is `0`.
*   **`needs_food`**: `0` - Does not require food.
*   **`sense_creatures`**: `1` - Actively senses other creatures.
*   **`attack_ranged_enabled`**: `0` - Ranged attacks are controlled by `AIAttackComponent`.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled.
*   **`attack_ranged_laser_sight_beam_kind`**: `1` - Uses a laser sight for aiming.
*   **`can_fly`**: `0` - Cannot fly.
*   **`aggressiveness_min` / `max`**: `1` / `80` - Exhibits a wide range of aggressiveness.

### `DamageModelComponent`

Manages the entity's health and damage resistances/vulnerabilities.

*   **`hp`**: `5` - Relatively low health.
*   **`ragdoll_material`**: `steel` - Defines the material for its ragdoll.
*   **`blood_material`**: `oil` - Spills oil when damaged.
*   **`in_liquid_shooting_electrify_prob`**: `30` - 30% chance to electrify when shooting in liquid.
*   **`damage_multipliers`**:
    *   `projectile`: `0.5` - Takes half damage from projectiles.
    *   `explosion`: `1.1` - Takes slightly more damage from explosions.
    *   `electricity`: `1.4` - Highly vulnerable to electricity.
    *   `fire`: `0.1` - Highly resistant to fire.

### `SpriteComponent` (Primary)

Defines the main visual appearance of the Tank Rocket.

*   **`image_file`**: `data/enemies_gfx/tank_rocket.xml` - Points to the sprite definition.
*   **`z_index`**: `-1` - Renders behind other elements.

### `PathFindingComponent`

Handles navigation and movement.

*   **`distance_to_reach_node_x` / `y`**: `20` - How close it gets to a pathfinding node.
*   **`frames_to_get_stuck`**: `120` - Takes 120 frames to consider itself stuck.
*   **`can_jump`**: `0` - Cannot jump.

### `CharacterPlatformingComponent`

Governs movement mechanics.

*   **`run_velocity`**: `12` - Standard running speed.

### `HitboxComponent`

Defines the collision area for interactions.

*   **`aabb_min_x` / `max_x`**: `-8` / `8` - Horizontal bounds of the hitbox.
*   **`aabb_min_y` / `max_y`**: `-12` / `4` - Vertical bounds of the hitbox.

### `ExplodeOnDamageComponent`

Determines if and how the entity explodes.

*   **`explode_on_death_percent`**: `1` - Always explodes upon death.
*   **`explode_on_damage_percent`**: `0.0` - Does not explode from taking damage, only from death.
*   **`config_explosion`**:
    *   `damage`: `3` - Explosion damage.
    *   `camera_shake`: `40` - Significant camera shake.
    *   `explosion_radius`: `40` - Large explosion radius.
    *   `ray_energy`: `180000` - High energy for destruction.
    *   `physics_explosion_power.min` / `max`: `1.1` / `1.7` - Strong physics impact.

### `SpriteComponent` (Emissive)

Adds a glowing effect to the entity.

*   **`image_file`**: `data/enemies_gfx/tank_emissive.xml` - Sprite for the emissive effect.
*   **`emissive`**: `1` - Enables emissive properties.
*   **`additive`**: `1` - Uses additive blending for the glow.
*   **`rect_animation`**: `walk` - Uses the "walk" animation for its visual cycle.

### `SpriteComponent` (Gun)

Defines the visual for the entity's weapon.

*   **`image_file`**: `data/enemies_gfx/tank_rocket_gun.xml` - Sprite for the gun.
*   **`transform_offset.y`**: `-5` - Positions the gun slightly above the main body.

### `AIAttackComponent`

Configures the entity's ranged attack behavior.

*   **`min_distance` / `max_distance`**: `0` / `300` - Attack range.
*   **`frames_between`**: `50` - Cooldown between attacks.
*   **`attack_ranged_aim_rotation_enabled`**: `1` - Can rotate to aim.
*   **`attack_ranged_use_laser_sight`**: `1` - Utilizes a laser sight.
*   **`animation_name`**: `attack_ranged` - Triggers the "attack_ranged" animation.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/rocket_tank.xml` - The projectile fired.
*   **`angular_range_deg`**: `90` - The arc within which it can aim.

### `AudioComponent` and `AudioLoopComponent`

Handle sound effects for the entity.

*   **`event_root`**: `animals/tank` - Base sound event path.
*   **`movement_loop`**: Plays a looping sound for movement.
*   **`turret_rotate_loop`**: Plays a looping sound for turret rotation.

### `GameEffectComponent`

Applies status effects.

*   **`effect`**: `PROTECTION_FREEZE` - Grants immunity to freezing.
*   **`frames`**: `-1` - Permanent immunity.

---