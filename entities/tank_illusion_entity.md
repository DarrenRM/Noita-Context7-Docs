---
title: Tank Illusion Entity
category: entities
---

# Tank Illusion Entity

This document describes the `tank.xml` entity, which represents an illusionary "tank" enemy in Noita. It's designed to mimic a robotic tank with ranged attack capabilities and a unique visual appearance.

## Key Attributes and Components

The Tank Illusion entity is built upon a `Base` entity, inheriting many of its properties. The following are the most significant components and their key attributes:

### Base Entity Configuration

*   **`Base file="data/entities/base_enemy_robot.xml"`**: Inherits core functionality from the `base_enemy_robot.xml` entity.

### AnimalAIComponent

This component governs the AI behavior of the tank.

*   **`preferred_job="JobDefault"`**: The default job assigned to this AI.
*   **`escape_if_damaged_probability="0"`**: The tank will not attempt to flee when damaged.
*   **`attack_melee_damage_min="0.4"` / `attack_melee_damage_max="0.7"`**: Defines the minimum and maximum damage for melee attacks (though melee is disabled).
*   **`creature_detection_range_x="600"` / `creature_detection_range_y="600"`**: The range at which the tank can detect other creatures.
*   **`attack_ranged_min_distance="0"` / `attack_ranged_max_distance="500"`**: The minimum and maximum distance for ranged attacks.
*   **`food_material="blood"`**: The material it consumes for sustenance (though `needs_food` is 0).
*   **`needs_food="0"`**: The tank does not require food.
*   **`sense_creatures="1"`**: The tank is capable of sensing creatures.
*   **`attack_melee_enabled="0"`**: Melee attacks are disabled for this entity.
*   **`can_fly="0"`**: The tank cannot fly.
*   **`aggressiveness_min="1"` / `aggressiveness_max="95"`**: Sets the range for the tank's aggressiveness.

### SpriteComponent (Base)

*   **`image_file="data/enemies_gfx/tank.xml"`**: The primary sprite for the tank's body.
*   **`alpha="0.5"`**: The base sprite has a semi-transparent appearance.
*   **`z_index="-1"`**: Renders the base sprite behind other elements.

### SpriteComponent (Emissive)

*   **`_tags="character"`**: This sprite is associated with the character's visual representation.
*   **`image_file="data/enemies_gfx/tank_emissive.xml"`**: Uses an emissive texture for a glowing effect.
*   **`emissive="1"` / `additive="1"`**: Enables emissive and additive blending for the sprite.
*   **`rect_animation="walk"`**: Specifies the walk animation for this sprite.

### SpriteComponent (Gun)

*   **`_tags="gun"`**: This sprite represents the tank's gun.
*   **`image_file="data/enemies_gfx/tank_gun_illusion.xml"`**: The sprite file for the gun.
*   **`transform_offset.y="-5"`**: Offsets the gun's position vertically.
*   **`update_transform="1"`**: The gun's transform (position/rotation) is updated.
*   **`z_index="-1"`**: Renders the gun sprite behind other elements.

### AIAttackComponent (Machinegun)

This component defines the tank's primary ranged attack, resembling a machine gun.

*   **`min_distance="30"` / `max_distance="500"`**: Attack range.
*   **`frames_between="3"`**: Delay between attacks.
*   **`attack_ranged_aim_rotation_enabled="1"`**: Enables aiming the gun.
*   **`attack_ranged_entity_file="data/entities/projectiles/machinegun_bullet_tank.xml"`**: The projectile fired by this attack.
*   **`angular_range_deg="90"`**: The arc within which the gun can aim.

### AIAttackComponent (Grenade)

This component defines a secondary ranged attack, firing grenades.

*   **`min_distance="8"` / `max_distance="40"`**: Attack range.
*   **`frames_between="40"`**: Delay between grenade attacks.
*   **`attack_ranged_entity_file="data/entities/projectiles/grenade_scavenger.xml"`**: The projectile fired by this attack.
*   **`attack_ranged_action_frame="8"`**: The frame at which the attack action occurs.

### AudioComponent and AudioLoopComponent

These components handle the sound effects for the tank.

*   **`file="data/audio/Desktop/animals.bank"`**: Specifies the audio bank.
*   **`event_root="animals/tank"`**: The root event for tank-specific sounds.
*   **`event_name="animals/tank/movement_loop"`**: The sound event for movement.
*   **`event_name="animals/tank/turret_rotate_loop"`**: The sound event for turret rotation.

### LifetimeComponent

*   **`lifetime="600"`**: The tank illusion will disappear after 600 frames (10 seconds).

### LuaComponent

*   **`script_source_file="data/scripts/animals/illusion_disappear.lua"`**: This script handles the illusion's disappearance logic.
*   **`execute_on_removed="1"`**: The script executes when the entity is removed.

## Summary

The Tank Illusion is a non-food-dependent, aggressive robotic enemy with a focus on ranged attacks. Its illusionary nature is conveyed through semi-transparent sprites and a script that handles its eventual disappearance. It utilizes two distinct ranged attack patterns: a rapid-fire machine gun and a slower grenade launcher. The entity is designed to be a visually distinct and potentially dangerous encounter, despite its temporary nature.